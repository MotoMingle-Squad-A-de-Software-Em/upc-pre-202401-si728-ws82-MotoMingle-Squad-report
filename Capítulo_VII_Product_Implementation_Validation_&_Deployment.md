# Capítulo VII: Product Implementation, Validation & Deployment

## 7.1.	Software Configuration Management.

### 7.1.1.	Software Development Environment Configuration.
**Project Management**

Hemos utilizado como centro de organización principal Github para organizar los puntos a realizar, pendientes y realizados. Asimismo, la herramienta de Trello como establecer hitos y fijar límites para realizar sus pendientes. Solo en casos de consultas y dudas se realiza una llamada grupal en Meet.

**Requirements Management**

Al realizar las partes designadas por cada estudiante, este pasa por el criterio de todos al revisar y sugerir algún tipo de cambio para disminuir o evitar errores al momento de presentar el proyecto.
Link de referencia: https://www.figma.com/

**Product UX/UI Design**

Hemos implementado esta parte usando Figma para el diseño de los wireframe de alta fidelidad y los Mockup. Además, se utilizó para realizar el prototipo de Web App y Mobile App.
Link de referencia: https://www.figma.com

**Software Development**

Las herramientas que utilizaremos para la implementación del proyecto son:
Para el entorno de desarrollo Webstorm de JetBrains
Link de referencia: https://www.jetbrains.com/es-es/webstorm/

Framework de Angular para el diseño (Frontend)
Link de referencia: https://angular.io

**Software Deployment**

Se ha utilizado Netlify para desplegar el Frontend a través de su funcionalidad de hosting.
Link de referencia: https://www.netlify.com

**Software Documentation**

GitHub es una compañía sin fines de lucro que ofrece un servicio de hosting de repositorios almacenados en la nube, En nuestro proyecto se utiliza para potenciar el trabajo colaborativo entre miembros del equipo permitiéndonos trabajar con repositorios remotos almacenando dentro los distintos proyectos del startup como la Landing Page, SPA (Single Page Application) and Server Side Backend, en donde cada miembro del equipo se encarga de una parte específica del proyecto trabajando de modo modular.

### 7.1.2.	Source Code Management.

URL del repositorio de GitHub para cada producto: Landing Page, Web Services, Frontend Web Applications.
|Report|https://github.com/MotoMingle-Squad-A-de-Software-Em/upc-pre-202401-si728-ws82-MotoMingle-Squad-report|
|------|------------------------------------------------------------------------------------------------------|

|Backend|https://github.com/MotoMingle-Squad-A-de-Software-Em/Backend-RentCarAssits|
|-------|--------------------------------------------------------------------------|

|Frontend|https://github.com/MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits|
|--------|---------------------------------------------------------------------------|

### 7.1.3.	Source Code Style Guide & Conventions.

Como convención general, todo el código realizado por los miembros del equipo debe redactarse en completo inglés.

HTML
•	Use Lowercase Element Name
	Se recomienda usar lowercase para los nombres de los elementos HTML:

<body>
	<p>Esto en un párrafo</p>
</body>

•	Close All HTML Elements
Se recomienda cerrar todos los elementos HTML:

<body>
	<p>Estos es un párrafo</p>
	<p>Esto es otro párrafo</p>
<body>

•	Use Lowercase Attribute Names
Se recomienda usar lowercase para los nombres de los atributos HTML:

<a href=https://www.w3schools.com/html/”>Visit our HTML tutorial</a>


•	Always Specify alt, width, and height for Images
Se recomienda seguir estas convenciones en caso de que la imagen no se puede mostrar y ayudar con la accesibilidad del contenido:

<img src="html5.gif" alt="HTML5" style="width:128px;height:128px">

•	Spaces and Equal Signs
Se recomienda no usar espacios en blanco entre las entidades para una mejor lectura:

<link rel="stylesheet" href="styles.css">

Para más información sobre las convenciones de HTML se usará como referencia: https://www.w3schools.com/html/html5_syntax.asp 

