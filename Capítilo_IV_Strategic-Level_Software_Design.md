# Capítulo IV: Strategic-Level Software Design.
## 4.1. Strategic-Level Attribute-Driven Design.
### 4.1.1. Design Purpose.
El propósito del diseño es desarrollar una plataforma de alquiler de vehículos que sea intuitiva y eficaz, satisfaciendo las necesidades tanto de los propietarios de vehículos como de los clientes. Esta solución está destinada a facilitar un proceso de alquiler seguro y confiable, maximizando la utilidad y la satisfacción del usuario.

### 4.1.2. Attribute-Driven Design Inputs.
#### 4.1.2.1. Primary Functionality (Primary User Stories).
|Orden|ID|Historia de Usuario|
|------|--|-------------------|
|1|US009|Como usuario arrendador registrado quiero colocar un anuncio de alquiler de auto para obtener ganancias.|
|2|US007|Como usuario arrendador registrado quiero adquirir un plan de suscripción de abono mensual para tener beneficios.|
|3|US023|Como usuario arrendatario quiero alquilar un auto de mi preferencia para trabajar y/o transportarme.|
|4|US016|Como usuario arrendador quiero seleccionar una serie de requisitos preconfigurados para el alquiler de mi auto.|

#### 4.1.2.2. Quality attribute Scenarios.
|ID|Atributo de calidad|Escenario|Historia de usuario|
|--|-------------------|---------|-------------------|
| AC-01 | Fiabilidad y Seguridad | Dado que la persona quiere adquirir un plan flota silver, cuando elige el plan flota silver, entonces debe ingresar una tarjeta de crédito o débito, cuando se valide la tarjeta mediante la API de stripe, entonces el sistema valida su membresía y le otorgará los accesos para que use el servicio. | US-007 |
| AC-02 | Fiabilidad | Dado que el usuario ingresa los datos de una tarjeta de crédito o débito inválida cuando se valida la tarjeta, entonces la vista muestra un aviso informando que la tarjeta es inválida. | US-007 |
| AC-03 | Usabilidad | Dado que el usuario se encuentra en la sección “Mis autos” y selecciona el botón “Añadir Auto”, cuando complete el formulario de añadir auto sin omitir ningún campo del formulario y rellenando campos como modelo, placa, fecha de disponibilidad entonces el sistema mostrará un mensaje de “Anuncio publicado exitosamente”. | US-009 |
| AC-04 | Fiabilidad | Dado que el usuario se encuentra en la sección “Mis autos” y selecciona el botón “Añadir Auto” cuando complete el formulario de añadir auto omitiendo algunos campos entonces el sistema mostrará un mensaje de “Información del auto inválida” | US-009 |
| AC-05 | Eficiencia | Dado que el usuario arrendador ingresa a las opciones del auto en el apartado “Alquiler” y puede escoger en la sección “restricciones” cuando visualice cada ítem de la lista con un checkbox al lado, podrá marcar cuales desea requerir, entonces para guardar la configuración podrá hacer click en el boton guardar. | US-016 |
| AC-06 | Usabilidad y Eficiencia | Dado que el usuario arrendatario se encuentra en la sección “Menú Principal”, el usuario arrendatario puede visualizar todos los tipos de autos disponibles cuando el usuario arrendatario seleccione cualquier auto, puede ver a detalle sus características. Si desea alquilar dicho auto, tan solo da clic “Alquilar auto” entonces el sistema le redirigirá a una nueva pantalla para hacer un trato con el dueño del auto | US-023 |


#### 4.1.2.3. Constraints.
|ID|Descripción|
|--|-----------|
| CON-001 | Validación de tarjeta de crédito o débito. |
| CON-002 | Validación de tarjeta de crédito o débito inválida |
| CON-003 | Completar el formulario de añadir auto sin omitir ningún campo y rellenando campos específicos como modelo, placa, y fecha de disponibilidad. |
| CON-004 | Omitir algunos campos al completar el formulario de añadir auto. |
| CON-005 | Permitir al usuario arrendador seleccionar y guardar restricciones para el alquiler del auto. |
| CON-006 | Permitir al usuario arrendatario visualizar y alquilar un auto desde el menú principal. |

