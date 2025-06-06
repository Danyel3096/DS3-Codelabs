# CODELAB: SPRING BOOT l

## Preguntas

 **1. ¿Qué es Spring Boot y para qué sirve?**

**R//: Spring Boot** es un framework basado en Spring que facilita la creación de aplicaciones Java, proporcionando configuración automática, un servidor embebido y convenciones por defecto para agilizar el desarrollo.

**2. ¿Qué hace la anotación `@SpringBootApplication`?**

**R//:** Agrupa tres anotaciones:
-   `@SpringBootConfiguration`: Marca la clase como fuente de configuración.
-   `@EnableAutoConfiguration`: Habilita la configuración automática de Spring.
-   `@ComponentScan`: Escanea los componentes dentro del paquete para detectarlos automáticamente.

 **3. ¿Cómo se inicia una aplicación Spring Boot?**

**R//:** Se puede iniciar con:

-   **IDE (como IntelliJ o Eclipse)**: Ejecutando la clase principal con `@SpringBootApplication`.
-   **Maven:** `mvn spring-boot:run`.
-   **Jar ejecutable:** `java -jar nombre-del-archivo.jar`.

**4. ¿Qué función tiene la anotación `@RestController`?**

**R//:** Convierte la clase en un controlador de REST. Combina `@Controller` y `@ResponseBody`, permitiendo devolver datos directamente en formato JSON o XML.

 **5.¿Cómo defines una URL en un controlador de Spring Boot?**

**R//:** Usando la anotación `@RequestMapping` o específicas como `@GetMapping` o `@PostMapping`.

![image](https://github.com/user-attachments/assets/81660383-dfa5-4436-b931-9fc1862d37fc)


 **6. ¿Cuál es el puerto por defecto en el que corre Spring Boot?**

**R//:** El puerto por defecto es el **8080**.

**7. ¿Cómo cambias el puerto de la aplicación?**

**R//:** Modificando el archivo `application.properties`: con el comando `server.port = 9090`

**8. ¿Qué comando de Maven permite ejecutar una aplicación Spring Boot?**

**R//:** `mvn spring-boot:run`

**9. ¿Cómo puedes probar un endpoint de Spring Boot en el navegador?**

**R//:** Iniciando la aplicación y accediendo a la URL en el navegador, por ejemplo: `http://localhost:8080/api/saludo`.
También puedes usar herramientas como **Postman** o **cURL** para probar métodos más complejos.

**10. ¿Para qué sirve el archivo `application.properties`?**

Sirve para configurar la aplicación, definiendo propiedades como:

-   **Puerto del servidor:** `server.port=8081`.
-   **Base de datos:** spring.datasource.url=jdbc:mysql://localhost:3306/db.
-   **Nivel de logs:** `logging.level.org.springframework=DEBUG`.