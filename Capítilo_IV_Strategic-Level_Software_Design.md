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

### 4.2.5. Context Mapping.