### 4.1.3. Architectural Drivers Backlog.
La selección de los drivers arquitectónicos se basa en su importancia para las partes interesadas y su complejidad técnica, con prioridad en la seguridad y la experiencia del usuario.

| Driver ID | Título de Driver | Descripción | Importancia para Stakeholders (High, Medium, Low) | Impacto en Architecture Technical Complexity (High, Medium, Low) |
| --------- | ---------------- | ----------- | ------------------------------------------------- | ---------------------------------------------------------------- |
| AD01 | Gestión de Anuncios | Capacidad para listar y gestionar anuncios de vehículos para alquiler | Alta | Media |
| AD02 | Suscripción y Beneficios | Proceso de suscripción para arrendadores con gestión de beneficios | Media | Baja |
| AD03 | Selección de Vehículos | Facilidad para que los arrendatarios encuentren y seleccionen vehículos | Alta | Alta |
| AD04 | Requisitos Preconfigurados | Capacidad para que los arrendadores establezcan requisitos preconfigurados para el alquiler | Media | Media |
| AD05 | Integración de Pagos Seguros | Implementar API de pagos para procesar tarjetas de crédito de forma segura y fiable (AC-01, AC-02) | Alta | Alta |
| AD06 | Facilidad de Publicación de Anuncios | Facilitar a los usuarios la adición de nuevos anuncios de vehículos sin errores (AC-03, AC-04) | Media | Media |
| AD07 | Configuración de Restricciones | Permitir a los arrendadores configurar restricciones personalizadas para el alquiler de autos (AC-05) | Media | Baja |
| AD08 | Optimización del Flujo de Alquiler | Mejorar la usabilidad y eficiencia en el proceso de visualización y alquiler de vehículos (AC-06) | Alta | Media |
| AD09 | Validación de Pago | Implementación de un sistema de validación de tarjetas de crédito/débito para transacciones seguras | Alta | Media |
| AD10 | Manejo de Tarjetas Inválidas | Proceso robusto para manejar tarjetas de crédito/débito inválidas y comunicar errores al usuario | Media | Baja |
| AD11 | Formulario de Añadir Auto | Diseño de formulario para añadir autos que sea flexible pero que asegure la captura de información crítica | Media | Alta |
| AD12 | Validación de Formulario | Validaciones para asegurar que no se omitan campos críticos en el formulario de añadir autos | Media | Media |
| AD13 | Restricciones de Alquiler | Facilidad para que los arrendadores establezcan y guarden restricciones para el alquiler de vehículos | Media | Baja |
| AD14 | Acceso y Visualización de Autos | Permitir a los usuarios visualizar y alquilar vehículos fácilmente desde el menú principal | Alta | Media |

### 4.1.4. Architectural Design Decisions.
Las decisiones de diseño incluyen la adopción de una arquitectura de microservicios para facilitar la escalabilidad y la independencia de los componentes del sistema.

