# Capítulo V: Tactical-Level Software Design.
## 5.1. Bounded Context: Renting Management
El dominio de Renting Management se centra en la gestión y coordinación de todas las actividades relacionadas con el alquiler de vehículos en el sistema Rent Car Assist. Este dominio es responsable de manejar las interacciones entre arrendadores, arrendatarios y mecánicos, así como de garantizar que las reglas de negocio específicas para el alquiler de vehículos se apliquen de manera adecuada.

**Diccionario de Clases:**  
El Diccionario de Clases es una herramienta importante en el proceso de diseño y desarrollo de nuestra plataforma de alquiler de automóviles, ya que proporciona una descripción detallada de las clases clave que forman la base del modelo de dominio del sistema. Este diccionario documenta las entidades y sus relaciones, atributos y comportamientos, lo que facilita la comunicación y la colaboración entre los miembros del equipo y garantiza una base sólida para nuestra solución de alquiler de vehículos.

En el Diccionario de Clases, hemos incluido cuatro clases principales: Rental, Vehicle, RentOrder y RentOffer. Estas clases representan los elementos esenciales de nuestra plataforma y definen las entidades y relaciones que permiten a los usuarios alquilar vehículos, gestionar órdenes de alquiler y publicar ofertas de alquiler.

[![image.png](https://i.postimg.cc/P5fBhXsK/image.png)](https://postimg.cc/QHP6JrMW)
[![image.png](https://i.postimg.cc/RZbbBwTV/image.png)](https://postimg.cc/750N1Gcp)
[![image.png](https://i.postimg.cc/tJ2NzHSC/image.png)](https://postimg.cc/RJJtM2xj)
[![image.png](https://i.postimg.cc/BQngnXb8/image.png)](https://postimg.cc/0rhmt5px)

### 5.1.1. Domain Layer.
Dentro del dominio de Renting Management, se encuentran entidades clave como Rental, Owner, Renter y Vehicle. Estas entidades desempeñan un papel fundamental en el proceso de alquiler, ya que permiten a los usuarios buscar, reservar y gestionar alquileres de vehículos de manera eficiente. 
En el caso de Renting Management, RentOrder es el agregado principal porque encapsula la lógica de negocio central relacionada con el proceso de alquiler de vehículos. RentOffer y RentingServiceOrder.

A continuación, se muestra todos los objetos relacionados con el dominio.  
[![image.png](https://i.postimg.cc/3xD2kpTw/image.png)](https://postimg.cc/LJ2J7Jhd)

### 5.1.2. Interface Layer.
En esta sección, presentamos la Capa de Interfaz de nuestra plataforma de alquiler de automóviles, que representa el punto de entrada para las interacciones entre los usuarios y el sistema. La Capa de Interfaz está compuesta por una serie de controladores que manejan las peticiones entrantes de los usuarios y devuelven las respuestas adecuadas, permitiendo una comunicación efectiva entre la plataforma y sus usuarios.

El contexto de esta capa incluye cuatro controladores principales: **RentalOrderController**, **VehicleController**, **PostRentingController** y **RentOfferController**. Estos controladores tienen la responsabilidad de gestionar las operaciones relacionadas con órdenes de alquiler, vehículos, publicación de alquileres y ofertas de alquiler, respectivamente.  
**RentalOrderController:** Este controlador se encarga de gestionar todas las acciones relacionadas con las órdenes de alquiler, como la creación de nuevas órdenes, la actualización de órdenes existentes y la consulta de órdenes por parte de arrendadores y arrendatarios.

**VehicleController:** Este controlador se encarga de gestionar las operaciones relacionadas con los vehículos disponibles en la plataforma, como la adición de nuevos vehículos, la actualización de la información del vehículo y la búsqueda de vehículos según criterios específicos.

**RentOfferController:** Este controlador se encarga de gestionar las acciones relacionadas con el proceso posterior al alquiler de vehículos. Después de que finaliza un alquiler, el PostRentingController se encarga de actualizar el estado del alquiler, del vehículo y de la orden correspondiente. Además, se encarga de notificar a los usuarios involucrados en la renta, como el arrendador y el arrendatario, sobre el estado actualizado y cualquier información relevante. Esto permite a los usuarios estar al tanto de las actualizaciones importantes y garantiza una transición sin problemas al final del alquiler.  
[![image.png](https://i.postimg.cc/NFMHB2DB/image.png)](https://postimg.cc/xJwCPCB4)

### 5.1.3. Application Layer.
En esta sección, presentamos la Capa de Aplicación (Application Layer) dentro del contexto del enfoque de diseño Domain-Driven Design (DDD) para nuestra plataforma de alquiler de automóviles. La Capa de Aplicación es responsable de coordinar las acciones y el flujo de datos entre la Capa de Dominio y la Capa de Infraestructura, actuando como intermediario y gestionando las interacciones entre estas capas. Esta capa es crucial para garantizar que la lógica de negocio, representada por la Capa de Dominio, se ejecute de manera eficiente y coherente.

La Capa de Aplicación se compone de servicios de aplicación, Command Handlers y Event Handlers. Los Command Handlers gestionan las operaciones de escritura en la plataforma, como **CreateRentCommandHandler**, que se encarga de crear nuevas solicitudes de alquiler; **UpdateOfferCommandHandler**, que actualiza la información de las ofertas de alquiler; **CreateOrderCommandHandler**, que crea nuevas órdenes de alquiler; **CreateVehicleCommandHandler**, que registra nuevos vehículos en la plataforma; y **UpdateCommandHandler**, que administra la actualización de información en general.

Por otro lado, los Event Handlers se encargan de manejar eventos del sistema, como **VehicleLocationEvent**, que rastrea y actualiza la ubicación de los vehículos en tiempo real; **UserNotificationEvent**, que se encarga de notificar a los usuarios sobre cambios relevantes en la plataforma, como actualizaciones de estado o confirmaciones de reserva; y **VehicleStatusEvent**, que monitorea y actualiza el estado de los vehículos, como su disponibilidad o si requieren mantenimiento.  
[![image.png](https://i.postimg.cc/qRBtx69y/image.png)](https://postimg.cc/94SFW0XQ)

### 5.1.4. Infrastructure Layer.
En esta sección, presentamos la Capa de Infraestructura (Infrastructure Layer) dentro del contexto del enfoque de diseño Domain-Driven Design (DDD) para nuestra el bounded context **Renting Management**. La Capa de Infraestructura es responsable de proporcionar los componentes técnicos y de soporte necesarios para que las otras capas del sistema funcionen correctamente. Esta capa incluye la implementación de repositorios, servicios que se conectan con sistemas externos y otros componentes de infraestructura.

Los repositorios en la Capa de Infraestructura implementan las interfaces definidas en la Capa de Dominio y se encargan de la persistencia y gestión de datos. En nuestra plataforma, utilizamos repositorios basados en JPA (Java Persistence API) para manejar la interacción con la base de datos. Entre los repositorios clave se encuentran **VehicleRepository**, que gestiona la información y disponibilidad de los vehículos; **OrderRepository**, que administra las órdenes de alquiler; y **OfferRepository**, que se encarga de las ofertas de alquiler publicadas por los arrendadores.

Además, la Capa de Infraestructura incluye servicios que interactúan con sistemas externos y proporcionan funcionalidades adicionales para la plataforma. El **EmailService** es un ejemplo de esto, ya que facilita el envío de correos electrónicos a los usuarios para notificaciones, confirmaciones de reserva y otros propósitos. Otro servicio importante es **LocationServiceImpl**, que se encarga de obtener y actualizar la información de ubicación de los vehículos en tiempo real mediante la integración con un servicio de geolocalización externo.  
[![image.png](https://i.postimg.cc/dVMLSxbq/image.png)](https://postimg.cc/4m5fYB4M)

### 5.1.6. Bounded Context Software Architecture Component Level Diagrams.
En esta sección, presentamos los Diagramas de Componentes a nivel de Arquitectura de Software del bounded Context **Renting Management** para nuestra plataforma de alquiler de automóviles. Estos diagramas proporcionan una visión detallada de cómo los diferentes componentes del sistema interactúan entre sí en el contexto de aplicaciones web y móviles. Al analizar estos diagramas, podemos obtener una comprensión clara de cómo la plataforma funciona desde un punto de vista arquitectónico y cómo los componentes se comunican entre sí.

Las aplicaciones web y móviles interactúan con el sistema a través de una serie de controladores, que gestionan las peticiones entrantes y proporcionan las respuestas adecuadas. Los controladores clave en nuestra plataforma incluyen **VehicleController**, **RentalOrderController**, **PostRentingController** y **RentOfferController**. Estos controladores manejan las operaciones (lectura y escritura) relacionadas con vehículos, órdenes de alquiler, publicación de alquileres y ofertas de alquiler, respectivamente.

Cada controlador interactúa con sus respectivos servicios y repositorios para realizar las operaciones requeridas. Los servicios implementan la lógica de negocio y coordinan las acciones entre los repositorios y otros componentes del sistema. Los repositorios, por otro lado, se encargan de la persistencia y gestión de datos, interactuando con la base de datos y, en algunos casos, con servicios externos.

Además, el sistema puede interactuar con servicios externos para obtener información adicional o realizar acciones específicas, como el servicio de geolocalización o el envío de correos electrónicos.  
[![image.png](https://i.postimg.cc/dVKV9TC3/image.png)](https://postimg.cc/WhXVNzXc)

### 5.1.7. Bounded Context Software Architecture Code Level Diagrams.
Estos diagramas proporcionan una visión detallada de cómo los diferentes componentes del sistema interactúan entre sí a nivel de código, enfocándose específicamente en la conexión e integración de servicios externos como Twilio y Mapbox.

El EmailService es un componente clave en nuestra plataforma, encargado de enviar correos electrónicos a los usuarios para notificaciones, confirmaciones de reserva y otros propósitos. Para lograr esto, el EmailService se conecta con Twilio, un servicio de comunicaciones en la nube que proporciona una API para enviar correos electrónicos de forma eficiente y segura. El diagrama de código muestra cómo el EmailService se comunica con Twilio a través de su API, enviando mensajes de correo electrónico a medida que se requieran en el sistema.

Otro componente importante en nuestra plataforma es el LocationService, que se encarga de obtener y actualizar la información de ubicación de los vehículos en tiempo real. Para lograr esto, el LocationService se integra con Mapbox, un proveedor de servicios de geolocalización y mapas. El diagrama de código muestra cómo el LocationService interactúa con la API de Mapbox para recuperar la información de ubicación actual de los vehículos y actualizarla en el sistema según sea necesario.  
[![image.png](https://i.postimg.cc/nLFVyb0t/image.png)](https://postimg.cc/cvzN3zpD)
[![image.png](https://i.postimg.cc/zB3zfCst/image.png)](https://postimg.cc/bDccCtNk)

#### 5.1.7.1. Bounded Context Domain Layer Class Diagrams.
Estos diagramas, específicamente modelan la capa de dominio dentro de un bounded context particular en DDD. Estos diagramas están diseñados para proporcionar una vista estructurada del modelo de dominio y cómo se organiza y se relaciona dentro de los límites del contexto delimitado. Son herramientas valiosas para asegurar que el equipo de desarrollo tenga una comprensión común y precisa de cómo se implementará la lógica de negocio en el código, y cómo cada parte del dominio interactúa dentro del contexto acotado.  
[![image.png](https://i.postimg.cc/L51mtH6j/image.png)](https://postimg.cc/8fT8DgvC)

#### 5.1.7.2. Bounded Context Database Design Diagram.
Es una representación gráfica que muestra cómo se organiza la base de datos en relación con un "Bounded Context" en el Diseño Guiado por el Dominio (DDD). Este tipo de diagrama se enfoca en los aspectos de almacenamiento de datos de un modelo de dominio particular y cómo los datos son estructurados y manejados dentro de los límites de un contexto específico.  
[![image.png](https://i.postimg.cc/SjbkVwJ3/image.png)](https://postimg.cc/D469wpQP)

## 5.2. Bounded Context: Billing Management
### 5.2.1. Domain Layer.
### 5.2.2. Interface Layer.
### 5.2.3. Application Layer.
### 5.2.4. Infrastructure Layer.
### 5.2.6. Bounded Context Software Architecture Component Level Diagrams.
### 5.2.7. Bounded Context Software Architecture Code Level Diagrams.
#### 5.2.7.1. Bounded Context Domain Layer Class Diagrams.
#### 5.2.7.2. Bounded Context Database Design Diagram.

## 5.3. Bounded Context: Workshop Management
### 5.3.1. Domain Layer.
### 5.3.2. Interface Layer.
### 5.3.3. Application Layer.
### 5.3.4. Infrastructure Layer.
### 5.3.6. Bounded Context Software Architecture Component Level Diagrams.
### 5.3.7. Bounded Context Software Architecture Code Level Diagrams.
#### 5.3.7.1. Bounded Context Domain Layer Class Diagrams.
#### 5.3.7.2. Bounded Context Database Design Diagram.

## 5.4. Bounded Context: Subscription Management
### 5.4.1. Domain Layer.
### 5.4.2. Interface Layer.
### 5.4.3. Application Layer.
### 5.4.4. Infrastructure Layer.
### 5.4.6. Bounded Context Software Architecture Component Level Diagrams.
### 5.4.7. Bounded Context Software Architecture Code Level Diagrams.
#### 5.4.7.1. Bounded Context Domain Layer Class Diagrams.
#### 5.4.7.2. Bounded Context Database Design Diagram.
