# Reto 3 - Persistencia de datos

## :dart: Objetivos

- Aplicar el patrón AAA (Arrange -  Act - Assert)
- Aplicar el patrón GWT (Given - When - Then)

## ⚙ Requisitos

- WebStorm
- Node.js
- Jest

## Desarrollo

Hasta este punto ya hemos utilizado el patron de inyección de dependencias para desacoplar la capa de persistencia (
repositorio) con la lógica de negocio (entidad). A continuación validaremos que cuando una inversión es creada, dicha
inversión se guarda.


**GIVEN** un usuario
**WHEN** ingresa los datos: nombre, descripción, interes, monto, fecha de inicio y duración en días
**THEN** se crea un registro de esta nueva inversion y se persiste dicho registro

`InvestmentRepositoryContract.js`

```javascript

class InvestmentRepositoryContract {
    getId() {
        throw new Error("You have to implement the method getId");
    }

    save(investment) {
        throw new Error("You have to implement the method save");
    }
}


1. En el archivo `TestInvestment.spec.js` añade la siguiente prueba:
    ```it('saves investment', () => {}); ```
2. Añadir el código necesario para validar que el meotdo save del repositorio es llamado
3. En el archivo `Investment.js` implementar la logica necesaria para pasar las pruebas.


```

<details>
  <summary>Solución</summary>

1. Creamos la prueba que nos permite validar que la inversión fue guardada.

`TestInvestment.spec.js`

```javascript

const Investment = require("../../entities/Investment");
const InvestmentRepositoryContract = require("../../repositories_contracts/InvestmentRepositoryContract");

class InvestmentRepositoryStub extends InvestmentRepositoryContract {
    constructor(id) {
        super();
        this.id = id;
        this.saveCalls = [];
    }

    getId() {
        return this.id;
    }

    save(investment) {
        this.saveCalls.push(investment);
    }
}

describe('Investment', () => {
    describe('Add new investment', () => {
        it('calculates end date based on initial day plus duration', () => {
            const name = "cetes 28 days";
            const description = "cetes for 28 days";
            const interest = 4.5;
            const startingAmount = 10;
            const durationDays = 28;
            const startDate = new Date('2021-01-01');
            const repository = new InvestmentRepositoryStub('123e4567-e89b-12d3-a456-426655440000');
            const expectedEndDate = new Date('2021-01-29');

            const investment = Investment.addInvestment(name, description, interest, startingAmount, startDate, durationDays, repository);

            expect(investment.endDate).toEqual(expectedEndDate);
        });

        it('calculates final amount based on starting amount plus interest generated in the amount of time', () => {
            const name = "cetes 28 days";
            const description = "cetes for 28 days";
            const interest = 4.5;
            const startingAmount = 10;
            const durationDays = 28;
            const startDate = new Date('2021-01-01');
            const repository = new InvestmentRepositoryStub('123e4567-e89b-12d3-a456-426655440000');
            const expectedFinalAmount = 10 * (1 + (((interest / 100) / 360) * durationDays));

            const investment = Investment.addInvestment(name, description, interest, startingAmount, startDate, durationDays, repository);

            expect(investment.finalAmount).toEqual(expectedFinalAmount);
        })

        it('assigns id gotten from repository', () => {
            const name = "cetes 28 days";
            const description = "cetes for 28 days";
            const interest = 4.5;
            const startingAmount = 10;
            const durationDays = 28;
            const startDate = new Date('2021-01-01');
            const expectedId = '123e4567-e89b-12d3-a456-426655440000';
            const repository = new InvestmentRepositoryStub(expectedId);
            const expectedFinalAmount = 10 * (1 + (((interest / 100) / 360) * durationDays));

            const investment = Investment.addInvestment(name, description, interest, startingAmount, startDate, durationDays, repository);

            expect(investment.id).toEqual(expectedId);
        })

        it('saves new investment', () => {
            const name = "cetes 28 days";
            const description = "cetes for 28 days";
            const interest = 4.5;
            const startingAmount = 10;
            const durationDays = 28;
            const startDate = new Date('2021-01-01');
            const expectedId = '123e4567-e89b-12d3-a456-426655440000';
            const repository = new InvestmentRepositoryStub(expectedId);
            const expectedFinalAmount = 10 * (1 + (((interest / 100) / 360) * durationDays));

            const investment = Investment.addInvestment(name, description, interest, startingAmount, startDate, durationDays, repository);

            expect(repository.saveCalls.length).toEqual(1);
            expect(repository.saveCalls[0]).toEqual(investment);
        })


    })

})


```

1. Nuestro código asigna un id a la inversión utilizando el método `getId()` del repositorio

`Investment.js`

```javascript
class Investment {
    id;
    name;
    description;
    interest;
    startingAmount;
    finalAmount;
    startDate;
    endDate;

    constructor(id, name, description, interest, startingAmount, finalAmount, startDate, endDate) {
        this.id = id;
        this.name = name;
        this.description = description;
        this.interest = interest;
        this.startingAmount = startingAmount;
        this.finalAmount = finalAmount;
        this.startDate = startDate;
        this.endDate = endDate;
    }

    static addInvestment(name, description, interest, startingAmount, startDate, duration, repository) {
        const endDate = startDate;
        endDate.setDate(endDate.getDate() + duration);

        const finalAmount = Investment._calculateFinalAmount(interest, startingAmount, duration);

        const investment = new Investment(repository.getId(), name, description, interest, startingAmount, finalAmount, startDate, endDate)
        repository.save(investment);
        return investment;
    }

    static _calculateFinalAmount(interest, startingAmount, duration) {
        const bankingYear = 360;
        const interestAsPercentage = interest / 100;
        return startingAmount * (1 + (((interestAsPercentage) / bankingYear) * duration));
    }
}


module.exports = Investment;

```

</details>