CSS 

•	ID and Class Naming 
Usar nombres de clases y ID significativos que expresen el propósito del elemento:

#gallery {}
#login {}
.video {}

•	ID and Class Name Style 
Usar nombres cortos para nombrar ID o clases, pero lo suficientemente largo para saber cuál es su propósito.

#nav {} 
.author {} 

•	Shorthand Properties 
Usar CSS shothand properties tanto como sea posible para que el código sea más eficiente y entendible: 

border-top: 0;
font: 100%/1.6 palatino, georgia, serif;
padding: 0 1em 2em;

•	0 and Units 
Evitar la unidad después de usar 0 en valores que lo requieran:

margin: 0;
padding: 0; 

•	ID and Class Name Delimiters
Separar las palabras en ID y clases con un guión: 

#video-id {} 
.ads-sample {}

•	Declaration Order 
Colocar las declaraciones en orden alfabético para que sean fáciles de mantener y recordar

background: fuchsia;
border: 1px solid;
border-radius: 4px;
color: black;
text-align: center;
text-indent: 2em; 

•	Selector and Declaration Separation
Separar los selectores y declaraciones en nuevas líneas: 

h1,
h2,
h3 { 
font-weight: normal;
 line-height: 1.2;
}

Para más información sobre las convenciones de CSS se usará como referencia: https://google.github.io/styleguide/htmlcssguide.html#CSS


### 7.1.4.	Software Deployment Configuration.

Se utilizó la herramienta github para el control de versiones y ciclo de vida del proyecto.

|Report|https://github.com/MotoMingle-Squad-A-de-Software-Em/upc-pre-202401-si728-ws82-MotoMingle-Squad-report|
|------|------------------------------------------------------------------------------------------------------|

|Backend|https://github.com/MotoMingle-Squad-A-de-Software-Em/Backend-RentCarAssits|
|-------|--------------------------------------------------------------------------|

|Frontend|https://github.com/MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits|
|--------|---------------------------------------------------------------------------|

## 7.2.	Solution Implementation.

### 7.2.1.	Sprint 1

#### 7.2.1.1.	Sprint Planning 1.
En esta sección se especificarán datos importantes del Sprint Planning Meeting

| Sprint # | Sprint 1 |
| -------- | -------- |
| Sprint Planning Background |         |
| Date | 2024-06-01 |
| Time | 20:00 PM |
| Location | Discord |
| Prepared By | Miner Lozano |
| Attendees (to planning meeting) | Leonardo Cesías / Leonardo Aquino / Toshiro Ysique |
| Sprint n Velocity | 14 |

#### 7.2.1.2.	Sprint Backlog 1.
El objetivo de este sprint 1 es empezar a implementar el frontend, landing page y backend de nuestro proyecto. Para ello, se ha dividido en 4 bounded context que serán detallados en el siguiente cuadro.  
| Sprint # | Sprint 1 |      |     |      |       |       |         |
| -------- | -------- | ---- | --- | ---- | ----- | ----- | ------- |
| User Story |       | Work-Item / Task |       |    |     |      |        |
| ID | Título | ID | Título | Description | Estimation (hours) | Assigned To | Status (To/do/ In Process / To-Review / Done) |
| US043 | Usuario administrador añade un banner principal | TA001 | Lading Page Banner | Implementar banner landing page | 5 | Cesías | Done |
| US044 | Usuario visitante visualiza los features de la plataform | TA001 | Landing Page Features | Implementar sección features landing page | 3 | Cesías | Done |
| US045 | Usuario visitante compara planes y precios | TA001 | Lading Page Planes | Implementar sección de planes y precios landing page | 3 | Cesías | Done |
| US046 | Usuario visitante accede a información adicional en el footer | TA001 | Landing Page Footer | Implementar sección footer lading page | 3 | Cesías | Done |
| US001 | Usuario se registra en la aplicación con usuario y contraseña | TA001 | Formulario de Login y Register | Mejorar los formularios de login y registro | 8 | Aquino | Done |
| US002 | Usuario completa su registro con sus datos personales | TA001 | Implementar las validaciones | Mejorar las validaciones en la web de los formularios de login y register | 8 | Aquino | Done |
| US006 <br> US007 <br> US008 | Usuario se suscribe a un plan Basic, Premium, Vip  | TA001 | Mejorar planes | Mejorar la administración de los planes  | 8 | Toshiro | In Process |
| US009 <br> US010 <br> US011 | Publicar, editar, eliminar anuncio de alquiler de auto.  | TA001 | Mejorar sección de alquilar auto | Mejorar las vistas de publicar, eliminar y editar anuncios de autos  | 8 | Toshiro | In Process |
| US16 | Usuario arrendatario recibe notificaciones de sus alquileres | TA001 | Reimplementar Twilio y mejorar las noficaciones para los usuarios | 8 | Cesías | In Process |

