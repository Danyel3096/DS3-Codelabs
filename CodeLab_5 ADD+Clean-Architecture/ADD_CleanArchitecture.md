# CodeLab: Agregando Clean Architecture

## 1. ¿Qué es Attribute-Driven Design (ADD) y cuál es su propósito en el Diseño de Software?
El Diseño Orientado a Atributos (ADD) consiste en una serie de fases a lo largo del desarrollo de un proyecto de software, donde cada ronda de diseño puede tener lugar dentro de un incremento del proyecto, como se hace con el desarrollo de software en un sprint.

El propósito del ADD y por lo que se caracteríza, es proporcionar una guía paso a paso, ordenada y precisa para garantizar que la arquitectura de un sistema cumpla con los requisitos de calidad, siempre que se cumplan las tareas durante las iteraciones de diseño.

### ¿Qué resuelve ADD?
- *Enfoque sistemático:* Brinda un método estructurado para diseñar arquitecturas, garantizando que se tengan en cuenta todos los aspectos fundamentales.

- *Enfoque en los atributos de calidad:* Garantiza que desde el principio se aborden los requisitos no funcionales, como el rendimiento y la seguridad.

- *Flexibilidad:* Es aplicable a diversos tipos de sistemas y proyectos, lo que la convierte en una herramienta versátil para arquitectos de software.

## 2. ¿Cómo se relaciona ADD con Clean Architecture en el proceso de diseño de sistemas?
* Ambas metodologías son eficaces para el desarrollo de proyectos grandes y complejos además de que promueven la separación de intereses y la creación de sistemas modulares y escalables:

| Relación                                                               | Explicación                                                                                                                                                                                  |
| ---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Complementarios**                                                    | ADD es un *proceso de diseño*, mientras que Clean Architecture es una *estructura resultado* del diseño, por lo que se puede usar ADD para decidir si Clean Architecture es adecuada para tu sistema. |
| **ADD puede derivar en Clean Architecture**                            | Si al usar ADD se identifican necesidades como mantenibilidad, testabilidad, independencia de frameworks, entonces *Clean Architecture es una opción natural*.                             |
| **Clean Architecture satisface atributos que ADD ayuda a identificar** | Si ADD detecta necesidad de desacoplamiento (modificabilidad), Clean Architecture lo logra al invertir dependencias y aislar el dominio.                                                 |
| **Clean Architecture es una implementación concreta**                  | Es uno de los estilos arquitectónicos (como MVC, hexagonal, etc.) que puede seleccionarse durante el proceso de ADD.                                                                            |

### Relación clave:
- Gracias a que ADD proporciona un enfoque basado en calidad para tomar decisiones arquitectónicas, se definen los atributos de calidad que la arquitectura debe cumplir.
- Por otro lado, la Arquitectura Limpia ayuda con la estructuración del código de manera que haya separación de responsabilidades, ayudando a implementar esos atributos mediante la separación de capas y la inversión de dependencias.

## 3. ¿Cuáles son los pasos principales del método ADD para definir una arquitectura de software?

**Paso 1: Revisar las entradas**
Se deben analizar los pasos del propósito del diseño, los requisitos funcionales, los escenarios de atributos de calidad, las restricciones y las preocupaciones previas para garantizar la iterabilidad de los pasos 2 a 7.

**Paso 2: Filtrar elementos del sistema**
Se elige el elemento del sistema que será el foco del proyecto para la iteración de los pasos posteriores.

**Paso 3: Elegir uno o más elementos para su refinamiento.**
Analizamos el elemento seleccionado para descomponerlo y enumeramos las prioridades de los requisitos de las partes interesadas que lo afectan. Se pueden asignar prioridades altas, medias o bajas a cada requisito enumerado.

**Paso 4: Elegir uno o más conceptos de diseño.**
Debemos elegir nuestro concepto de diseño, lo que significa seleccionar los principales tipos de elementos y sus relaciones. Se pueden identificar las preocupaciones asociadas con el diseño y los componentes arquitectónicos que tienden a abordar el problema.

**Paso 5: Lista de elementos arquitectónicos.**
Se seleccionan varios tipos de elementos de software en el paso anterior. A estos elementos se les asignan responsabilidades según su tipo. La responsabilidad de los elementos enumerados se deriva de cada requisito funcional asociado.

**Paso 6: Vista previa del boceto.**
Los servicios y propiedades requeridos para cada elemento se denominan interfaz y no simplemente una lista de componentes operativos. Las interfaces pueden incluir cualquiera de los siguientes elementos:

