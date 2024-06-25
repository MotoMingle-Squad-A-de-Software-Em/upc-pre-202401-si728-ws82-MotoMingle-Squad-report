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

| Backend | https://github.com/MotoMingle-Squad-A-de-Software-Em/Backend-RentCarAssits |
|---------|----------------------------------------------------------------------------|

| Frontend | https://github.com/MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits |
|----------|-----------------------------------------------------------------------------|

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

| Report | https://github.com/MotoMingle-Squad-A-de-Software-Em/upc-pre-202401-si728-ws82-MotoMingle-Squad-report |
|--------|--------------------------------------------------------------------------------------------------------|

| Backend | https://github.com/MotoMingle-Squad-A-de-Software-Em/Backend-RentCarAssits |
|---------|----------------------------------------------------------------------------|

| Frontend | https://github.com/MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits |
|----------|-----------------------------------------------------------------------------|

## 7.2.	Solution Implementation.

### 7.2.1.	Sprint 1

#### 7.2.1.1.	Sprint Planning 1.
En esta sección se especificarán datos importantes del Sprint Planning Meeting

| Sprint #                        | Sprint 1                          |
|---------------------------------|-----------------------------------|
| Sprint Planning Background      |                                   |
| Date                            | 2024-06-01                        |
| Time                            | 20:00 PM                          |
| Location                        | Discord                           |
| Prepared By                     | Leonardo Cesías                   |
| Attendees (to planning meeting) | Leonardo Cesías / Leonardo Aquino |
| Sprint n Velocity               | 14                                |

#### 7.2.1.2.	Sprint Backlog 1.
El objetivo de este sprint 1 es empezar a implementar el frontend, landing page y backend de nuestro proyecto. Para ello, se ha dividido en 4 bounded context que serán detallados en el siguiente cuadro.  

| Sprint #                    | Sprint 1                                                      |                  |                                                                   |                                                                           |                    |             |                                               |
|-----------------------------|---------------------------------------------------------------|------------------|-------------------------------------------------------------------|---------------------------------------------------------------------------|--------------------|-------------|-----------------------------------------------|
| User Story                  |                                                               | Work-Item / Task |                                                                   |                                                                           |                    |             |                                               |
| ID                          | Título                                                        | ID               | Título                                                            | Description                                                               | Estimation (hours) | Assigned To | Status (To/do/ In Process / To-Review / Done) |
| US043                       | Usuario administrador añade un banner principal               | TA001            | Lading Page Banner                                                | Implementar banner landing page                                           | 5                  | Cesías      | Done                                          |
| US044                       | Usuario visitante visualiza los features de la plataform      | TA001            | Landing Page Features                                             | Implementar sección features landing page                                 | 3                  | Cesías      | Done                                          |
| US045                       | Usuario visitante compara planes y precios                    | TA001            | Lading Page Planes                                                | Implementar sección de planes y precios landing page                      | 3                  | Cesías      | Done                                          |
| US046                       | Usuario visitante accede a información adicional en el footer | TA001            | Landing Page Footer                                               | Implementar sección footer lading page                                    | 3                  | Cesías      | Done                                          |
| US001                       | Usuario se registra en la aplicación con usuario y contraseña | TA001            | Formulario de Login y Register                                    | Mejorar los formularios de login y registro                               | 8                  | Aquino      | Done                                          |
| US002                       | Usuario completa su registro con sus datos personales         | TA001            | Implementar las validaciones                                      | Mejorar las validaciones en la web de los formularios de login y register | 8                  | Aquino      | Done                                          |
| US006 <br> US007 <br> US008 | Usuario se suscribe a un plan Basic, Premium, Vip             | TA001            | Mejorar planes                                                    | Mejorar la administración de los planes                                   | 8                  | Toshiro     | In Process                                    |
| US009 <br> US010 <br> US011 | Publicar, editar, eliminar anuncio de alquiler de auto.       | TA001            | Mejorar sección de alquilar auto                                  | Mejorar las vistas de publicar, eliminar y editar anuncios de autos       | 8                  | Toshiro     | In Process                                    |
| US16                        | Usuario arrendatario recibe notificaciones de sus alquileres  | TA001            | Reimplementar Twilio y mejorar las noficaciones para los usuarios | 8                                                                         | Cesías             | In Process  |

