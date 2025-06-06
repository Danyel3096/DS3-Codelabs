# Introducción a la Práctica de Kubernetes

En esta guía aprenderás paso a paso cómo desplegar y gestionar una aplicación en Kubernetes. Se usarán imágenes ilustrativas para comprender cada proceso.

## Preparación del entorno

En esta sección se configura el entorno necesario para comenzar a trabajar con Kubernetes.

![Preparar el entorno - Minikube iniciado](./Imagenes/Kubernetes_1.png)  
*Minikube iniciado correctamente.*

![Preparar el entorno - Verificación del clúster](./Imagenes/Kubernetes_2.png)  
*Verificación de que el clúster está funcionando.*


## Desplegando la primera aplicación

Ahora se crea y despliega la primera aplicación en Kubernetes utilizando un deployment.

![Crear el deployment - archivo yaml](./Imagenes/Kubernetes_3.png)  
*Se define el archivo de configuración del deployment.*

![Crear el deployment - aplicación desplegada](./Imagenes/Kubernetes_4.png)  
*Aplicación desplegada correctamente con `kubectl apply`.*

![Crear el deployment - ver pods](./Imagenes/Kubernetes_5.png)  
*Se verifican los pods en ejecución.*

![Crear el deployment - verificar servicios](./Imagenes/Kubernetes_6.png)  
*Se comprueba que el servicio está creado y funcionando.*


### Accediendo desde el navegador

El siguiente paso es abrir la aplicación en el navegador utilizando la URL proporcionada por Minikube o el servicio NodePort.

![Acceder desde el navegador - vista en navegador](./Imagenes/Kubernetes_7.png)  
*La aplicación se muestra correctamente en el navegador.*


### Escalando la aplicación

Se aumenta la cantidad de réplicas para escalar horizontalmente la aplicación.

- Se aumenta el número de réplicas a 3 con el siguiente comando:

![Aumentar el número de replicas](./Imagenes/Kubernetes_8.png)
