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

### Desarrollo eficiente de software. 
    Las iteraciones más pequeñas (pasos) permiten pruebas más fáciles y eficientes. El alcance limitado del código en cada nueva iteración, así como el alcance para probarlo, facilita la búsqueda y corrección de errores. Las funcionalidades se evalúan más fácilmente en cuanto a su utilidad y aceptación por parte del usuario, y las funcionalidades menos útiles se ajustan fácilmente o incluso se abandonan antes de que se invierta un mayor tiempo de desarrollo.
    
### Productos de software competitivos. 
    Los enfoques tradicionales de desarrollo de software pueden llevar meses o años, y las especificaciones y los requisitos formalizados no se adaptan bien a las necesidades y expectativas cambiantes de los usuarios. El desarrollo de CI/CD se adapta fácilmente a los requisitos nuevos y cambiantes, lo que permite a los desarrolladores implementar cambios en iteraciones posteriores. Los productos desarrollados con CI/CD pueden llegar al mercado más rápido y con más éxito.

### Libertad para fallar. 
La rápida ciclicidad de CI/CD permite a los desarrolladores experimentar con algoritmos y estilos de codificación innovadores, con mucho menos riesgo que los paradigmas tradicionales de desarrollo de software. Si un experimento no funciona, probablemente nunca verá producción y se puede deshacer en la próxima iteración rápida. El potencial de innovación competitiva es un poderoso impulsor para que las organizaciones utilicen CI/CD.

### Mejor mantenimiento del software. 
Los errores pueden tardar semanas o meses en corregirse en el desarrollo de software tradicional, pero el flujo constante de una canalización de CI/CD hace que sea más fácil abordar y corregir errores más rápido y con mayor confianza. El producto es más estable y fiable a lo largo del tiempo.

### Mejor soporte de operaciones. 
Los lanzamientos regulares de software mantienen al personal de operaciones en sintonía con los requisitos del software y las necesidades de monitoreo. Los administradores pueden implementar mejor las actualizaciones de software y manejar los rollbacks con menos errores de implementación y resolución de problemas innecesaria. Del mismo modo, las tecnologías de automatización de TI pueden ayudar a acelerar las implementaciones y reducir los errores de instalación o configuración.

A pesar de estos atractivos beneficios, los líderes empresariales y los equipos de desarrollo deben considerar algunos de los peligros potenciales de los pipelines de CI/CD:

### Dedicación a la automatización. 
    
    CI/CD se basa en la consistencia de un conjunto de herramientas establecido y una fuerte automatización para realizar builds de software, probar e implementar cada build. Esto exige una gran inversión intelectual para implementar y administrar la automatización, lo que puede implicar una curva de aprendizaje pronunciada. Los cambios en el proceso de desarrollo o el conjunto de herramientas pueden tener un impacto profundo en el pipeline de CI/CD, por lo que CI/CD a menudo se emplea en entornos de desarrollo maduros y activos.
    
### Disciplina y planificación del personal. 
    Un proceso de CI/CD no puede aportar todo el valor a la empresa si no está generando constantemente nuevas versiones, probando versiones candidatas e implementando candidatas seleccionadas en producción. Esto requiere una planificación cuidadosa y habilidades expertas en gestión de proyectos. Los desarrolladores deben cumplir con las pautas de desarrollo establecidas para garantizar la calidad, el estilo y los estándares arquitectónicos. Mientras tanto, los líderes empresariales y las partes interesadas del proyecto pueden sentirse extremadamente incómodos con las implementaciones automatizadas en paradigmas de implementación continua, y las reuniones para tomar decisiones manuales sobre la implementación pueden estar cargadas de estrés por consecuencias desconocidas o imprevistas. Esto puede causar demoras innecesarias, todo mientras llegan nuevas compilaciones a través del pipeline.
    
### Comunicación y colaboración. 
Ninguna cantidad de automatización y herramientas es un sustituto de una buena comunicación y colaboración entre los desarrolladores y las partes interesadas del proyecto. Estas interacciones facilitan la experimentación rápida y eficiente que hace que CI/CD sea tan poderoso. La automatización y las herramientas son solo medios para ese fin.