#### 7.2.1.3.	Development Evidence for Sprint Review.
En esta parte del trabajo se presenta commits realizados por los miembros del equipo durante el sprint 1.  
En primer lugar, se mostrarán la cantidad total de commits de cada integrante del equipo, incluye fix, update.

| Integrante                  | Landing Page |
|-----------------------------|--------------|
| Cesías Díaz, Leonardo Paolo | 19           |

| Integrantes                 | Web Application |
|-----------------------------|-----------------|
| Cesías Díaz, Leonardo Paolo | 37              |
| Aquino Cruz, Leonardo José  | 16              |

Se presenta la tabla de commits con mayor relevancia:  

| Repository                                                  | Branch  | Commit id                                | Commit Message                                                                                        | Commit Message Body | Commited on Date |
|-------------------------------------------------------------|---------|------------------------------------------|-------------------------------------------------------------------------------------------------------|---------------------|------------------|
| MotoMingle-Squad-A-de-Software-Em/LandingPage-RentCarAssist | main    | 86dbbc4eac6dfc008447176d12652dd5780a3f8c | Fixed paths                                                                                           | -                   | 03/06/2024       |
| MotoMingle-Squad-A-de-Software-Em/LandingPage-RentCarAssist | main    | b0a64da29f4d083bd63a50e24537c1b9f359ce0b | Test                                                                                                  | -                   | 03/06/2024       |
| MotoMingle-Squad-A-de-Software-Em/LandingPage-RentCarAssist | main    | 52793683f37c6dd5962ebe0f62de585bf29ad692 | Merge branch 'main' of https://github.com/MotoMingle-Squad-A-de-Software-Em/LandingPage-RentCarAssist | -                   | 03/06/2024       |
| MotoMingle-Squad-A-de-Software-Em/LandingPage-RentCarAssist | main    | 7feb148036590fc48b2c2e58d1a9965eaf43dc57 | Fixed file                                                                                            | -                   | 03/06/2024       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits    | develop | 6d6a87679fd2c7b12590bd8db010adec97a23ed7 | Improved navbar in mycars view                                                                        | -                   | 04/06/2024       | 
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits    | develop | 5f00a49dee90f34c340c9d1de320436ce9b76fe8 | Improved navbar in home view                                                                          | -                   | 04/06/2024       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits    | develop | 049a25c7e9c89abd0757c949388f0ff74e07b3ad | In the welcome component, add sign-in and sign-up                                                     | -                   | 03/06/2024       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits    | develop | c91673b7a4b2514cb92a019a6cd5e27244bdbf14 | Update welcome component                                                                              | -                   | 03/06/2024       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits    | develop | 35aeda6a232ad1fb1f8ce540b19b8b178b30cdfa | Cleaned code                                                                                          | -                   | 03/06/2024       |

