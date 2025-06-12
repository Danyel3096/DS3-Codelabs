# CodeLab: Sobre Attribute-Driven Design (ADD)

## 1. ¿Cuál es el propósito principal de la metodología ADD en el diseño de arquitecturas de software?
ADD busca guiar la creación de una arquitectura de software partiendo de los atributos de calidad y los requisitos del sistema. Su propósito es ofrecer una metodología ordenada que permita tomar decisiones arquitectónicas alineadas con los objetivos del negocio y las necesidades técnicas, considerando los compromisos necesarios entre distintas alternativas.

## 2. ¿Qué atributos de calidad se consideran en ADD y por qué son importantes en el proceso de diseño?
En ADD, los atributos de calidad son esenciales porque definen cómo debe comportarse el sistema más allá de sus funcionalidades, y estos atributos influyen directamente en cómo se diseña la arquitectura y qué decisiones se toman. Entre los más relevantes están:

- **Rendimiento:** Para garantizar tiempos de respuesta aceptables.
- **Escalabilidad:** Para soportar un aumento de usuarios o datos sin degradación.
- **Mantenibilidad:** Para facilitar la evolución y corrección del sistema.
- **Disponibilidad:** Para asegurar que el sistema esté activo cuando se necesite.
- **Seguridad:** Para proteger la integridad y confidencialidad de los datos.

## 3. Explica la importancia de la selección del módulo a diseñar en ADD. ¿Cuáles son los criterios principales para elegir un módulo?
ADD trabaja de forma progresiva, por lo que seleccionar el módulo inicial es clave para controlar la complejidad. Se elige en función de:

- **Atributos de calidad prioritarios:** Como rendimiento o seguridad.
- **Dependencias:** Se da preferencia a los módulos que otros componentes utilizan.
- **Riesgos:** Se abordan primero los módulos con mayor incertidumbre técnica.
- **Valor para el negocio:** Se priorizan los que aportan más a los objetivos comerciales.

## 4. ¿Cómo influyen las tácticas arquitectónicas en la toma de decisiones dentro de ADD? Menciona dos ejemplos de tácticas y su aplicación.
Las tácticas son estrategias utilizadas para asegurar que se cumplan los atributos de calidad y estas tácticas permiten tomar decisiones fundamentadas durante el diseño. En ADD, guían cómo se estructura el sistema. Ejemplos:

- **Uso de caché:** Mejora el rendimiento almacenando información en memoria en lugar de consultar constantemente la base de datos.
- **Circuit Breaker:** Mejora la disponibilidad evitando que errores en servicios externos afecten todo el sistema.

## 5. ¿Cuál es la relación entre los escenarios de calidad y la evaluación de la arquitectura en ADD?
Los escenarios de calidad describen situaciones concretas en las que se prueba el comportamiento del sistema. Sirven para:

- Orientar las decisiones de diseño.
- Comprobar que la arquitectura cumple con los atributos de calidad requeridos.
- Comparar opciones arquitectónicas basadas en su desempeño frente a esos escenarios.

## 6. Describe los principales pasos del proceso ADD y cómo se interrelacionan.
ADD sigue un proceso iterativo que incluye: Cada iteración permite ajustar y perfeccionar la arquitectura.

- **Recolección de requisitos:** Identificación de atributos de calidad y escenarios relevantes.
- **Selección del módulo a diseñar:** Se prioriza según criticidad, dependencias y riesgos.
- **Aplicación de tácticas y patrones:** Para cumplir con los atributos definidos.
- **Diseño de la estructura:** Definición de módulos, interfaces y relaciones.
- **Evaluación de la arquitectura:** Validación mediante escenarios de calidad.
- **Documentación:** Registro de decisiones y fundamentos.

## 7. ¿Por qué es crucial documentar las decisiones arquitectónicas en ADD? Menciona al menos tres elementos que deben incluirse en la documentación.
La documentación permite:

- Rastrear las decisiones tomadas.
- Facilitar la comunicación entre miembros del equipo.
- Asegurar que el sistema pueda evolucionar con base sólida.

Debe incluir:

- Razones detrás de cada decisión.
- Atributos de calidad que se busca lograr.
- Opciones consideradas y sus pros y contras.

## 8. En un proyecto real, ¿cómo se puede evaluar si una arquitectura diseñada con ADD cumple con los atributos de calidad esperados?
Se pueden usar métodos como:

- **Pruebas de rendimiento:** Para medir tiempos de respuesta y eficiencia.
- **ATAM:** Para analizar los efectos de decisiones en diferentes atributos.
- **Prototipos:** Para probar versiones reducidas en condiciones reales.
- **Simulaciones de fallos:** Para probar la tolerancia ante errores.

## 9. ¿Cuáles son los beneficios de utilizar ADD en comparación con otros enfoques de diseño arquitectónico?
ADD se destaca por: Esto lo hace especialmente útil en sistemas complejos y cambiantes.

- Enfocarse en atributos de calidad desde el comienzo.
- Brindar un proceso estructurado para la toma de decisiones.
- Ser iterativo y flexible, facilitando adaptaciones.
- Fomentar la documentación clara y útil.

## 10. ¿Qué desafíos pueden surgir al aplicar ADD en un equipo de desarrollo y cómo podrían abordarse?
Posibles obstáculos:

- *Falta de conocimiento sobre atributos de calidad*
➝ Solución: Capacitar al equipo en arquitectura de software.

- *Rechazo al enfoque iterativo*
➝ Solución: Mostrar beneficios como reducción de errores.

- *Problemas para documentar correctamente*
➝ Solución: Usar plantillas y herramientas colaborativas.

- *Complicaciones al evaluar la arquitectura en fases tempranas*
➝ Solución: Aplicar pruebas con prototipos o simulaciones.
