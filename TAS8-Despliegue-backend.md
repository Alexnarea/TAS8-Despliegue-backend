# TAS8 - Despliegue backend con base datos local
## 1. Título  
Contenerización de una Aplicación Backend con PostgreSQL y pgAdmin utilizando Docker y Multi-stage Build

## 2. Tiempo de duración  
El tiempo fue de 200 minutos. 

## 3. Fundamentos

### Dockerfile 

Un contenedor Docker tiene una vida limitada e interactúa con su entorno. Imagina que contenedor es como un organismo vivo. Piensa en un organismo unicelular, como una célula de levadura. Siguiendo esta analogía, una imagen Docker equivale, digamos, a la información genética: todos los contenedores creados a partir de una imagen son iguales, como todos los organismos unicelulares clonados a partir de una unidad de información genética. El Dockerfile define los pasos a seguir para crear una nueva imagen. Hay que entender que se empieza siempre con una imagen base existente. La nueva imagen nace de la imagen base. Además, hay ciertos cambios puntuales. En nuestro ejemplo de la célula de levadura, los cambios serían mutaciones (¿Qué Es El Dockerfile? - IONOS, n.d.). 

### ¿Cómo funciona un Dockerfile y cómo se crea una imagen a partir de él?

Dockerfile es un archivo de texto totalmente normal. El Dockerfile contiene un conjunto de instrucciones, cada una en una línea distinta. Para crear una Docker Image, las instrucciones se ejecutan una tras otra. Quizás te suene este esquema de la ejecución de un script por lotes. Durante la ejecución, se añaden paso por paso más capas a la imagen.  Una imagen Docker se crea ejecutando las instrucciones de un Dockerfile. Este paso se conoce como el proceso build y empieza con la ejecución del comando “docker build”. El contexto de construcción es un concepto crucial: define a qué archivos y directorios tiene acceso el proceso de construcción, donde un directorio local hace las veces de fuente. El contenido del directorio fuente se transfiere al Docker Daemon al accionar “docker build”. Las instrucciones contenidas en el Dockerfile reciben acceso a los archivos y directorios contenidos en el contexto de construcción (¿Qué Es El Dockerfile? - IONOS, n.d.).

<img src="./dockimage/dfile.jpeg" alt="contenedor react docker" width="500"/>

## 4. Conocimientos previos

El estudiante debe conocer:
- Fundamentos de Sping Boot.
- Comandos básicos de Docker.
- Lectura y escritura de archivos `Dockerfile`.
- Uso de entornos .env para variables de configuración.
- Conceptos básicos de bases de datos relacionales y PostgreSQL.


## 5. Objetivos a alcanzar

- Contenerizar la aplicación backend mediante un Dockerfile.
- Implementar multi-stage build para optimizar la imagen.
- Configurar los servicios de base de datos y cliente (pgAdmin) en docker-compose.yml.
- Gestionar variables de entorno mediante archivo .env.
- Verificar la conexión del backend con PostgreSQL.
- Validar la conexión desde pgAdmin al servicio de base de datos.


## 6. Equipo necesario

- Computador.
- Navegador web.
- Conexión a internet.

## 7. Material de apoyo

- Documentación oficial de Docker.
- Cheatsheet de comandos Docker.
- Repositorio de la práctica.
- Videos tutoriales.
- Guía de asignatura.

## 8. Procedimiento

### Pasos 

1. Clona el repositorio del proyecto backend.

Figura 8-1 Clonacion del repositorio backend.

<img src="./dockimage/clonacion.PNG" alt="contenedor react docker" width="500"/>

2. Crear archivo .env con las variables necesarias para la configuración.

Figura 8-2 Variables de entorno definidas.

<img src="./dockimage/levantamiento.PNG" alt="contenedor react docker" width="500"/>

3.Crear el archivo Dockerfile con técnica de multi-stage build.

Figura 8-3 Dockerfile multi-stage.

<img src="./dockimage/file.PNG" alt="contenedor react docker" width="500"/>


4. Configurar docker-compose.yml para los servicios backend, PostgreSQL y pgAdmin.

Figura 8-4 Estructura de docker-compose.

<img src="./dockimage/i3.PNG" alt="contenedor react docker" width="500"/>

5. Levantar los servicios con docker-compose up --build -d y verificar su ejecución.

Figura 8-5 Backend corriendo y Flyway ejecutando migraciones.

<img src="./dockimage/container.PNG" alt="contenedor react docker" width="500"/>

6. Acceder a pgAdmin y conectar con PostgreSQL correctamente.

Figura 8-6 Conexión desde pgAdmin al servicio de PostgreSQL.

## 9. Resultados esperados

Al finalizar la práctica, se cumplió exitosamente con todos los objetivos propuestos. La aplicación backend fue contenerizada correctamente utilizando un Dockerfile con multi-stage build. Se creó una imagen liviana y optimizada que fue ejecutada mediante docker-compose, junto con una base de datos PostgreSQL y la herramienta de administración pgAdmin. Durante el proceso se verificó:
- La conexión entre la aplicación y la base de datos PostgreSQL mediante logs de Spring Boot.
- La ejecución automática de migraciones con Flyway.
- La exposición de puertos y correcta ejecución en segundo plano.
- La conexión a la base de datos desde pgAdmin, confirmando la persistencia y la comunicación en red entre los servicios.
Todo el proceso fue acompañado de capturas que evidencian los pasos seguidos, desde la clonación del repositorio hasta la verificación de la aplicación corriendo dentro del contenedor.

 <img src="./dockimage/resultado.PNG" alt="contenedor react docker" width="500"/>


## 10. Bibliografía

- ¿Qué es el Dockerfile? - IONOS. (n.d.). Retrieved May 16, 2025, from https://www.ionos.com/es-us/digitalguide/servidores/know-how/dockerfile/