#### 7.2.1.4.	Testing Suite Evidence for Sprint Review.
Empleando la herramienta de Gherkin, se realizó los siguientes tests.  
[![image.png](https://i.postimg.cc/59pbWkG5/image.png)](https://postimg.cc/0r6LpZ9r)

#### 7.2.1.5.	Execution Evidence for Sprint Review.
Esta sección se mostrarán imágenes de las principales vistas implementadas en el Landing Page y Web Application.  

**Landing Page:**  
Link: [https://motomingle-squad-a-de-software-em.github.io/LandingPage-RentCarAssist/](https://motomingle-squad-a-de-software-em.github.io/LandingPage-RentCarAssist/)

[![image.png](https://i.postimg.cc/Qx47CmB1/image.png)](https://postimg.cc/N5XFP1kj)  
[![image.png](https://i.postimg.cc/Cx9fHKsK/image.png)](https://postimg.cc/xXyC9n7r)

**Web Application:**  

*Login and Register:*  
[![image.png](https://i.postimg.cc/T2bNryjK/image.png)](https://postimg.cc/F19xvHBv)  
[![image.png](https://i.postimg.cc/vmjXnMc7/image.png)](https://postimg.cc/jWHzVp6C)  
[![image.png](https://i.postimg.cc/C5pNvNCz/image.png)](https://postimg.cc/phkzrK6H)  
*Sección Search Cars:*  
[![image.png](https://i.postimg.cc/RFK1ntr9/image.png)](https://postimg.cc/BLZPrXQw)  
*Sección My Cars:*  
[![image.png](https://i.postimg.cc/NjnRJDBB/image.png)](https://postimg.cc/bZQGdQZB)

#### 7.2.1.6.	Services Documentation Evidence for Sprint Review.
Para esta entrega no se considerará este punto ya que solo se ha desarrollado el lading page y el application web y no un servicio para documentarlo.

#### 7.2.1.7.	Software Deployment Evidence for Sprint Review.
Para esta entrega se ha trabajo el landing Page y la aplicación web, como también se ha desplegado en GitHub Page y Netlify respectivamente.

**Landing page:**  
[![image.png](https://i.postimg.cc/SKvqzX6Z/image.png)](https://postimg.cc/bGk47wFb)  
**Web Application:**  
[![evidence.jpg](https://i.postimg.cc/WbsdgJPn/evidence.jpg)](https://postimg.cc/nMwVtrrj)

#### 7.2.1.8.	Team Collaboration Insights during Sprint.
En este sprint la participación de los miembros del grupo fue el siguiente:  
**Landing page:**  
[![image.png](https://i.postimg.cc/T2mGp3p9/image.png)](https://postimg.cc/z3J4Q5wb)

**Web Application:**  
[![image.png](https://i.postimg.cc/zXFrF2wH/image.png)](https://postimg.cc/svxqVcN3)

### 7.2.2.	Sprint 2
En esta sección se especificarán datos importantes del Sprint Planning Meeting

| Sprint #                        | Sprint 2                          |
|---------------------------------|-----------------------------------|
| Sprint Planning Background      |                                   |
| Date                            | 2024-06-15                        |
| Time                            | 20:00 PM                          |
| Location                        | Discord                           |
| Prepared By                     | Leonardo Cesías                   |
| Attendees (to planning meeting) | Leonardo Cesías / Leonardo Aquino |
| Sprint n Velocity               | 16                                |

#### 7.2.2.2.	Sprint Backlog 2.
El objetivo de este sprint 1 es empezar a implementar el frontend, landing page y backend de nuestro proyecto. Para ello, se ha dividido en 4 bounded context que serán detallados en el siguiente cuadro.  

| Sprint #                     | Sprint 2                                                                 |                  |                                                                   |                                                                     |                    |             |                                               |
|------------------------------|--------------------------------------------------------------------------|------------------|-------------------------------------------------------------------|---------------------------------------------------------------------|--------------------|-------------|-----------------------------------------------|
| User Story                   |                                                                          | Work-Item / Task |                                                                   |                                                                     |                    |             |                                               |
| ID                           | Título                                                                   | ID               | Título                                                            | Description                                                         | Estimation (hours) | Assigned To | Status (To/do/ In Process / To-Review / Done) |
| US003                        | Usuario registrado inicia sesión con su usuario y contraseña.            | TA001            | Log in                                                            | Implementar función de iniciar sesión en la aplicación              | 1                  | Cesías      | Done                                          |
| US005                        | Como usuario quiero cerrar sesión del dispositivo en el que me encuentro | TA001            | Log out                                                           | Implementar cerrar sesión en la aplicación                          | 1                  | Cesías      | Done                                          |
| US023                        | Usuario arrendatario alquila un auto de su preferencia                   | TA001            | Chose a car to rent                                               | Implementar lista de vehiculos a rentar                             | 3                  | Cesías      | Done                                          |
| US029                        | Usuario arrendatario busca autos por ubicación y fechas                  | TA001            | Search a car by address or date                                   | Implementar funcionaidad de filtro                                  | 3                  | Cesías      | In process                                    |
| US032                        | Usuario arrendatario visualiza los requisitos para el alquiler del auto  | TA001            | Requirements for rent a car                                       | Mostrar información de los vehiculos                                | 2                  | Cesías      | Done                                          |
| IOT01                        | Herramienta IoT se comunica con el backend                               | TA001            | Iot tools working with backend                                    | Implementar IoT que funcione con el backend                         | 8                  | Cesías      | Done                                          |

#### 7.2.2.3.	Development Evidence for Sprint Review.
En esta parte del trabajo se presenta commits realizados por los miembros del equipo durante el sprint 1.  
En primer lugar, se mostrarán la cantidad total de commits de cada integrante del equipo, incluye fix, update.

| Integrante                  | Landing Page |
|-----------------------------|--------------|
| Cesías Díaz, Leonardo Paolo | 19           |

| Integrantes                 | Frontend |
|-----------------------------|----------|
| Cesías Díaz, Leonardo Paolo | 72       |
| Aquino Cruz, Leonardo José  | 4        |

| Integrantes                 | Backend |
|-----------------------------|---------|
| Cesías Díaz, Leonardo Paolo | 27      |
| Aquino Cruz, Leonardo José  | 9       |

Se presenta la tabla de commits con mayor relevancia:

| Repository                                               | Branch                          | Commit id                                | Commit Message                                                                                         | Commit Message Body         | Commited on Date |
|----------------------------------------------------------|---------------------------------|------------------------------------------|--------------------------------------------------------------------------------------------------------|-----------------------------|------------------|
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | c9996bb68fdb17421fbce9f1b097e615c269ffe6 | Added configuration view                                                                               | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | c3b4c0f6a0f04fedcd95b4973ddab95501255c81 | Added data component                                                                                   | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | e0d54e9d2adeb0003aa7b13b9c33719cd8cd51df | Updated app module                                                                                     | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | f63328eaf51b1021f908c333ef32f3986895abdc | Added routing                                                                                          | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 6f9b9db43f8ca7d82285d5a6c78cb5e6119c84cf | Added bookings view                                                                                    | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 74fadf3075c4d9514400586fc5b928741dd869b9 | Updated rent card                                                                                      | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 3df42cf9d7fdb0e953a86d275cd02510d6915bf0 | Updated sidebar                                                                                        | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 354ebcce440f4e7bd27888bc211ff0473c550ef7 | Added booking cards component                                                                          | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 498a630c464e1d7416a641f68c784f75d9c32162 | Updated routing                                                                                        | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 9b12ccebf8eb05eb102dd5fea046db754acdb50a | Fixed features                                                                                         | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | c1216448a7a00c352f19dbfa4e990c0dabb2469a | Cleaned code                                                                                           | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 89a87a4dda0293ea075aadc41c2a8d9ee53820ff | Updated car add                                                                                        | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 087a97a4c5ad19505a4a7c571736b827be9c68a6 | Updated login                                                                                          | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 68819c11141d89b5f53e11f1b8082257e9058f52 | Updated app module                                                                                     | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 092107b3fef4ecef10c1dc704b73650aac801150 | Updated car add                                                                                        | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 7cf8c8cacb39251d8035d4d95b8de6babaa80110 | Updated car data                                                                                       | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 7323d71e854606b9c12b8eac0c6a7d70b32687e1 | Updated car owner                                                                                      | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | cabb039b3d95da9c6970170503d60e6e5b86edb2 | Updated car card                                                                                       | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 150ed09f8e437db0be8d2d8e492bcde6b1fdf453 | RentCar                                                                                                | adicional para rentar carro | 2024-06-08       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 6d379d0461ab653d3d9341f10d95feb3d49970ac | Improved navbar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | d3a5716d816855e3d9f6e9375b62336e79e419ae | Fixed broken tests                                                                                     | -                           | 2024-06-01       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | fe452a4803620a5983827c706e153a37e34b4b35 | Improved navbar in home view                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | e97f69e387bf9d8d5c7022d8f2e6f727a4e3bcfa | Updated car card                                                                                       | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | aea6c61792b1f623b527c8e4d0d00c8adfefb8f5 | Added new views                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 1cb7dc3253b2a4b855efb1bdfb57f759645c9256 | Fixed booking                                                                                          | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 6f5426a5b17a0604e7f8a7d33b71b3e850441482 | Updated car card                                                                                       | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | f97ae95b4ac0a68263e693f14ffcb69c1fe8d19b | Added car owner data                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 36514cb8261f2852e5e2b18052424e17f0645e11 | Added car data                                                                                         | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 6ac1795b17d18c8d02d96b6cc307ec0e6e8f8d9f | Cleaned code                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | fe32d8f1cb9e9bb7d3a7a68c060024d145a52d85 | Updated routes                                                                                         | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a92b6f939fd0a05309e61e6f262776a674bd0ed6 | Improved navbar in profile view                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 6be165a54e26813c1553cb3834564f7d7f0ec7c5 | Added profile component                                                                                | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | b95eab6f8ea5b8827392bace153a7d4cb9c86e5d | Added profile view                                                                                     | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | d08e40ac2973c6f07ac20cbf10073d82ac85d3c7 | Updated login                                                                                          | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 35faba7d8ecff40d4201b882bba12be6b39e4fa3 | Cleaned code                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 1e2f5dfd7af8eec0e4e4e55d3c1582a9b2609c2c | Updated sidebar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 91b93c4feec0044a050e4aeb248b24696007a1f1 | Updated car add                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 38093c2444f3ef5db0d9fcbb6fc6f1fae890e9dc | Improved navbar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 202e03e2f8b2f051b9b3e17975f6b7926826fa83 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 93b8f4512907d2c6a5c22d6d24b1ea7c7b6d089d | Improved navbar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | f4091348a5c81f2be0344bdeabafaeefb18c2ba0 | Updated sidebar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 9c56fd6bcfe74611784e457fa88891d2ddc2b7f7 | Updated car owner                                                                                      | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a2226c4b14b512015fc69bda1bcf05e0f40e4fe1 | Updated profile                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | c178d73252704a89d688a6bade4a7a2531e8b033 | Updated sidebar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 35b4dbf548d44d8b7eac5314221129fc2cd1446a | Updated sidebar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 12341e16b345e243b1728c81b22c5d9d34074b58 | Updated sidebar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 2e63514e20cb0229b4c08ae07d57b0d70c962cb2 | Improved navbar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 0c5201e3cd53060a107f9d264c7a8e31cf5f7c5b | Added profile view                                                                                     | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 36720c2d5d60a640a2b71da1085b6b499e5166de | Cleaned code                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | db1172d6b0bba063fc57d7a79fc77f28e8c83d12 | Updated profile                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | d2268c991982ef86a22d6d6a2906b8b7ddcb9df9 | Updated car data                                                                                       | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | e1bfb68a7f5390d1aef81a9dd5856d9dce13c830 | Updated profile                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a7cb2446d91f46dfb14584f3b0cfaf36b020f35b | Cleaned code                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 907e8bcff8458c13d51d526125ff6c27b7bc2c1f | Updated profile                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | f4f7a17ff7f5305731a2a01ab21e0e1e5f2a9493 | Updated home                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 201d3a5ab199ca0c78d20fe43c8b920967c3016d | Updated sidebar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | c4c0b0ecff47ea1060a3b3c6372e7a2cf2efba7a | Updated sidebar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 45c645be85e3e5a4f4155d060e3677158a7f4bdb | Cleaned code                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 74f85cc8ffb999ac8081a3cda42192d16e394fa7 | Updated profile                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 0a7583e49e9244d9a0537d71fd759bf76a7f2820 | Updated sidebar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 7a1d3ed83c43237f3d2bb7308c03f12625165b36 | Added car owner data                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 298e4ad2e258ef37e12ee3e9ab8b683f15c4a11c | Updated routes                                                                                         | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 478c4734c9b580239503cd7e0862f281b16ec11c | Added profile                                                                                          | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | c03024f1c6db3c2ab39a41f1cf9b4e44927a2805 | Updated routes                                                                                         | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 697d81b4cd70247d8e4c2ff68286dd7f106c94f5 | Updated routes                                                                                         | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 95b72cb823fce7c9f9fcf09d94c171d1ab0843a2 | Updated home                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 7e6c0d978b53068af8b9a0a9f30d9407c14af2bb | Updated sidebar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 59875e8db963a58922de30c2790b1599d70910a2 | Added car data                                                                                         | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 6485c0b4b274ed84b38c1e3cf51e2e9e99170a0d | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 568301e2df97e8a58c5cf620d33b6dc1bcb54b35 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 6e41c0134d6c9d604e4451b65d244f35d580febb | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 5ef2c9a04dcf97e8a20b567cb7a6a1b476e92a95 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a61b1dd87a78cd5d589b3b101f04f8351f5b63fc | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | e330ce7cc4c7d9202c1e967b94790e6e647cf6cf | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 938e929b1bdc8c018b2a3d1239c620e198b62091 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | f5d0c622ae0cb42d64771d3b7b800c0d79edca26 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a0e2d53b36e4c283edfbf35bcfdc391d5941a089 | Added car data                                                                                         | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 3085e3f3d7f0c7e0ed9259827fdd8e4b0c924c56 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 2311ad0eb0f3484a50d2a3093d62bdb17824427a | Added profile component                                                                                | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 230764d0d9fc472bdc524ed94a7c38fe6f4b5a9d | Improved navbar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a062ecaf7bb370d4b95a3c9b278a76ac9a59d14a | Added profile view                                                                                     | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | e31252b658dc50a7d0ef4e5ff3b1d72a8074e1b8 | Updated profile                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 6ff1b8b042f9cbe43b8e67e4fa12760e2ebcfe5f | Updated sidebar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a83e78142d229ca0e3fcbe2f54e8af2716a882e0 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 2bdbfb0c4e7b9eb505ad5b48a3f2d2e23d7267af | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | b1c316f9f0d3c25b4725c2801ee594b057279245 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 2259e194da3448f4e99c7f2c5e12b7c9d3150d7e | Improved navbar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | dca0feadbf66e8b00f6a9a8243ff92ef83aa98f1 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 2e9245b3530d61c004eb8010309c787329dbf849 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 9df6b3f15fe2de0f6ec9c3a6bff65a4b7cbabbd0 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 6d60c67578c9ed178fda780a94e8c66092b36a7a | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | e41d72fce7651d3f874f8fdc3138de69c235a0c5 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 2e5c69fc7f7ad26e5e666f93efcddbdd6507d898 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 23f5d108b226a78b536f803c471eb74c7f62e8ad | Updated routes                                                                                         | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 75e5b69d9bc1c3ae4e6d8707a2a7d383f4cb6da4 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 6fc5920c5942c326cc4b9798c9402238c6e2b872 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 2721b0d0f530cbce61592d8afbd9c528f5df5b17 | Updated routes                                                                                         | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 9720c7fcb5f121af2b37d367b55ef7d0b10c2a99 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 6c348b2b13d795468f65ee55b4d5f5d3f2e14eb8 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 8124bc37314df2d10c196d8b7900e1c86c69aa24 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | e364fa3e68cf26ed37c20b7ecfbb0a2fdcdb9e05 | Updated routes                                                                                         | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 4c92542f7e0c8d50b7e3ccf68000c702ace59b57 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 8afaba17ac6b7fb5d18dc2cbdc94eae1e2a392b8 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 5cd2f57d79d06f0f5001cbcb7e7524fdfc388cc0 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 8a1ccf212e50a7b2e8b7f63e70237b185c0d1f18 | Updated sidebar                                                                                        | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 94f36d6b4b7bfa2b7e8bff3c0d66324cbf2b33e1 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a81bdefe62bb52475fcbfb60cbd9640862c5033c | Updated routes                                                                                         | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | c3510f5053216fe800334b8b36ed39dfe2021b68 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 9512b16351f3eaf64dfb4523f4560845d3998dff | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a36dcf658b514f5ad3f24e5e3748e5db80e20a7b | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | f9a805fc242aebde1e9ad8f43879f3b74bfcf56c | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 87d0033b48c1c748a683ce9c08427d791e6d66e8 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 1e98e62b2ec38120b6fa1e5e16c9706728ddcf2b | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a263bdb4a56b93a4d2870a558c8534b95ff99734 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 7a1e616c499d1d7bb6a2a9269daab668d97da76e | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a00dd73db305d35a1dd3507eeb20699be9365675 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | d6d95085e43e295d2646b5a0c991027c1ab4c46b | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 16eeb1f7ffdf7c7ab0ab2fa7c1103175d30d7a36 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 9fdd4bdb92a78973a768ea2096662c3e6d69b40e | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | d92d60728d3222fa18efae78e08d0603cf96b63b | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 02b9649ab5195b65ae5542a360b295e071b55e30 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 39248c9a351ed368b56fe8ac7f88e5b026db1b52 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 1afbd028ff3a76fcbcd4b2a742e0eab17c663e79 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | f1b0276beeb989107680e2a92a8f408a927bd5af | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | feccdb005019e8ba1080d14a991a429d94658c5c | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | f22655fe79e110c2972e8f4f6a8ef526b34dcb5b | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | e47787f44a77c9e0314982185f7fd6eb5f13b1e1 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | f91803ce7266e72af8dd4b468fc98d5b231d291d | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a4b45f9c93f65ffb8b88cf39dc9f6ff6b9efb924 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 7d66fa8ab151fcfbc6b8fef4be9a2d3271191303 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | c545d5e8e4df2c75dc2071a4f5ef1b7cb6e5ff4c | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 18a616520ae279d0d6f3fc6f9e390a07d27df5a4 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | fe8cce203eacc09f75f27d44e39a5e97ecdbadd9 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 41f9efcc7c49ed29912b8cba1234ffb9423d32c0 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 92ecdf2783f88ef4a1481ce1b32a96d0f7b5c90f | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | e1b5f02a4d8c147579a383c9e4192d49cf5bb928 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 0b37b34252b99f8494e07c896fb7d682ffad1949 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 8d3b57269b738b26b04c6fc5ce27dd071d94e408 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a2e4254cb2b17f2f68e0e0f05f98a46f9f15d349 | Updated routes                                                                                         | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 9e46c625e7e7e7c3f5d0b9d4180a243ceec95a0e | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 88dc23b7645b7a050f56c3f6ce78eb6803ea55d0 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | e40a4e46bb80992d5e5686a06bdf7f1cb469351e | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 159c1464cb307a3a3d59097fd7da6e3629db9f00 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 953bde6018482e1226e5025e11a8444ff0b2a450 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 1e35a05b830fffb7de22864957b5b1e351cf9d6c | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 63af7ffce4ddff6125ba31235b7b3cb20e49b8b2 | Updated routes                                                                                         | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 02c8b5b02fa5f0a4b4b6f30e3df1b2c4ffb7fc19 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | fbdfeb15b6b3da4f207b88e7ae2e7388d3be3b41 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | e8b9b871408601908682c3dd6b83e9c623da5fc5 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 1196de74530628c8a217d7878e617c8d63e1314d | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 70ac2533eebbe17e03b33d84cf54d16b216cd0e6 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 5a097d7764e0621aebda40b287cd5247e16ad138 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 6a7a88b231a157ef27898e9ce445276a53cf11b5 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | e5025cfbdd69a2cb8ad09b39c6d318be25c9b31a | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 451d2a97064892b21798d50b20534a438c147abe | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a30b7121cbdcb2b972787d6e35fd38ab49da8b78 | Updated routes                                                                                         | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 3740a62028809b15e77d9e597b38d3b6d67ef417 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 87a6030cd03173c0ee89a4a37b6d8fa2dcb9878f | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a9b8331c172ff502d84c4a7dd5b19350a3f4e0a0 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 4fc0ff3c8425ea51914e20e2a6bb655d8fe06f9d | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | c3e77eab21ecf41ae024e63d42e72af1d16d05e1 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 1ae0f72ff8f603a6d0e8cbe6b2e669b4c0637c8d | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | e050c9b1dbd1d67be5d53bb93029da34f27b0b6a | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 4c8a2f1e8b730d6fa6a5f4b7fa6ec0a13a4c13c6 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | a8f10f8b788a7bb4a285b96ff90e05f03d9c8654 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 15ebbb6a0ac26b594ed4af7e462d21d5e593774e | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 67c85061fa2e0f5da470adfd00a4e5c258e3565b | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | b4cf06b367d99aa42dd3202d6784850c19c7120c | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | b90ac0c4f4bfc1f287bf3aab799374d1251cf9c4 | Added routes                                                                                           | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | e297279a72ee674ac91ce59cf59b6b66379a1c70 | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 1246d5f861a1e0e2887e015e7df13d0504a9cb8f | Added home component                                                                                   | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | 6a3905b609d74de13f7dc9bbba760ceebec17de7 | Updated routes                                                                                         | -                           | 2024-06-04       |
| MotoMingle-Squad-A-de-Software-Em/Frontend-RentCarAssits | develop                         | c9996bb68fdb17421fbce9f1b097e615c269ffe6 | Added configuration view                                                                               | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em                        | master                          | ef37d2a4d917914dfebe77e429488bd4e93a52d9 | Merge pull request #4 from MotoMingle-Squad-A-de-Software-Em/develop<br>Update User                    | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em                        | develop                         | 0919f2421187dab242a6cc0c6f10f9e1eac32aec | Update User                                                                                            | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em                        | master                          | b158f87a69aa92f8405a5734267cb10f27a5cf0a | Merge pull request #3 from MotoMingle-Squad-A-de-Software-Em/develop<br>Add configuration for deployed | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em                        | develop                         | 951330b0ecc12629081cf6cf0560815496e39e77 | Add configuration for deployed                                                                         | -                           | 2024-06-24       |
| MotoMingle-Squad-A-de-Software-Em                        | feature/booking                 | 6df9840f2a6e413edcd249083fedbe1a5296a157 | Added Booking Controller                                                                               | -                           | 2024-06-21       |
| MotoMingle-Squad-A-de-Software-Em                        | feature/vehicles                | 571d96351948f8f20ad4efcfe2b35f12ac905871 | Added VehicleController                                                                                | -                           | 2024-06-16       |
| MotoMingle-Squad-A-de-Software-Em                        | feature/subscription-management | bbf2314c1bd286c42dafb9f7e9c5ebe0f8ff3f32 | Add Subscription                                                                                       | -                           | 2024-06-13       |
| MotoMingle-Squad-A-de-Software-Em                        | feature/iam-management          | 1487cf7bed25d8de5c96969be45c6802fadfddbc | Add User                                                                                               | -                           | 2024-05-29       |

Esto incluye todos los commits con su mensaje y la fecha de commit correspondiente.

#### 7.2.2.4.	Testing Suite Evidence for Sprint Review.
Empleando la herramienta de Gherkin, se realizó los siguientes tests.  
[![image.png](https://i.postimg.cc/59pbWkG5/image.png)](https://postimg.cc/0r6LpZ9r)

#### 7.2.2.5.	Execution Evidence for Sprint Review.
Esta sección se mostrarán imágenes de las principales vistas implementadas en el Landing Page y Web Application.

**Landing Page:**  
Link: [https://motomingle-squad-a-de-software-em.github.io/LandingPage-RentCarAssist/](https://motomingle-squad-a-de-software-em.github.io/LandingPage-RentCarAssist/)

[![image.png](https://i.postimg.cc/Qx47CmB1/image.png)](https://postimg.cc/N5XFP1kj)  
[![image.png](https://i.postimg.cc/Cx9fHKsK/image.png)](https://postimg.cc/xXyC9n7r)

**Web Application:**

*Login and Register:*  
[![image.png](https://i.postimg.cc/T2bNryjK/image.png)](https://postimg.cc/F19xvHBv)  
[![image.png](https://i.postimg.cc/vmjXnMc7/image.png)](https://postimg.cc/jWHzVp6C)  
[![image.png](https://i.postimg.cc/C5pNvNCz/image.png)](https://postimg.cc/phkzrK6H)  
*Sección Search Cars:*  
[![image.png](https://i.postimg.cc/RFK1ntr9/image.png)](https://postimg.cc/BLZPrXQw)  
*Sección My Cars:*  
[![image.png](https://i.postimg.cc/NjnRJDBB/image.png)](https://postimg.cc/bZQGdQZB)

#### 7.2.2.6.	Services Documentation Evidence for Sprint Review.
Para esta entrega no se considerará este punto ya que solo se ha desarrollado el lading page y el application web y no un servicio para documentarlo.

#### 7.2.2.7.	Software Deployment Evidence for Sprint Review.
Para esta entrega se ha trabajo el landing Page y la aplicación web, como también se ha desplegado en GitHub Page y Netlify respectivamente.

**Landing page:**  
[![image.png](https://i.postimg.cc/SKvqzX6Z/image.png)](https://postimg.cc/bGk47wFb)  
**Web Application:**  
[![evidence.jpg](https://i.postimg.cc/WbsdgJPn/evidence.jpg)](https://postimg.cc/nMwVtrrj)

#### 7.2.2.8.	Team Collaboration Insights during Sprint.
En este sprint la participación de los miembros del grupo fue el siguiente:  
**Landing page:**  
[![image.png](https://i.postimg.cc/T2mGp3p9/image.png)](https://postimg.cc/z3J4Q5wb)

**Web Application:**  
[![image.png](https://i.postimg.cc/zXFrF2wH/image.png)](https://postimg.cc/svxqVcN3)

## 7.3.	Validation Interviews.

### 7.3.1.	Diseño de Entrevistas.

### 7.3.2.	Registro de Entrevistas.

### 7.3.3.	Evaluaciones según heurísticas.

## 7.4.	Video About-the-Product.
