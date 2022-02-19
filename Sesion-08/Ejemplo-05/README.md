# Ejemplo 5 - Etapas y mantenimiento de un pipeline de CI/CD 

## :dart: Objetivos

- Identificar las etapas de un pipeline de CI/CD
- Analizar los retos del mantenimiento de un pipeline de Ci/CD
- 
## ⚙ Requisitos

- WebStorm
- Node.js
- Jest
- Una cuenta de GitHub

## Desarrollo

### Etapas de un pipeline de CI/CD

Un pipeline de CI/CD combina integración, entrega e implementación continuas en cuatro fases principales: origen, construcción, prueba e implementación. Cada fase utiliza procesos, estándares, herramientas y automatización altamente detallados. Así como los productos físicos fabricados en una fábrica pueden beneficiarse de máquinas de fabricación personalizadas, los pipeklines de software se adaptan con frecuencia para satisfacer las necesidades específicas del proyecto y el negocio.

#### Fuente.

La primera fase de un pipeline de CI/CD es la creación del código fuente, donde los desarrolladores traducen los requisitos en algoritmos, comportamientos y características funcionales. Las herramientas empleadas para esto dependen de si el equipo de desarrollo está trabajando en Java, .NET, C#, PHP o muchos otros lenguajes de desarrollo. Los entornos de desarrollo integrados (IDE) a menudo se seleccionan porque admiten un lenguaje específico además de varias funciones de verificación de código, como la detección básica de errores, el escaneo de vulnerabilidades y el cumplimiento de los estándares de codificación establecidos. Otras herramientas de soporte de canalización y código fuente, incluidos los repositorios de código y los sistemas de control de versiones como Git, suelen formar la base para las fases de creación y prueba.

No hay una canalización única para la creación de fuentes. Una empresa puede tener varias partes de origen del pipeline de CI/CD según los diversos proyectos en desarrollo, como una plataforma del lado del servidor que usa C++, aplicaciones de sitios web que usan Java y aplicaciones móviles que usan Go. Del mismo modo, las funciones de codificación pueden variar entre los IDE y los proyectos debido a los diferentes estándares o vulnerabilidades entre los proyectos, como los sistemas de producción empresarial frente a una aplicación de consumo.

#### Construir. 

El proceso de compilación extrae el código fuente de un repositorio, establece enlaces a bibliotecas, módulos y dependencias relevantes, y compila (construye) todos estos componentes en un archivo ejecutable (.exe). Las herramientas utilizadas en esta etapa también generan registros del proceso, indican errores para investigar y corregir, y notifican a los desarrolladores que la compilación se completó.

Al igual que con la creación de código fuente, las herramientas de compilación generalmente dependen del lenguaje de programación seleccionado. Un grupo de desarrollo puede emplear herramientas independientes para generar una compilación; muchos IDE incorporan tales capacidades de compilación, lo que significa que admiten de manera efectiva tanto la creación de fuentes como las fases de compilación dentro de un pipeline de CI/CD.

Una fase de compilación puede emplear herramientas adicionales, como secuencias de comandos, para traducir el archivo ejecutable a un entorno de ejecución empaquetado o implementable, como una VM (completa con un sistema operativo y componentes relacionados) o un contenedor, como un contenedor Docker con bibliotecas y dependencias

#### Prueba. 

Si bien el código fuente ya completó algunas pruebas estáticas, la compilación completa ahora ingresa a la siguiente fase de CI/CD de pruebas dinámicas integrales. Por lo general, esto comienza con pruebas funcionales o unitarias básicas para verificar que las nuevas características y funciones funcionen según lo previsto, y pruebas de regresión para garantizar que los nuevos cambios o adiciones no interrumpan accidentalmente ninguna característica que funcione anteriormente. La compilación también se somete a una batería de pruebas de integración, aceptación por parte del usuario y rendimiento. Si se producen errores durante las pruebas, los resultados se envían a los desarrolladores para su análisis y corrección en compilaciones posteriores.

La automatización es particularmente crítica en la fase de prueba de CI/CD, donde una compilación se somete a una enorme variedad de pruebas y casos de prueba para validar su funcionamiento. Las pruebas en humanos suelen ser demasiado lentas y están sujetas a errores y descuidos para garantizar resultados de prueba fiables u objetivos. Los especialistas en pruebas crean criterios y casos de prueba integrales, pero dependen de las herramientas de prueba para implementar las pruebas y la validación en una tubería ocupada.

#### Desplegar. 

En última instancia, la compilación pasa la fase de prueba y se considera candidata para su implementación en un entorno de producción. En una tubería de entrega continua, se envía a las partes interesadas humanas, se aprueba y luego se implementa. En un pipeline de implementación continua, la compilación se implementa automáticamente tan pronto como pasa su conjunto de pruebas.

El paso de implementación suele implicar la creación de un entorno de implementación, por ejemplo, el aprovisionamiento de recursos y servicios dentro del centro de datos, y el traslado de la compilación a su destino de implementación, como un servidor. Estos pasos generalmente se automatizan con scripts o a través de flujos de trabajo en herramientas de automatización. Las implementaciones también suelen conectarse a herramientas de informes de errores y emisión de tickets para encontrar errores inesperados después de implementar la compilación y alertar a los desarrolladores. Los usuarios también pueden enviar tickets de errores para indicar errores reales o percibidos con el lanzamiento.

Incluso los candidatos a la implementación más optimistas rara vez se comprometen con la producción sin reservas. Las implementaciones con frecuencia implican precauciones adicionales y períodos de prueba en vivo, incluidas pruebas beta, pruebas A/B, pruebas azul/verde y otros períodos cruzados para reducir o revertir problemas de software imprevistos y minimizar el impacto comercial.


### Mejores practicas

