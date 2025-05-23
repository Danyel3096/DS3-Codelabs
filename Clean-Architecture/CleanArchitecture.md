# CodeLab: Sobre Clean Architecture

### 1. ¿Qué problema busca resolver Clean Architecture en el desarrollo de software?
Clean Architecture pretende solucionar el problema del fuerte acoplamiento entre la lógica del negocio y la infraestructura, facilitando que las aplicaciones sean más fáciles de mantener, ampliar y probar. En concreto, resuelve dificultades como:

- La complejidad para cambiar frameworks o tecnologías sin afectar la lógica central.
- La imposibilidad de probar el código fácilmente debido a dependencias directas con bases de datos o frameworks.
- La escasa reutilización de la lógica del negocio en distintos tipos de aplicaciones (web, móvil, escritorio).

### 2. ¿Cuáles son las principales capas de Clean Architecture y qué responsabilidad tiene cada una?
Clean Architecture se organiza en cuatro capas concéntricas, donde las dependencias siempre apuntan hacia el núcleo:

- **Entidades (Capa de Dominio):** Contiene la lógica de negocio fundamental, definiendo entidades con reglas de negocio que no cambian. Esta capa es independiente de frameworks o tecnologías.
- **Casos de Uso (Capa de Aplicación):** Implementa la lógica específica para cada aplicación, coordinando las entidades y definiendo los casos de uso. No depende de la infraestructura.
- **Adaptadores (Capa de Interfaces):** Proporciona las interfaces para interactuar con la aplicación, incluyendo controladores, APIs, vistas, etc. Se comunica con la capa de aplicación mediante interfaces de servicio.
- **Infraestructura (Capa de Frameworks y Drivers):** Incluye las implementaciones concretas de bases de datos, frameworks y herramientas externas, sin contener lógica de negocio.

### 3. ¿Qué relación tiene Clean Architecture con el principio de Inversión de Dependencias (DIP) en SOLID?
Clean Architecture aplica DIP asegurando que:

- Las capas externas dependen de las internas, nunca al revés.
- La lógica del negocio depende únicamente de abstracciones, no de implementaciones concretas de infraestructura.

### 4. ¿Por qué es importante desacoplar la lógica de negocio de la infraestructura en una aplicación?
Si la lógica de negocio está mezclada con detalles técnicos (por ejemplo, consultas SQL dentro de controladores), los cambios tecnológicos pueden provocar muchos ajustes complicados.

Separar estas capas aporta beneficios como:

- **Flexibilidad:** Se puede cambiar de base de datos, framework o tecnología sin impactar la lógica central.
- **Facilidad para probar:** La lógica de negocio puede testearse de forma aislada, sin depender de la base de datos.
- **Mantenibilidad:** El sistema puede evolucionar sin afectar todas las partes.

### 5. ¿Cómo Clean Architecture facilita la escalabilidad y mantenibilidad de un sistema?
- **Escalabilidad:**

- Permite añadir nuevas funciones sin modificar el código existente.
- Facilita dividir la aplicación en módulos independientes.
- Apoya la distribución y balanceo eficiente de la carga.

- **Mantenibilidad:**

- El código está organizado según responsabilidades claras.
- Cambios en tecnologías específicas (como cambiar de JPA a MongoDB) no afectan la lógica del negocio.
- Fomenta la reutilización del código.

### 6. ¿Qué diferencia hay entre la capa de dominio y la capa de aplicación en Clean Architecture?
- **Dominio:** Se encarga de definir las reglas de negocio mediante entidades y lógica inmutable.
- **Aplicación:** Coordina cómo se usan esas entidades para implementar los casos de uso específicos.

### 7. ¿Por qué los controladores (controllers) y la base de datos deben estar en la capa de infraestructura?
Porque son detalles de implementación que pueden cambiar sin impactar la lógica de negocio.
Por ejemplo, si un controlador está en la capa de aplicación y se cambia la tecnología de REST a GraphQL, esto afectaría toda la lógica. En cambio, ubicándolo en infraestructura, solo se modifica la forma en que se expone la API.

### 8. ¿Qué ventajas tiene usar una interfaz en la capa de dominio para definir repositorios en lugar de usar directamente JpaRepository?
Las interfaces en la capa de dominio aportan:

- **Desacoplamiento:** La lógica de negocio no depende directamente de la base de datos ni de JPA.
- **Flexibilidad:** Permite cambiar tecnologías sin afectar la lógica del negocio.
- **Testabilidad:** Facilita simular repositorios en pruebas unitarias.

### 9. ¿Cómo interactúan los casos de uso (UseCases) con las entidades de dominio en Clean Architecture?
Los casos de uso en la capa de aplicación coordinan la ejecución de las reglas de negocio que definen las entidades de dominio.

### 10. ¿Cómo se puede aplicar Clean Architecture en una aplicación de microservicios con Spring Boot?
- Cada microservicio está diseñado siguiendo Clean Architecture, con sus propias capas (Dominio, Aplicación, Infraestructura).
- Se usan interfaces en el dominio para desacoplar la infraestructura.
- La comunicación entre microservicios se hace mediante eventos o APIs REST sin exponer la lógica de negocio.
- Cada microservicio se despliega de forma independiente usando contenedores como Docker o Kubernetes.