| Interfaz | Ejemplo |
|--------------------|---------------------|
| **Sintaxis de las operaciones**   | Firma |
| **Semántica de las operaciones** | Descripción, precondiciones y poscondiciones, restricciones |
| **Información intercambiada** | Eventos marcados, datos globales |
| **Requisitos de los atributos de calidad de elementos u operaciones individuales**     | Usar colas para desacoplar pagos, al procesar un pago |
| **Gestión de errores** | añadir un sistema de monitoreo y alertas, al transferir fondos entre cuentas |

**Paso 7: Análisis del rendimiento**
En este paso, se analizará el trabajo realizado en los pasos anteriores para evitar repeticiones. En este paso, el arquitecto puede volver al paso 2 y comenzar de nuevo si algo sale fuera de contexto. Si todo funciona según lo previsto, el siguiente paso es proporcionar un nuevo elemento para una nueva iteración, de modo que comience el paso 1.

## 4. ¿Cómo se identifican los atributos de calidad en ADD y por qué son importantes?
Los atributos de calidad son requisitos no funcionales como usabilidad, confiabilidad, rendimiento y escalabilidad que el sistema debe cumplir. El proceso se da principalmente en las primeras etapas del diseño arquitectónico y se apoya en distintas fuentes:

1. A partir de los escenarios de calidad, donde ADD promueve describir los atributos de calidad como escenarios concretos, con estructura clara.

2. En la revisión de los requerimientos del sistema, se analizan los documentos de requisitos (casos de uso, historias de usuario, criterios de aceptación, restricciones del cliente) para detectar: Necesidades implícitas o explícitas de rendimiento, seguridad, disponibilidad, requisitos regulatorios o normativos (ej. PCI-DSS, HIPAA, ISO 25010).

3. Entrevistas o talleres con stakeholders, para consultar a Usuarios finales, Clientes, Dueños de producto, Equipos técnicos, y priorizar qué atributos son críticos.

4. Con un análisis del contexto y restricciones de los factores como el entorno tecnológico (web, móvil, embebido), las condiciones de red, el presupuesto o los tiempos de entrega, el número de usuarios concurrentes se pueden revelar necesidades de rendimiento, escalabilidad o simplicidad en el diseño.

### Ejemplo de atributos de calidad y cómo afectan el diseño:
Servicio de videconferencias:

| Atributo de calidad           | Escenario concreto                                                                                                        | Impacto en el diseño                                                                                                                                                                      |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Rendimiento (Performance)** | "El sistema debe iniciar una videollamada en menos de 1 segundo el 90% del tiempo."                                       | Usar *WebRTC* para conexión peer-to-peer. Minimizar llamadas al backend en el proceso de conexión. Optimizar la entrega de scripts y recursos (lazy loading, compresión). |
| **Escalabilidad**             | "Debe soportar hasta 10,000 usuarios concurrentes en diferentes videollamadas sin degradar el servicio."                  | Usar arquitectura basada en *microservicios* y *balanceo de carga*. Escalado automático con Kubernetes. Uso de servidores de medios distribuidos.                       |
| **Disponibilidad**            | "El servicio debe estar disponible el 99.99% del tiempo."                                                                 | Despliegue multi-región en la nube. Redundancia de servidores y *failover automático*. Monitoreo activo con alertas.                                                      |
| **Seguridad**                 | "Las videollamadas deben estar cifradas de extremo a extremo."                                                            | Implementar *encriptación E2E con claves temporales*. Control estricto de autenticación (OAuth, tokens JWT). Reglas de firewall y control de acceso granular.             |
| **Usabilidad**                | "Un nuevo usuario debe poder unirse a una llamada sin instalar software adicional."                                       | Web app basada en navegador sin plugins (WebRTC). Interfaz sencilla con flujos guiados.                                                                                           |
| **Mantenibilidad**            | "El sistema debe permitir añadir nuevas funcionalidades (como fondos virtuales) sin afectar las llamadas existentes."     | Arquitectura *modular*, con separación de responsabilidades. Aplicación de principios SOLID. Pruebas automatizadas y CI/CD.                                               |
| **Tolerancia a fallos**       | "Si falla el servidor de videollamada, los usuarios deben ser redirigidos automáticamente a otro sin notar interrupción." | Uso de *circuit breakers*, *reintentos automáticos* y *detección de fallos en tiempo real*. Clustering de servidores de medios.                                             |

## 5. ¿Por qué Clean Architecture complementa ADD en la implementación de una solución?
Se complementa, porque cada uno aborda una parte distinta del ciclo de diseño y construcción del software, pero ambos se pueden integrar de forma natural para lograr una arquitectura sólida, mantenible y alineada a los atributos de calidad del sistema.

## 6. ¿Qué criterios se deben considerar al definir las capas en Clean Architecture dentro de un proceso ADD?
* *Atributos de calidad:* Define capas según los atributos priorizados (rendimiento, seguridad, mantenibilidad, etc.) detectados en ADD.