#### Empieza pequeño. 

CI/CD brinda velocidad y agilidad, así que déle tiempo al proceso para que evolucione y permita que los desarrolladores prueben diferentes herramientas y pasos. Una empresa puede comenzar con un pipeline de CI y agregar CD más adelante. Los pequeños proyectos son lugares ideales para probar nuevas herramientas y técnicas que pueden mejorar un pipeline más amplio.

#### Defina el éxito. 

Comprenda los beneficios previstos, como una creación de código más rápida o menores tasas de error/reelaboración, y luego implemente métricas para medir esos criterios. Compare las métricas con el rendimiento previo a la canalización y realice un seguimiento de esas métricas a medida que evoluciona el pipeline. Esto hace que sea más fácil ver el valor de la canalización, detectar problemas a lo largo del tiempo e invertir en formas de construir y mejorar la canalización de CI/CD.

#### Procesos de documentos. 

A menudo pasada por alto y subestimada, la documentación es una parte esencial del proceso de desarrollo. Presenta el proceso y las herramientas para todos los desarrolladores y usuarios comerciales, y explica cómo se relaciona y configura todo. Además, puede ayudar a solucionar problemas. La documentación también contribuye a la postura de cumplimiento y seguridad de una organización, lo que permite a los líderes auditar las actividades.

#### Piensa en las operaciones.

Los paradigmas de desarrollo ágiles, como DevOps y la implementación continua, abarcan funciones tanto de operaciones como de desarrollo. Los desarrolladores deben comprender tanto la implementación como las operaciones, y apropiarse más de la confiabilidad y el rendimiento del software. Los líderes empresariales y de proyectos deben fomentar y reforzar este cambio de actitud.

#### Centrarse en la retroalimentación. 

La retroalimentación dentro del de CI/CD es más efectiva cuando cada paso, y cada participante, trabaja activamente para detectar y abordar problemas para ahorrar tiempo y trabajar de manera eficiente. Esto comienza con la detección de errores en el código fuente y continúa durante todo el proceso de prueba e implementación. Por ejemplo, encuentre y corrija un error de sintaxis en el código fuente en la etapa de compilación, en lugar de perder tiempo y esfuerzo durante la fase de prueba. La categorización y el análisis de errores también pueden ayudar a las empresas a mejorar las habilidades y los procesos de desarrollo.

#### Incluir seguridad en todo. 

Las herramientas de escaneo de seguridad a nivel de código (herramientas SAST y SCA) son útiles para el diagnóstico temprano de vulnerabilidades y errores, pero pueden producir una gran cantidad de falsos positivos. El escaneo de seguridad a nivel de prueba (herramientas DAST e IAST) requiere que el software se construya y se ejecute, lo que significa que los errores se detectan más adelante en el pipeline, donde las correcciones de errores requieren más tiempo y son más costosas. Seleccione las mejores herramientas de análisis de seguridad para las tareas en cuestión y utilícelas para actualizar automáticamente el sistema de seguimiento de errores y generar automáticamente tickets para un rápido examen y corrección.

Además, piense en la seguridad de la canalización en sí: la autorización y la autenticación incorrectas pueden exponer las herramientas y los repositorios a acciones maliciosas. Asegure las herramientas y los repositorios, use registros para rastrear el acceso de los usuarios a ellos y marque actividades inusuales, como descargas a direcciones IP fuera de la LAN corporativa.

#### Adopte pruebas continuas. 

Durante las etapas de fuente y construcción, realice SCA, SAST y otros escaneos de código básicos para estándares de estilo y seguridad. Cuando se complete la construcción, aplique una batería de condiciones de prueba establecidas utilizando herramientas de prueba. Comience con una validación funcional simple y amplíe sistemáticamente las pruebas a una integración más compleja y completa, seguridad profunda (como DAST) y rendimiento. El personal debe construir cuidadosamente pruebas y casos de prueba para validar las características y la funcionalidad de cada nueva compilación a medida que evolucionan las compilaciones, el proyecto e incluso los requisitos del proyecto. Las nuevas funciones que se agregan con frecuencia requieren pruebas frecuentes y casos de prueba.

#### Fomentar la comunicación. 

La integración y la entrega funcionan juntas, pero a menudo se implementan por separado y las manejan diferentes equipos, como codificadores y evaluadores. Una canalización de CI/CD que funcione sin problemas requiere una comunicación y colaboración oportunas y claras entre los diferentes equipos a lo largo de la canalización; de lo contrario, puede estropearse fácilmente con retrasos innecesarios.

#### Evite el desperdicio. 

Crear y mantener un pipeline de CI/CD incurre en varios costos de herramientas, infraestructura y recursos. El uso ineficiente de cualquiera de estos (herramientas subutilizadas o sin usar, infraestructura de TI sobreasignada para pruebas e implementaciones, mala coordinación, evaluación insuficiente de procesos o herramientas) puede retrasar el desarrollo y afectar la productividad del desarrollador. Los pipelines de CI/CD son entidades dinámicas que requieren refinamiento frecuente y capacitación regular de desarrolladores para operar de manera eficiente y confiable.

Esto también significa evitar áreas menos obvias de ineficiencias. No haga 10 compilaciones diferentes en el mismo día si no hay una forma práctica de probar e implementar esas 10 compilaciones en el mismo día. Los equipos y el esfuerzo del proyecto deben reflejar el uso más efectivo del pipeline.

#### Mejorar el ecosistema. 

CI/CD y otros pilenes ágiles son ecosistemas compuestos por herramientas vinculadas con procesos y automatización, con innumerables caminos y pasos alternativos para diferentes productos. Los equipos siempre deben evaluar nuevas herramientas y refinar los procesos para mantener el pipeline general lo más fluido y eficiente posible.
