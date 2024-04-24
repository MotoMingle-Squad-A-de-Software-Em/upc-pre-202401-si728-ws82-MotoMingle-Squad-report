# Capítulo IV: Strategic-Level Software Design.
## 4.1. Strategic-Level Attribute-Driven Design.
### 4.1.1. Design Purpose.
El propósito del diseño es desarrollar una plataforma de alquiler de vehículos que sea intuitiva y eficaz, satisfaciendo las necesidades tanto de los propietarios de vehículos como de los clientes. Esta solución está destinada a facilitar un proceso de alquiler seguro y confiable, maximizando la utilidad y la satisfacción del usuario.

### 4.1.2. Attribute-Driven Design Inputs.
#### 4.1.2.1. Primary Functionality (Primary User Stories).
|#Orden|ID|Título|Historia de Usuario|
|------|--|------|-------------------|
|1|US009|Usuario arrendador registrado quiere colocar un anuncio de alquiler de auto.|Como usuario arrendador registrado quiero colocar un anuncio de alquiler de auto para obtener ganancias.|
|2|US007|Como usuario quiero suscribirme a un plan para tener beneficios|Como usuario arrendador registrado quiero adquirir un plan de suscripción de abono mensual para tener beneficios.|
|3|US023|Usuario arrendatario alquila un auto de su preferencia|Como usuario arrendatario quiero alquilar un auto de mi preferencia para trabajar y/o transportarme.|
|4|US016|Como usuario arrendador quiero establecer mis requisitos por el alquiler de mi auto|Como usuario arrendador quiero seleccionar una serie de requisitos preconfigurados para el alquiler de mi auto.|

#### 4.1.2.2. Quality attribute Scenarios.
**Usabilidad:** La plataforma deberá permitir a los usuarios registrarse y realizar un alquiler o listar un vehículo en menos de cinco minutos.  
**Medida:** Medición del tiempo promedio que toma completar las acciones mencionadas a través de pruebas de usuario.

#### 4.1.2.3. Constraints.
**Conformidad con GDPR:** La solución debe cumplir con la normativa general de protección de datos para operar en los mercados pertinentes.  
**Criterios de Aceptación:** Implementación de medidas de seguridad de datos, como el cifrado y la obtención del consentimiento del usuario.

### 4.1.3. Architectural Drivers Backlog.
La selección de los drivers arquitectónicos se basa en su importancia para las partes interesadas y su complejidad técnica, con prioridad en la seguridad y la experiencia del usuario.

### 4.1.4. Architectural Design Decisions.
Las decisiones de diseño incluyen la adopción de una arquitectura de microservicios para facilitar la escalabilidad y la independencia de los componentes del sistema.

### 4.1.5. Quality Attribute Scenario Refinements.
Los escenarios de atributos de calidad se han refinado para priorizar la usabilidad y la seguridad, asegurando que la plataforma sea accesible y confiable.

## 4.2 Strategic-Level Domain-Driven Design.
### 4.2.1. EventStorming.
En cuanto al proceso de nuestro EventStorming se utilizó la herramienta MIRO, donde se realizó todo el proceso. Se inició con el primer paso que sería Unstructured Exploration, para ello se analizó y compartieron diferentes opiniones acerca a los eventos del dominio, de igual manera se tuvo en cuenta varios criterios para elegir los eventos de dominio.

![Primer Paso de DDD](Resources/images/DDD-Images/Unstructured-Exploration.png)

Seguido de lo previamente nombrado, se inició el segundo paso llamado Timelines, donde discutimos el flujo de los eventos del dominio para tener una idea mucho más clara.

![Segundo Paso de DDD](Resources/images/DDD-Images/Timelines.png)

### 4.2.2. Candidate Context Discovery.
Para hallar a nuestros Candidate Context, continuamos con el paso 3 (Paint Points), donde discutimos eventos del flujo que podrían ser cuellos de botella o pasos manuales que requieren automatización. Algunos más importantes que hallamos fueron, por ejemplo, ¿Como sabremos la posición actual del vehículo? Y ¿cómo sabemos el estado del carro?

![Tercer Paso de DDD](Resources/images/DDD-Images/Paint-Points.png)

Después, comenzamos con el cuarto paso de DDD llamado Pivotal Points, donde identificamos puntos o eventos comerciales importantes que indicaban un cambio en el contexto o la fase. 
Para el flujo de línea del arrendador se encontraron los siguientes pivotal points:

![Pivotal Points del Ownver](Resources/images/DDD-Images/Pivotal-Points-Owner.png)

Para el usuario Arrendatario fueron los siguientes:

![Pivotal Points del Renter](Resources/images/DDD-Images/Pivotal-Points-Renter.png)

Y para el usuario Mecanico fueron los siguientes: 

![Pivotal Points del Mechanic](Resources/images/DDD-Images/Pivotal-Points-Mechanic.png)

Con todo ello, comenzamos el paso de Commands, donde escribimos el desencadenante de ciertos eventos del dominio, así como el actor encargado.

