# Ejemplo 4 - Beneficios y retos de un pipeline de CI/CD 

## :dart: Objetivos

- Identificar los beneficios de un pipeline de CI/CD
- Analizar los retos de los pipelines de Ci/CD y diferentes estrategias de resolución

## ⚙ Requisitos

- WebStorm
- Node.js
- Jest
- Una cuenta de GitHub

## Desarrollo

### Beneficios y retos de un pipeline de CI/CD

itops-cicd_pipeline.png![imagen](https://user-images.githubusercontent.com/5317347/154777905-cd6f41a1-b865-4eaf-a6ca-f358057f1f45.png)

En un pipeline de CI/CD, todo está diseñado para que suceda simultáneamente: algunas partes del software se codifican, mientras otras se prueban y otras son liberadas a producción. Aún así, CI/CD implica importantes compensaciones entre beneficios y desventajas.

Los beneficios de un pipeline de CI/CD incluyen lo siguiente:

#### Desarrollo eficiente de software. 

Las iteraciones más pequeñas (pasos) permiten pruebas más fáciles y eficientes. El alcance limitado del código en cada nueva iteración, así como el alcance para probarlo, facilita la búsqueda y corrección de errores. Las funcionalidades se evalúan más fácilmente en cuanto a su utilidad y aceptación por parte del usuario, y las funcionalidades menos útiles se ajustan fácilmente o incluso se abandonan antes de que se invierta un mayor tiempo de desarrollo.
    
#### Productos de software competitivos. 

Los enfoques tradicionales de desarrollo de software pueden llevar meses o años, y las especificaciones y los requisitos formalizados no se adaptan bien a las necesidades y expectativas cambiantes de los usuarios. El desarrollo de CI/CD se adapta fácilmente a los requisitos nuevos y cambiantes, lo que permite a los desarrolladores implementar cambios en iteraciones posteriores. Los productos desarrollados con CI/CD pueden llegar al mercado más rápido y con más éxito.

#### Libertad para fallar. 

La rápida ciclicidad de CI/CD permite a los desarrolladores experimentar con algoritmos y estilos de codificación innovadores, con mucho menos riesgo que los paradigmas tradicionales de desarrollo de software. Si un experimento no funciona, probablemente nunca verá producción y se puede deshacer en la próxima iteración rápida. El potencial de innovación competitiva es un poderoso impulsor para que las organizaciones utilicen CI/CD.

#### Mejor mantenimiento del software. 

Los errores pueden tardar semanas o meses en corregirse en el desarrollo de software tradicional, pero el flujo constante de una canalización de CI/CD hace que sea más fácil abordar y corregir errores más rápido y con mayor confianza. El producto es más estable y fiable a lo largo del tiempo.

#### Mejor soporte de operaciones. 

Los lanzamientos regulares de software mantienen al personal de operaciones en sintonía con los requisitos del software y las necesidades de monitoreo. Los administradores pueden implementar mejor las actualizaciones de software y manejar los rollbacks con menos errores de implementación y resolución de problemas innecesaria. Del mismo modo, las tecnologías de automatización de TI pueden ayudar a acelerar las implementaciones y reducir los errores de instalación o configuración.

A pesar de estos atractivos beneficios, los líderes empresariales y los equipos de desarrollo deben considerar algunos de los peligros potenciales de los pipelines de CI/CD:

#### Dedicación a la automatización. 
    

CI/CD se basa en la consistencia de un conjunto de herramientas establecido y una fuerte automatización para realizar builds de software, probar e implementar cada build. Esto exige una gran inversión intelectual para implementar y administrar la automatización, lo que puede implicar una curva de aprendizaje pronunciada. Los cambios en el proceso de desarrollo o el conjunto de herramientas pueden tener un impacto profundo en el pipeline de CI/CD, por lo que CI/CD a menudo se emplea en entornos de desarrollo maduros y activos.
    
#### Disciplina y planificación del personal. 

Un proceso de CI/CD no puede aportar todo el valor a la empresa si no está generando constantemente nuevas versiones, probando versiones candidatas e implementando candidatas seleccionadas en producción. Esto requiere una planificación cuidadosa y habilidades expertas en gestión de proyectos. Los desarrolladores deben cumplir con las pautas de desarrollo establecidas para garantizar la calidad, el estilo y los estándares arquitectónicos. Mientras tanto, los líderes empresariales y las partes interesadas del proyecto pueden sentirse extremadamente incómodos con las implementaciones automatizadas en paradigmas de implementación continua, y las reuniones para tomar decisiones manuales sobre la implementación pueden estar cargadas de estrés por consecuencias desconocidas o imprevistas. Esto puede causar demoras innecesarias, todo mientras llegan nuevas compilaciones a través del pipeline.
    
#### Comunicación y colaboración. 

Ninguna cantidad de automatización y herramientas es un sustituto de una buena comunicación y colaboración entre los desarrolladores y las partes interesadas del proyecto. Estas interacciones facilitan la experimentación rápida y eficiente que hace que CI/CD sea tan poderoso. La automatización y las herramientas son solo medios para ese fin.


### Atributos de un buen pipeline de CI/CD

Entonces, ¿cómo se ve realmente el CI/CD efectivo? Estas son algunas características comunes de un buen proceso de CI/CD:

#### Velocidad. 
 
Un pipline de CI/CD puede tener numerosos pasos y partes, pero una compilación debe poder moverse a través del pipeline (integración, prueba, entrega e incluso implementación) en poco tiempo, tal vez solo unos minutos para completar una integración y unas pocas horas para que terminen los ciclos de prueba. Si lleva días mover una compilación a través del pipeline, es probable que se esté desperdiciando una gran cantidad de tiempo valioso y que el proceso deba ajustarse.
    
#### Consistencia. 

Los procesos y componentes utilizados en un lugar o ciclo son exactamente los mismos en todos los lugares y ciclos. Por ejemplo, si una compilación da como resultado un contenedor de Docker, ese contenedor es el objeto que se prueba y se mueve a través del pipeline hasta la entrega o implementación. Los desarrolladores pueden escribir scripts y crear procesos de automatización con la confianza de que dichos esfuerzos tendrán éxito y brindarán los resultados deseados en todo momento. Los procesos que introducen variaciones o pasos manuales ralentizan la canalización e invitan a errores e ineficiencia.
    
#### Control estricto de versiones. 

Los repositorios o componentes y compilaciones bien documentados permiten la restauración rápida de compilaciones anteriores cuando las nuevas compilaciones o implementaciones fallan. Un buen control de versiones facilita reversiones rápidas, precisas y confiables, tal vez a la versión de trabajo anterior, siempre que surja la necesidad.

#### Automatización. 

La automatización extensiva mueve el nuevo código a través de la integración, prueba y entrega o implementación con poca o ninguna interacción manual. Idealmente, un ser humano hace poco más que desarrollar y confirmar código, luego esperar una solicitud de extracción aprobada y aprobación antes de una implementación, si es necesario. Un pipeline que depende de pasos y procesos manuales es lenta y propensa a errores.

#### Bucles de retroalimentación integrados. 

Un pipeline de CI/CD es un bucle que produce innumerables pasos iterativos para un proyecto completo, y cada fase también ofrece un bucle de vuelta al principio. Un problema con el código fuente no generará una compilación. Un problema con la compilación no pasará a las pruebas. Un problema en las pruebas o después de la implementación exigirá soluciones de origen. Cuanto antes se identifique un problema, más rápido, más fácil y más económico será solucionarlo, lo que mantendrá en movimiento el pipeline general.

#### Seguridad en todo. 

Los descuidos y errores en la programación y las pruebas pueden crear vulnerabilidades y exponer el software a actividades maliciosas. Por lo tanto, es fundamental infundir las mejores prácticas de seguridad en todo el pipeline de CI/CD. Las herramientas como los verificadores de vulnerabilidades pueden ayudar a detectar posibles fallas de seguridad en el código que fluye a través del pipeline, mientras que se deben realizar evaluaciones de seguridad adicionales durante la fase de prueba.


![imagen](https://user-images.githubusercontent.com/5317347/154784414-52744b1f-36bb-486c-988f-8006ec03612e.png)


