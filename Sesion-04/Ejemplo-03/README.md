# Ejemplo 3 - Pruebas de regresión

## :dart: Objetivos

- Identificar las caracteristicas de las pruebas de regresión
- eleccionar casos de prueba para pruebas de regresión

## Desarrollo

### ¿Qué son las pruebas de regresión?

Las pruebas de regresión se definen como un tipo de prueba de software para confirmar que un programa reciente o un
cambio de código no ha afectado negativamente a las funciones existentes. Las prueba de regresión no es más que una
selección total o parcial de casos de prueba ya ejecutados que se vuelven a ejecutar para garantizar que las
funcionalidades existentes funcionen bien.

Esta prueba se realiza para asegurarse de que los nuevos cambios de código no tengan efectos secundarios en las
funcionalidades existentes. Garantiza que el código antiguo siga funcionando una vez que se hayan realizado los últimos
cambios en el código.

### Necesidad de pruebas de regresión

La necesidad de las pruebas de regresión surge principalmente cuando existe la necesidad de cambiar el código y
necesitamos probar si el código modificado afecta o no a la otra parte de la aplicación de software. Además, se
necesitan pruebas de regresión cuando se agrega una nueva función a la aplicación de software y para corregir defectos y
problemas de rendimiento.

### Cómo hacer pruebas de regresión

Para realizar el proceso de pruebas de regresión, primero debemos depurar el código para identificar los errores. Una
vez que se identifican los errores, se realizan los cambios necesarios para solucionarlo, luego se realiza la prueba de
regresión seleccionando casos de prueba relevantes del conjunto de pruebas que cubre las partes modificadas y afectadas
del código.

El mantenimiento del software es una actividad que incluye mejoras, correcciones de errores, optimización y eliminación
de funciones existentes. Estas modificaciones pueden hacer que el sistema funcione incorrectamente. Por lo tanto, las
pruebas de regresión se vuelven necesarias. Las pruebas de regresión se pueden llevar a cabo utilizando las siguientes
técnicas:

#### Volver a probar todo

Este es uno de los métodos para las pruebas de regresión en el que se deben volver a ejecutar todas las pruebas en el
grupo o conjunto de pruebas existente. Esto es muy costoso ya que requiere mucho tiempo y recursos.

#### Selección de pruebas de regresión

La selección de prueba de regresión es una técnica en la que se ejecutan algunos casos de prueba seleccionados del
conjunto de pruebas para probar si el código modificado afecta o no a la aplicación de software. Los casos de prueba se
clasifican en dos partes, casos de prueba reutilizables que se pueden usar en ciclos de regresión posteriores y casos de
prueba obsoletos que no se pueden usar en ciclos posteriores.

#### Priorización de casos de prueba

Priorice los casos de prueba según el impacto comercial, las funcionalidades críticas y de uso frecuente. La selección
de casos de prueba en función de la prioridad reducirá en gran medida el conjunto de pruebas de regresión.

### Selección de casos de prueba para pruebas de regresión

Se encontró a partir de datos de la industria que una buena cantidad de defectos informados por los clientes se debieron
a correcciones de errores de última hora que crearon defectos secundarios y, por lo tanto, seleccionar el caso de prueba
para la prueba de regresión es un arte y no es tan fácil. Las pruebas de regresión efectivas se pueden realizar
seleccionando los siguientes casos de prueba:

     Casos de prueba que tienen defectos frecuentes
     Funcionalidades más visibles para los usuarios
     Casos de prueba que verifican las características principales del producto
     Casos de prueba de funcionalidades que han sufrido cambios más recientes
     Todos los casos de prueba de integración
     Todos los casos de prueba complejos
     Casos de prueba de valor límite
     Una muestra de casos de prueba exitosos
     Una muestra de casos de prueba de falla

### Ejercicio

Continuando con el login que hemos trabajado durante esta sesión, imaginemos que se descubre un problema donde el login
lanza una excepción cuando la contraseña contiene los siguientes caracteres: `$"%&`

Nuestro primer paso sería definir si queremos aceptarlos o no.

Si decidimos que queremos aceptarlos debemos considerarlo un defecto(bug) y levantar la incidencia correspondiente.

Como parte de la solución se debería incluir un nuevo conjunto de pruebas (unitarias o de integración) donde se valide
que al ingresar contraseñas con estos caracteres el código funciona correctamente. A este conjunto de pruebas que valida
regresar a un estado incosistente tambipen se le conoce como pruebas de regresión.

Por último seleccionariamos nuestro conjunto de pruebas para aplicar la tecnica de _regression testing_, aquí deberiamos
incluir las pruebas de: sign up, login y modificar contraseña.