![Quinto paso de DDD](Resources/images/DDD-Images/Commands.png)

Después proseguimos con el paso 6, Policies, donde identificamos eventos que debían de ejecutarse en automático o necesitaban alguna politica.Por ejemplo, para actualizar el estado del vehículo una vez que este alquilado.

![Sexto paso de DDD](Resources/images/DDD-Images/Polices.png)

Con ello procedimos a discutir los modelos de lectura de datos, y logramos identificar algunos como el Rent, que se encarga del alquiler de vehículos. Los criterios para ello fueron complejidad, relevancia y frecuencia de actualización.

![Séptimo paso de DDD](Resources/images/DDD-Images/Read-Models.png)

También empezamos a discutir el uso de sistemas externos los cuales estaban relacionados a pagos y ubicación.

![Octavo paso de DDD](Resources/images/DDD-Images/External-Systems.png)

Después, se comenzó con la identificación de los agregattes, para ello, tomamos criterios como granularidad, consistencia, y estabilidad. Con esos criterios, se procedió a elegir  los Agreggattes, los cuales fueron los siguientes:
Aggregate encargado del proceso de la publicación de vehículos en renta:

![](Resources/images/DDD-Images/Submit-Order.png)

Aggregate encargado del proceso del regreso del auto:

![](Resources/images/DDD-Images/Confirm-Order-2.png)

Aggregate encargado del proceso de  la busqueda y alquiler del auto:

![](Resources/images/DDD-Images/Confirm-Order.png)

Aggregate encargado del proceso de la publicación de vehículos en renta:

![](Resources/images/DDD-Images/Submit-Order-4.png)

Aggregate encargado del proceso de manejo de autos del mecánico:

![](Resources/images/DDD-Images/Submit-Order-2.png)

Aggregate encargado del proceso de mantenimiento del auto:

![](Resources/images/DDD-Images/Confirm-Order-3.png)

Aggregate encargado del proceso de manejo de las suscripciones:

![](Resources/images/DDD-Images/Submit-Order-3.png)

Ya por ultimo y despues de un analisis y discusión grupal, los siguientes boudend contexts fueron elegidos:

![](Resources/images/DDD-Images/Renting-Management.png)

![](Resources/images/DDD-Images/Workshop-Service-Management.png)

![](Resources/images/DDD-Images/Subscription-Management.png)

![](Resources/images/DDD-Images/Billing-Management.png)

### 4.2.3. Domain Message Flows Modeling.
En relación a los flujos de mensajería, se eligieron los más relevantes para nuestro negocio, dejando de lado flujos generales como registro de usuario o pago de servicios.
Se estuvieron planteando los siguientes Flujos de mensajeria:
En primer lugar, tenemos el flujo de la creación del vehículo, el cual es clave para nuestro negocio. 

![](Resources/images/DDD-Images/Create-New-Car-Successfully.png)

El segundo flujo, es el que abarca el proceso de reservar un vehículo.

![](Resources/images/DDD-Images/Book-Car.png)

En tercer lugar, tenemos el flujo del pago de las suscripciones en este caso del dueño del vehiculo. 

![](Resources/images/DDD-Images/Pay-Subscription-Lessor.png)

En cuarto lugar, tenemos el flujo de seleccionar un mecánico.

![](Resources/images/DDD-Images/Select-Mechanic.png)

Por último, se tiene el flujo de mandar el vehículo a reparación.

![](Resources/images/DDD-Images/Send-Car-Mechanic.png)

### 4.2.4. Bounded Context Canvases.
De acuerdo con los boundend contexts definidos en puntos anteriores, se crearon sus respectivos Canvases: 

![](Resources/images/DDD-Images/Renting-Management-Canva.png)

![](Resources/images/DDD-Images/Workshop-Service-Management-Canva.png)

![](Resources/images/DDD-Images/Subscription-Management-Canva.png)

![](Resources/images/DDD-Images/Security.png)

![](Resources/images/DDD-Images/Billing-Management-Canva.png)

### 4.2.5. Context Mapping.

![](Resources/images/DDD-Images/Context-Mapping.png)

## 4.3. Software Architecture.
### 4.3.1. Software Architecture System Landscape Diagram.
[![image.png](https://i.postimg.cc/K8BLjmVt/image.png)](https://postimg.cc/k2MDhP75)

### 4.3.1. Software Architecture Context Level Diagrams.
[![image.png](https://i.postimg.cc/Kj132bBk/image.png)](https://postimg.cc/0KqyYLtP)

### 4.3.2. Software Architecture Container Level Diagrams.
[![image.png](https://i.postimg.cc/c1z8cKGQ/image.png)](https://postimg.cc/t7hTq4TT)

### 4.3.3. Software Architecture Deployment Diagrams.
[![image.png](https://i.postimg.cc/RZ769X6R/image.png)](https://postimg.cc/v4mHt7vg)