#### 7.2.1.3.	Development Evidence for Sprint Review.
En esta parte del trabajo se presenta commits realizados por los miembros del equipo durante el sprint 1.  
En primer lugar, se mostrarán la cantidad total de commits de cada integrante del equipo, incluye fix, update.

| Integrante | Landing Page |
| ---------- | ------------ |
| Cesías Díaz, Leonardo Paolo | 19 |

| Integrantes | Web Application |
| ----------- | --------------- |
| Cesías Díaz, Leonardo Paolo | 37 |
| Aquino Cruz, Leonardo José | 16 |

Se presenta la tabla de commits con mayor relevancia:  

| Repository | Branch | Commit id | Commit Message | Commit Message Body | Commited on Date |
| ---------- | ------ | --------- | -------------- | ------------------- | ---------------- |
| MotoMingle-Squad-A-de-Software-Em/LandingPage-RentCarAssist | main | 86dbbc4eac6dfc008447176d12652dd5780a3f8c | Fixed paths | - | 03/06/2024 |
| MotoMingle-Squad-A-de-Software-Em/LandingPage-RentCarAssist | main | b0a64da29f4d083bd63a50e24537c1b9f359ce0b | Test | - | 03/06/2024 |
| MotoMingle-Squad-A-de-Software-Em/LandingPage-RentCarAssist | main | 52793683f37c6dd5962ebe0f62de585bf29ad692 | Merge branch 'main' of https://github.com/MotoMingle-Squad-A-de-Software-Em/LandingPage-RentCarAssist | - | 03/06/2024 |
| MotoMingle-Squad-A-de-Software-Em/LandingPage-RentCarAssist | main | 7feb148036590fc48b2c2e58d1a9965eaf43dc57 | Fixed file | - | 03/06/2024 |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop | 6d6a87679fd2c7b12590bd8db010adec97a23ed7 | Improved navbar in mycars view | - | 04/06/2024 | 
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop | 5f00a49dee90f34c340c9d1de320436ce9b76fe8 | Improved navbar in home view | - | 04/06/2024 |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop | 049a25c7e9c89abd0757c949388f0ff74e07b3ad | In the welcome component, add sign-in and sign-up | - | 03/06/2024 |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop | c91673b7a4b2514cb92a019a6cd5e27244bdbf14 | Update welcome component | - | 03/06/2024 |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop | 35aeda6a232ad1fb1f8ce540b19b8b178b30cdfa | Cleaned code | - | 03/06/2024 |

#### 7.2.1.4.	Testing Suite Evidence for Sprint Review.

#### 7.2.1.5.	Execution Evidence for Sprint Review.

#### 7.2.1.6.	Services Documentation Evidence for Sprint Review.

#### 7.2.1.7.	Software Deployment Evidence for Sprint Review.

#### 7.2.1.8.	Team Collaboration Insights during Sprint.

## 7.3.	Validation Interviews.

### 7.3.1.	Diseño de Entrevistas.

### 7.3.2.	Registro de Entrevistas.

### 7.3.3.	Evaluaciones según heurísticas.

## 7.4.	Video About-the-Product.
