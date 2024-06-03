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
El dominio de Billing Management se centra en la gestión de todo lo relacionado al proceso de facturación en el sistema de Rent Car Assist. Este dominio es responsable de manejar la gestión y notificación de los comprobantes de los usuarios, así como garantizar que las reglas de negocio específicas para el proceso de facturación se apliquen de manera adecuada.

**Diccionario de Clases:**  
En el Diccionario de Clases, hemos incluido 2 clases principales: Invoice y Payement. Estas clases representan los elementos esenciales de nuestra plataforma y definen las entidades y relaciones que permiten a los usuarios realizar el pago de las facturas, generación de facturas y recibir las notificaciones  
[![image.png](https://i.postimg.cc/hjzkhVj8/image.png)](https://postimg.cc/JD862Djt)
[![image.png](https://i.postimg.cc/dVsgrb3V/image.png)](https://postimg.cc/KRW9yst6)

### 5.2.1. Domain Layer.
Dentro del dominio de Billing Management, se encuentran entidades clave como Invoice y Payment. Estas entidades desempeñan un papel fundamental en el proceso de facturación, ya que permiten a los usuarios generar su comprobante y poder realizar los pagos de los servicios de manera eficiente.

En el caso de Billing management, Billing es el agregado principal porque encapsula la lógica tanto de Invoice y de Payment para poder realizar el proceso principal de facturación.

A continuación, se muestra todos los objetos relacionados con el dominio.  
[![image.png](https://i.postimg.cc/zf3MPTnm/image.png)](https://postimg.cc/CZTmRBPJ)

### 5.2.2. Interface Layer.
La interface layer del bounded context del billing management es una parte escencial del sistema, ya que es la capa que permite la comunicación entre los diferentes componentes de la aplicación. Se encarga de manejar todas las solicitudes relacionadas con la facturación de los clientes. Esto incluye la creación de facturas, envió de facturas y pago de las facturas. 

A continuación, se muestra los controllers identificados:  
[![image.png](https://i.postimg.cc/wTHrYChQ/image.png)](https://postimg.cc/pyGCD1cm)

### 5.2.3. Application Layer.
En esta sección, presentamos la Capa de Aplicación (Application Layer) dentro del contexto del enfoque de diseño Domain-Driven Desing(DDD) para nuestra plataforma de alquileres de automóviles. La Capa de Aplicación es responsable de coordinar las acciones y el flujo de datos entre la Capa de Dominio y la Capa de Infraestructura, actuando como intermediario y gestionando las interacciones entre estas capas. Esta capa es crucial para garantizar que la lógica de negocio, representada por la Capa de Dominio, se ejecute de manera eficiente y coherente.

La Capa de Aplicación se compone de servicios de aplicación, Command Handlers y Event Handlers. Los Command Handlers gestionan las operaciones de escritura en la plataforma, PayInvoiceCommandHandler, que es aquel que se encarga de gestionar la información de las facturas y así poder crear un registro de pago, asimismo se encargara de actualizar la factura según sea reflejado el estado actual del pago.

Por otro lado, los Event Handlers se encargan de manejar eventos del sistema, como NotificationEvent, que se encarga de enviar las notificaciones según sea el estado del payment. PaymentStatusEvent, que se encarga de actualizar el Status del Payment si el pago ha sido realizado y notificar al Invoice del cambio. InvoiceStatusEvent que se encargara de actualizar el Status del Invoice según el estado que pueda tener el Payment.  
[![image.png](https://i.postimg.cc/Nf4zsdDq/image.png)](https://postimg.cc/56X3pqDn)

### 5.2.4. Infrastructure Layer.
En esta sección, presentamos la Capa de Infraestructura (Infrastructure Layer) dentro del contexto del enfoque de diseño Domain-Driven Design (DDD) para nuestra el bounded context **Billing Management**. La Capa de Infraestructura es responsable de proporcionar los componentes técnicos y de soporte necesarios para que las otras capas del sistema funcionen correctamente. Esta capa incluye la implementación de repositorios, servicios que se conectan con sistemas externos y otros componentes de infraestructura.

Los repositorios en la Capa de Infraestructura implementan las interfaces definidas en la Capa de Dominio y se encargan de la persistencia y gestión de datos. En nuestra plataforma, utilizamos repositorios basados en JPA (Java Persistence API) para manejar la interacción con la base de datos. Entre los repositorios clave se encuentran **InvoiceRepository**, que gestiona la información de las facturas generadas por el sistema; **PaymentRepository**, que se encarga de la gestión de los pagos recibidos por las facturas generadas por el sistema; y **NotificationRepository**, que se encarga de gestionar las notificaciones enviadas a los clientes con relación a sus facturas y pagos.

Además, la Capa de Infraestructura incluye servicios que interactúan con sistemas externos y proporcionan funcionalidades adicionales para la plataforma. El **NiubizAPIClient** es un ejemplo de esto, ya que nos facilitara la realización de pagos dentro de nuestra web page y mobile app.  
[![image.png](https://i.postimg.cc/fyvBbbxj/image.png)](https://postimg.cc/YLh1nMDh)

### 5.2.6. Bounded Context Software Architecture Component Level Diagrams.
En esta sección, presentamos los Diagramas de Componentes a nivel de Arquitectura de Software del bounded Context **Billing Management** para nuestra plataforma de alquiler de automóviles. Estos diagramas proporcionan una visión detallada de cómo los diferentes componentes del sistema interactúan entre sí en el contexto de aplicaciones web y móviles. Al analizar estos diagramas, podemos obtener una comprensión clara de cómo la plataforma funciona desde un punto de vista arquitectónico y cómo los componentes se comunican entre sí.

Las aplicaciones web y móviles interactúan con el sistema a través de una serie de controladores, que gestionan las peticiones entrantes y proporcionan las respuestas adecuadas. Los controladores y consumer clave en nuestra plataforma incluyen **InvoiceController**, **NotificationConsumer** y **PaymentController**. Estos controladores manejan las operaciones (lectura y escritura) relacionadas con facturación, notificaciones y pagos del alquiler.

Además, el sistema puede interactuar con servicios externos para obtener información adicional o realizar acciones específicas, como el servicio de Niubuz.  
[![image.png](https://i.postimg.cc/xTt6Dcj9/image.png)](https://postimg.cc/D84r1fbN)

### 5.2.7. Bounded Context Software Architecture Code Level Diagrams.
Estos diagramas proporcionan una visión detallada de cómo los diferentes componentes del sistema interactúan entre sí a nivel de código, enfocándose específicamente en la conexión e integración del servicio externo Niubiz.

El InvoiceService se encarga de gestionar las operaciones relacionadas con la facturación, incluyendo la creación y envío de facturas, seguimiento de pagos y generación de informes financieros.

El PaymentService se encarga de gestionar las operaciones de pago, incluyendo la comunicación con el servicio de pago en línea utilizado por la aplicación.

El NubizServiceFacade se encarga de proporcionar una interfaz para que otros componentes de la aplicación puedan acceder a los servicios proporcionados por Nubiz, un proveedor externo de servicios financieros.  
[![image.png](https://i.postimg.cc/1tGKWzYh/image.png)](https://postimg.cc/62QRqBXY)
[![image.png](https://i.postimg.cc/KjmDCydK/image.png)](https://postimg.cc/621ZGF6w)
[![image.png](https://i.postimg.cc/ZnjxSMSw/image.png)](https://postimg.cc/fSt975kd)

#### 5.2.7.1. Bounded Context Domain Layer Class Diagrams.
El Bounded Context Domain Layer Class Diagrams del bounded context del **Billing management** representa los diagramas de clases para los diferentes componentes del dominio, incluyendo Invoice, Payment, Billing y Notification. Estos diagramas muestran cómo se modela la funcionalidad en el dominio del negocio, y cómo las diferentes clases interactúan para cumplir con las necesidades del negocio. Cada diagrama de clase muestra los atributos y métodos relevantes.  
[![image.png](https://i.postimg.cc/Gm6JdDWn/image.png)](https://postimg.cc/21FBx1j0)

#### 5.2.7.2. Bounded Context Database Design Diagram.
El bounded Context Database Design Diagram del bounded context del Billing Management describe la estructura de datos y las relaciones entre ellas. En este caso, las cinco tablas incluyen Informacion sobre los renters y los owners. Las tablas están conectadas de manera que se registra quién está siendo facturado, qué facturas han sido pagadas y qué facturas están incluidas en el ciclo de facturación actual.  
[![image.png](https://i.postimg.cc/63fdrmyB/image.png)](https://postimg.cc/47n7Zw60)

## 5.3. Bounded Context: Workshop Management
El dominio de WorkShop Management se centra en la gestión y coordinación de todas las actividades relacionadas con el mantenimiento de los vehículos en el sistema Rent Car Assist. Este dominio es responsable de manejar las interacciones entre mecánicos y los dueños de los vehículos.

**Diccionario de Clases:**  
Para el presente trabajo se tuvo en cuenta las principales clases de las que se hace uso y que pertenecen al WorkShop. Para esto nuestro diccionario de clases es el siguiente:  
[![image.png](https://i.postimg.cc/GpkYR5Pv/image.png)](https://postimg.cc/Z950FjMq)
[![image.png](https://i.postimg.cc/PJq8mfgM/image.png)](https://postimg.cc/nj6zxxcs)
[![image.png](https://i.postimg.cc/SNJMRs7S/image.png)](https://postimg.cc/9rHMNcnK)

### 5.3.1. Domain Layer.
Dentro del dominio de WorkShop Management, se encuentran entidades clave como Maintenance y Workshop. Estas entidades desempeñan un papel fundamental en el proceso de facturación, ya que permiten a los usuarios generar su comprobante y poder realizar los pagos de los servicios de manera eficiente.

En el caso de WorkShop management, MaintenanceOrder es el agregado principal porque encapsula la lógica tanto de Maintenance para poder realizar el proceso principal de crear la orden de Mantenimiento.

A continuación, se muestra todos los objetos relacionados con el dominio  
[![image.png](https://i.postimg.cc/0NqMVCgj/image.png)](https://postimg.cc/CRmx1kxp)

### 5.3.2. Interface Layer.
La interface layer del bounded context del WorkShop Management es una parte esencial del sistema, ya que es la capa que permite la comunicación entre los diferentes componentes de la aplicación. Se encarga de manejar todo lo referente al taller de mecánica, así como los mantenimientos que estos deberán realizar. A continuación, se muestra los controllers identificados:  
[![image.png](https://i.postimg.cc/SsgnNFnY/image.png)](https://postimg.cc/Q9W80zkj)

### 5.3.3. Application Layer.
En esta sección, presentamos la Capa de Aplicación dentro del contexto del enfoque de diseño Domain-Driven Desing para nuestra plataforma de alquileres de automóviles. La Capa de Aplicación es responsable de coordinar las acciones y el flujo de datos entre la Capa de Dominio y la Capa de Infraestructura, actuando como intermediario y gestionando las interacciones entre estas capas. Esta capa es crucial para garantizar que la lógica de negocio, representada por la Capa de Dominio, se ejecute de manera eficiente y coherente.  
[![image.png](https://i.postimg.cc/6qSTnrL9/image.png)](https://postimg.cc/30XKHDc6)

### 5.3.4. Infrastructure Layer.
En esta sección, presentamos la Capa de Infraestructura (Infrastructure Layer) dentro del contexto del enfoque de diseño Domain-Driven Design (DDD) para nuestro bounded context Workshop Management. La Capa de Infraestructura es responsable de proporcionar los componentes técnicos y de soporte necesarios para que las otras capas del sistema funcionen correctamente. Esta capa incluye la implementación de repositorios, servicios que se conectan con sistemas externos y otros componentes de infraestructura.  
[![image.png](https://i.postimg.cc/hPzXgYch/image.png)](https://postimg.cc/ZCmbxV9h)

### 5.3.6. Bounded Context Software Architecture Component Level Diagrams.
En esta sección presentamos el component level diagram de nuestro bounded context Workshop Management. Estos diagramas proporcionan una visión detallada de cómo los diferentes componentes del sistema interactúan entre sí en el contexto de aplicaciones web y móviles. Al analizar estos diagramas, podemos obtener una comprensión clara de cómo la plataforma funciona desde un punto de vista arquitectónico y cómo los componentes se comunican entre sí.  
[![image.png](https://i.postimg.cc/htVhQ7JB/image.png)](https://postimg.cc/NKfQWF7J)

### 5.3.7. Bounded Context Software Architecture Code Level Diagrams.
#### 5.3.7.1. Bounded Context Domain Layer Class Diagrams.
El Bounded Context Domain Layer Class Diagrams del bounded context del Workshop Management representa los diagramas de clases para los diferentes componentes del dominio. Estos diagramas muestran cómo se modela la funcionalidad en el dominio del negocio, y cómo las diferentes clases interactúan para cumplir con las necesidades del negocio. Cada diagrama de clase muestra los atributos y métodos relevantes.  
[![image.png](https://i.postimg.cc/C1rKpG2j/image.png)](https://postimg.cc/yg9KFZsd)

#### 5.3.7.2. Bounded Context Database Design Diagram.
En el presente bounded context se tienen en cuenta las diferentes entidades y relaciones que deberán hacer persistencia en la base de datos que en este caso es una base de datos relacional.  
[![image.png](https://i.postimg.cc/qBY7mGyr/image.png)](https://postimg.cc/V5q1vnKZ)

## 5.4. Bounded Context: Subscription Management
Este dominio se centra en aplicar el plan escogido en aplicación móvil RentCar Assist. Este dominio maneja que los arrendadores, mecánicos y arrendatarios tengan acceso a los beneficios correspondientes según el plan que hayan pagado.

**Diccionario de clases:**  
[![image.png](https://i.postimg.cc/667Z5qh9/image.png)](https://postimg.cc/3WTNtK66)
[![image.png](https://i.postimg.cc/JzQDdkRQ/image.png)](https://postimg.cc/XrpYrXGZ)

### 5.4.1. Domain Layer.
Dentro del dominio Subscription Management, se encuentran las entidades User, Payment, Plan. Dichas entidades son las importantes para adquirir una subscripción.

Subscription Management, tiene como agregado principal Subscription el cual contiene toda la lógica de negocio de la subscripción a un plan.

A continuación, se muestra los objetos de este dominio.  
[![image.png](https://i.postimg.cc/MGPczJMM/image.png)](https://postimg.cc/JyX7QgQM)

### 5.4.2. Interface Layer.
En la capa de interfaz identificamos los controladores de las peticiones de los usuarios para acceder a los beneficios de la subscripción. Está compuesto por 3 controladores AccountController la cual se relaciona con las cuentas que realizarán la subscripción PlanController la cual se relaciona con actualizar el plan y SubscriptionController.  
[![image.png](https://i.postimg.cc/KzCRg75m/image.png)](https://postimg.cc/TLqRzDSs)

### 5.4.3. Application Layer.
En la capa de interacción identificamos CommandHandler y EventHandler. Identificamos a CreateSubscriptionCommandHandler la cual crea nuevas solicitudes de subscripción UpdateSubscriptionCommandHandler la cual actualiza la información de las suscripciones.  
[![image.png](https://i.postimg.cc/pXbmWZTZ/image.png)](https://postimg.cc/vDhYX55g)

### 5.4.4. Infrastructure Layer.
En la capa de infraestructura utilizamos repositorios jpa para manejar la interacción con la base de datos. Entre los repositorios clave identificamos SubscriptionRepository, PlanRepository y AccountRepository.  
[![image.png](https://i.postimg.cc/7Zqb7ZSJ/image.png)](https://postimg.cc/3dbKQ7S3)

### 5.4.6. Bounded Context Software Architecture Component Level Diagrams.
Para esta sección tenemos el diagrama de componentes del bounded context de subscripciones. Con este diagrama buscamos dar a entender cómo se relaciones los distintos componentes que conforman el servicio de suscripción que la plataforma ofrece. En el siguiente diagrama se puede apreciar que tanto la aplicación web como la aplicación móvil interactúan con los controladores que interactúan las peticiones que serán necesarias para validad la suscripción del usuario y de los planes con el que cuenta, siendo estos 2 servicios internos, con excepción del servicio de pago ya que se planea hacer uso de un servicio externo.  Cada controlador con excepción del que se acaba de mencionar interactúa con su respectivo repository el cual se encargara de hacer las peticiones correspondientes a la base de datos.  
[![image.png](https://i.postimg.cc/s2XX6H6V/image.png)](https://postimg.cc/Hrqdjz1K)

### 5.4.7. Bounded Context Software Architecture Code Level Diagrams.
Estos diagramas proporcionan información de como diferentes componentes de la aplicación interactuaran a nivel de código para poder extraer información de la base de datos, en este caso podemos observar la interacción de los servicios del usuario y de los planes que ofrece nuestra aplicación.

Dentro de los componentes tenemos el user Service, el cual nos permite obtener información acerca de los usuarios y a la vez guardar y actualizar información acerca de estos mismos. Un ejemplo de la usabilidad de estos es que mediante este servicio podemos actualizar el estado de suscripción de algún usuario afiliado a algún plan que ofrece la plataforma.

Por otro lado, tenemos el componente de plan, este servicio nos permite saber la cantidad de planes que tiene la aplicación para ofrecer a los usuarios de modo que siempre podemos tener actualizadas las ofertas que ofrezca nuestra plataforma y saber que usuarios están relacionados con algún plan y de ese modo saber quién está subscrito o no y que beneficios posee este usuario.  
[![image.png](https://i.postimg.cc/BbWnvSq6/image.png)](https://postimg.cc/KkN2qy3S)
[![image.png](https://i.postimg.cc/fWXbr9K0/image.png)](https://postimg.cc/F1rmf1w9)

#### 5.4.7.1. Bounded Context Domain Layer Class Diagrams.
El Bounded Context Domain Layer Class Diagrams del bounded context del subpcription  management representa los diagramas de clases para los diferentes componentes del dominio, incluyendo User, plan, payment. Estos diagramas muestran cómo se modela la funcionalidad en el dominio del negocio, y cómo las diferentes clases interactúan para cumplir con las necesidades del negocio. Cada diagrama de clase muestra los atributos y métodos relevantes.  
[![image.png](https://i.postimg.cc/zXrfZGt2/image.png)](https://postimg.cc/0rVv7Pq7)

#### 5.4.7.2. Bounded Context Database Design Diagram.
En esta sección se muestra la estructura de la base de datos y la relación que tendrán entre ellas. En este caso tenemos 4 tablas que representara la forma en la que se trabaja la subscripción de usuarios, de modo que se puedan hacer consultas acerca de los pagos que ha realizado el usuario y al plan que se encuentra afiliado.  
[![image.png](https://i.postimg.cc/SxQNRtpW/image.png)](https://postimg.cc/Xph0DLqJ)
