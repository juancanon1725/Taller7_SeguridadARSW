## Author

Juan Pablo Poveda Cañon

# SEGURIDAD EN APLICACIONES WEB Y WEBSOCKETS

artiendo de la aplicación web del tablero interactivo debe construir una aplicación web segura y que sea segura a a nivel de websockets.

Código inicial del tablero: https://github.com/dnielben/tableroInteractivo2023.git

a. Para asegurar la parte web debe usar autenticación basada en passwords y conexiones seguras sobre https.

b. Implemente un protocolo de seguridad para websockets como el siguiente:

El protocolo WebSocket no maneja la autorización o autenticación.

Un patrón común que parece resolver el problema de autenticación de WebSocket es un sistema de autenticación basado en un "ticket":
Cuando el código del lado del cliente decide abrir un WebSocket, se pone en contacto con el servidor HTTP para obtener un "ticket" de autorización.

El servidor genera este ticket. Por lo general, contiene algún tipo de ID de usuario / cuenta, la IP del cliente que solicita el ticket, una marca de tiempo y cualquier otro tipo de registro interno que pueda necesitar.

El servidor almacena este ticket (es decir, en una base de datos o caché) y también lo devuelve al cliente.

El cliente abre la conexión WebSocket y envía este "ticket" como parte de un apretón de manos inicial.

El servidor puede comparar este ticket, verificar las IP de origen, verificar que el ticket no se haya reutilizado y no haya expirado, y hacer cualquier otro tipo de verificación de permisos. Si todo va bien, la conexión WebSocket ahora se verifica.

Evolucione su backend para que sea totalmente stateless, es decir, que soporte fallas del servidor y escalamiento horizontal elástico.

## Prerequisitos

Maven: Automatiza y estandariza el flujo de vida de la construcción de software.

Git: Administrador descentralizado de configuraciones.

 
 
## Instalación

Clonamos el proyecto TallerSeguridadARSW donde se encuentra el backend de nuestra aplicación Web.  

```
git clone https://github.com/juancanon1725/TallerSeguridadARSW.git
```

## Ejecución

Para compilar el proyecto se debe usar:

```
 mvn clean install
```

Para ejecutar el proyecto utilizamos los comandos:

```
 mvn spring-boot:run 
```

![CorrerSpring](https://github.com/user-attachments/assets/85a515ed-f95c-4f85-8f17-07e1db9291fd)

Tenemos nuestra pantalla de Welcome

![Welcome](https://github.com/user-attachments/assets/21651b1f-37df-488c-a607-af4c819808b7)

En 'Create' podemos crear un usuario:

![create](https://github.com/user-attachments/assets/ef2620c4-6782-4d61-91da-43c62873b1b7)

Y podemos ver que en la base de datos se crea un usuario

![database](https://github.com/user-attachments/assets/f3c80bb7-f316-4a41-8cdf-4bcb28140461)

Con el usuario creado podemos ir a loguearnos con el usuario

![login](https://github.com/user-attachments/assets/e368a4f7-d052-4ae1-bbe8-31e9a61df686)

Y en seguido verificamos la funcioalidad del juego

![tablero](https://github.com/user-attachments/assets/d0c03658-2f0b-4464-9795-f7687d1b6565)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