* *Separación de responsabilidades:* Cada capa debe tener una única responsabilidad, por ejemplo, entidad (lógica de negocio pura), casos de uso (reglas específicas de aplicación), adaptadores (presentación, persistencia, interfaces externas) y frameworks (detalles tecnológicos (DB, web, etc.)).

* *Regla de dependencia:* Las dependencias deben ir siempre hacia el centro (de frameworks a entidades, nunca al revés).

* *Cambio controlado:* Define capas para aislar el impacto de cambios, como reemplazar una base de datos sin tocar la lógica de negocio.

* *Interfaces explícitas:* Usa interfaces para desacoplar capas y facilitar pruebas, sustitución de componentes, y adaptabilidad.

## 7. ¿Cómo ADD ayuda a tomar decisiones arquitectónicas basadas en necesidades del negocio?
ADD se encarga de traducir las necesidades del negocio en atributos de calidad. Por ejemplo, priorizando atributos según objetivos del negocio, guía en la selección de tácticas arquitectónicas, define estructuras que soporten esos atributos, justifica cada decisión
y cada elección arquitectónica que se basa en un requisito real, no en intuición.

## 8. ¿Cuáles son los beneficios de combinar ADD con Clean Architecture en un sistema basado en microservicios?
### Ventajas clave:
1. *Diseño alineado a objetivos del negocio:* ADD garantiza que los microservicios estén diseñados con base en atributos de calidad como escalabilidad, disponibilidad o seguridad, mientras que Clean Architecture permite implementar estos servicios de forma clara, desacoplada y sostenible.

2. *Modularidad y responsabilidad clara:* ADD te ayuda a identificar los módulos y límites de los microservicios, y por otro lado, Clean Architecture asegura que cada servicio tenga capas bien definidas (entidades, casos de uso, adaptadores), facilitando mantenimiento y pruebas.

3. *Alta mantenibilidad y extensibilidad:* Los cambios en reglas de negocio afectan solo la capa central de Clean Architecture. ADD ayuda a prever y preparar el diseño ante posibles cambios o crecimiento del sistema.

4. *Escalabilidad técnica guiada por necesidades reales:* ADD prioriza atributos como rendimiento o capacidad de crecimiento, guiando decisiones como balanceo, particionado de servicios, cachés, etc. Clean Architecture estructura el código de forma que se puede escalar o migrar con mínimo impacto.

5. *Independencia tecnológica:* Clean Architecture desacopla lógica del negocio de frameworks, bases de datos o protocolos. ADD permite tomar decisiones informadas sobre qué tecnologías usar según los atributos de calidad requeridos.

6. *Facilita evolución e innovación:* ADD define desde el inicio cómo se debe comportar el sistema ante cambios. Clean Architecture lo implementa de forma que esos cambios sean fáciles de introducir sin romper la arquitectura.

7. *Mejor comunicación entre técnicos y stakeholders:* ADD traduce objetivos del negocio en requisitos técnicos. Clean Architecture los implementa con una estructura que puede ser explicada y entendida fácilmente.

## 9. ¿Cómo se asegura que la arquitectura resultante cumpla con los atributos de calidad definidos en ADD?
1. *Escenarios de calidad específicos:* Se definen escenarios concretos por atributo.

2. *Tácticas arquitectónicas alineadas a cada atributo:* ADD recomienda tácticas específicas para cumplir los atributos.

3. *Decisiones arquitectónicas documentadas:* Cada decisión se justifica con su atributo asociado, permitiendo rastrear por qué se tomó una decisión y validar si sigue vigente al cambiar requisitos.

4. *Validación continua:* Durante el desarrollo se aplican prácticas como revisión de arquitectura con checklist por atributo y prototipos o pruebas de concepto (spikes) para atributos críticos (como latencia o escalabilidad).

5. *Trazabilidad entre requerimientos y componentes:* Cada componente del sistema (microservicio, módulo, clase) debe poder rastrearse hasta el atributo de calidad que motivó su existencia o forma.

6. *Monitoreo en producción:* Una vez desplegado, se usa monitoreo para verificar atributos como: Tiempos de respuesta, tasa de errores, uso de CPU/memoria validando que las decisiones siguen cumpliendo los atributos esperados.

## 10. ¿Qué herramientas o metodologías pueden ayudar a validar una arquitectura diseñada con ADD y Clean Architecture?
### Herramientas y enfoques útiles:
1. *ATAM (Architecture Tradeoff Analysis Method)*: Metodología formal para evaluar decisiones arquitectónicas en función de atributos de calidad.

2. *ADRs (Architecture Decision Records):* Documenta cada decisión arquitectónica con:

3. *Quality Attribute Scenarios:* ADD los promueve: define escenarios concretos para atributos como rendimiento, disponibilidad o seguridad.
