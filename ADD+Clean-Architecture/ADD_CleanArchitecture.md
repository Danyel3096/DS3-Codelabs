# CodeLab: Agregando Clean Architecture

## 1. ¿Qué es Attribute-Driven Design (ADD) y cuál es su propósito en el Diseño de Software?
El Diseño Orientado a Atributos (ADD) consiste en una serie de fases a lo largo del desarrollo de un proyecto de software, donde cada ronda de diseño puede tener lugar dentro de un incremento del proyecto, como se hace con el desarrollo de software en un sprint.

El propósito del ADD y por lo que se caracteríza, es proporcionar una guía paso a paso, ordenada y precisa para garantizar que la arquitectura de un sistema cumpla con los requisitos de calidad, si se cumplen con las tareas que deben realizarse durante las iteraciones de diseño.

### ¿Qué resuelve ADD?
- *Enfoque sistemático:* Brinda un método estructurado para diseñar arquitecturas, garantizando que se tengan en cuenta todos los aspectos fundamentales.

- *Enfoque en los atributos de calidad:* Garantiza que desde el principio se aborden los requisitos no funcionales, como el rendimiento y la seguridad.

- *Flexibilidad:* Es aplicable a diversos tipos de sistemas y proyectos, lo que la convierte en una herramienta versátil para arquitectos de software.

## 2. ¿Cómo se relaciona ADD con Clean Architecture en el proceso de diseño de sistemas?
* Ambas metodologías son eficaces para el desarrollo de proyectos grandes y complejos además de que promueven la separación de intereses y la creación de sistemas modulares y escalables:

1. Alineación con el Negocio e Independencia Tecnológica:
Mientras que ADD garantiza que el software esté profundamente alineado con el dominio del negocio, la Arquitectura Limpia garantiza que esta alineación no dependa de tecnologías específicas.

2. Reducción de la Complejidad y Modularidad
ADD ayuda a descomponer la complejidad en componentes manejables como entidades, objetos de valor y agregados. Después, al aplicar La Arquitectura Limpia se organizan estos componentes en capas diferenciadas, cada una con responsabilidades claras, lo que aumenta aún más la modularidad y la facilidad de mantenimiento del sistema.

3. Flexibilidad y Evolución Continua
Ambos enfoques facilitan la adaptación a los cambios. Empezando por ADD, se permite que el modelo de dominio evolucione a medida que cambia el negocio, mientras que la Arquitectura Limpia garantiza que estos cambios se puedan implementar sin necesidad de refactorizar otras partes del sistema.

4. Comunicación y Capacidad de Prueba
El uso de un lenguaje ubicuo en ADD mejora la comunicación entre desarrolladores y expertos, mientras que la Arquitectura Limpia, con sus capas independientes, facilita la creación de pruebas unitarias y de integración, garantizando que el sistema funcione según lo previsto.

### Relación clave:
- Gracias a que ADD proporciona un enfoque basado en calidad para tomar decisiones arquitectónicas, se definen los atributos de calidad que la arquitectura debe cumplir.
- Por otro lado, la Arquitectura Limpia ayuda con la estructuración del código de manera que haya separación de responsabilidades, ayudando a implementar esos atributos mediante la separación de capas y la inversión de dependencias.

## 3. ¿Cuáles son los pasos principales del método ADD para definir una arquitectura de software?
- *Identificar los impulsores de la arquitectura:* Comience por identificar los requisitos funcionales, los atributos de calidad (como rendimiento, modificabilidad y seguridad) y las restricciones que guiarán el diseño de la arquitectura.

- *Descomponer el sistema:* Dividir el sistema en módulos o componentes más pequeños y manejables.

- *Asignar funcionalidad:* Asignar funcionalidades específicas a diferentes módulos o componentes.

- *Definir interfaces:* Especificar las interfaces entre los componentes para garantizar que se comuniquen e interactúen correctamente.

- *Verificar y perfeccionar la arquitectura:* Verificar continuamente si la arquitectura cumple con los requisitos y realizar los ajustes necesarios.