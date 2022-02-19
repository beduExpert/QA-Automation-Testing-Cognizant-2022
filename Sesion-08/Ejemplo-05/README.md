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