| Driver ID | Título de Driver | Pattern 1: MVC |               | Pattern 2: Microservicio |                  | Pattern 3: Serverless |                        |
| --------- | ---------------- | -------------- | ------------- | ------------------------ | ---------------- | --------------------- | ---------------------- |
|           |                  | Pro            |  Con          | Pro                      | Con              | Pro                   | Con                    |
| AD01 | Gestión de Anuncios | Separación de concerns | Puede ser rígido | Escalabilidad | Complejidad de despliegue | Costo variable | Depende de terceros |
| AD02 | Suscripción y Beneficios | Ciclo de desarrollo conocido | Menos flexible | Independencia de servicios | Requiere coordinación | Escalabilidad automática | Integración compleja |
| AD03 | Selección de Vehículos | Consistencia en el UI | Menor escalabilidad | Despliegue independiente | Costo inicial alto | Alta disponibilidad | Limitaciones de tiempo de ejecución |
| AD04 | Requisitos Preconfigurados | Control centralizado | Flexibilidad limitada | Permite personalización | Complejidad de gestión | Implementación rápida | Menor control sobre la infraestructura |
| AD05 | Integración de Pagos Seguros | Integración centralizada que puede facilitar el cumplimiento de PCI DSS. | Más difícil de escalar en caso de un gran volumen de transacciones. | Permite escalar el servicio de pagos de forma independiente según la demanda. | Complejidad adicional en la gestión de transacciones. | Escalabilidad automática y no hay necesidad de manejar la infraestructura de pagos. | Dependencia en la disponibilidad y fiabilidad del proveedor de servicios serverless. |
| AD06 | Facilidad de Publicación de Anuncios | Vista unificada para la creación de anuncios. | Menor flexibilidad para evolucionar la UI de manera independiente. | Permite una gestión independiente del microservicio de anuncios | Posible redundancia y necesidad de sincronización de datos. | Simplificación de la implementación de la publicación de anuncios. | Puede incurrir en costos adicionales y tiempos de respuesta variables. |
| AD07 | Configuración de Restricciones | Fácil gestión de restricciones en el mismo lugar que la lógica de negocio. | Puede requerir actualización completa si cambian las restricciones. | Servicios dedicados a manejar restricciones pueden ser actualizados sin afectar otros servicios. | Complejidad en mantener consistencia entre servicios. | Flexibilidad para ajustar las restricciones en función del uso. | Depende de la consistencia y la comunicación con otros servicios serverless. |
| AD08 | Optimización del Flujo de Alquiler | Proceso de alquiler coherente y centralizado. | Puede ser menos adaptable a flujos de usuarios altamente dinámicos. | Los flujos de alquiler pueden escalar y evolucionar de manera independiente.  | Aumento de la complejidad en la gestión de estado y transacciones. | Se puede ajustar rápidamente a picos de demanda. | Posible complejidad en el manejo del estado entre funciones serverless. |
| AD09 | Validación de Pago | Consistente en todas las interfaces de usuario. | Puede ser un cuello de botella si no se maneja adecuadamente. | Permite la segregación de la lógica de validación de pagos. | Necesidad de manejo consistente de errores a través de microservicios. | Escalabilidad en función del volumen de pagos. | Riesgos asociados a la integración con proveedores de servicios de pago externos. |
| AD10 | Manejo de Tarjetas Inválidas | Fácil implementación de validaciones en un solo lugar. | Menos flexibilidad para actualizaciones rápidas. | Servicios dedicados para manejar validaciones específicas de pago. | Mayor esfuerzo en la coordinación de servicios. | La función puede ser activada específicamente para la validación de pagos, optimizando recursos. | Puede haber latencia en la comunicación entre servicios. |
| AD11 | Formulario de Añadir Auto | Interfaz de usuario coherente para la entrada de datos. | Cambios en el formulario pueden requerir actualizaciones globales. | Desarrollo y despliegue independiente del servicio de formularios. | Integración compleja con otros servicios. | Flexibilidad y escalabilidad para manejar picos de actividad al añadir autos. | Posible dependencia de terceros para la gestión del estado. |
| AD12 | Validación de Formulario | Valida datos en tiempo real con el usuario, mejorando la experiencia de usuario. | Requiere una vista y controlador robustos | Permite la reutilización de servicios de validación para diferentes partes de la aplicación. | Complejidad adicional en la gestión y orquestación de microservicios. | Las validaciones pueden escalar automáticamente y aislar la lógica de validación. | Requiere gestión cuidadosa de la consistencia de datos entre invocaciones. |
| AD13 | Restricciones de Alquiler | Centraliza las reglas de negocio para evitar restricciones. | Actualizar las restricciones puede requerir despliegues de toda la aplicación. | Microservicios específicos pueden manejar reglas de restricciones que cambian con frecuencia. | Necesidad de un mecanismo de comunicación eficaz entre servicios. | Flexibilidad para cambiar las restricciones sin afectar otros componentes. | Puede haber retos en el manejo del estado y la coherencia. |
| AD14 | Acceso y Visualización de Autos | Proceso unificado y consistente para la visualización de autos. | Puede no ser tan escalable para grandes inventarios. | Escala fácilmente con la adición de más servicios, ideal para grandes inventarios. | Más complejidad en la gestión de la información distribuida. | Escalabilidad basada en demanda para la visualización y selección de autos. | Dependencia de la estabilidad del proveedor de la plataforma serverless. |

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

