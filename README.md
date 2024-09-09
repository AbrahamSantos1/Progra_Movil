# Aplicación dedicada al Control de la Salud Infantil 

## 1. Introducción

El propósito de este documento es proporcionar una descripción detallada del diseño del software para el Proyecto Control Salud. Este documento está destinado a desarrolladores, arquitectos y otras partes interesadas para comprender la estructura y el comportamiento del sistema.

## 1.1. Visión general del sistema
El Proyecto Salud es un sistema diseñado para gestionar perfiles de pacientes y sus registros médicos. El sistema está orientado a padres y profesionales de la salud, proporcionando una interfaz para registrar, actualizar y consultar información médica de los pacientes. Los usuarios principales del sistema son padres que desean llevar un registro detallado de la salud de sus hijos y profesionales de la salud que necesitan acceder y actualizar estos registros.

## 2. Entorno de desarrollo

## 3. Diagrama de Despliegue
A continuación, se presenta el Diagrama de Despliegue relacionado con los requerimientos no funcionales

![Diagrama de Despliegue](/Imagenes/DiagramaDespliegue.png)

## 4. Requerimientos funcionales - Historias de Usuario
A continuación, se describe cada uno de las historias de usuario que se consideró en el proyecto.   

![HU1](/Historias%20de%20Usuario/1.png)

![HU2](/Historias%20de%20Usuario/2.png)

![HU3](/Historias%20de%20Usuario/3.png)

![HU4](/Historias%20de%20Usuario/4.png)

![HU5](/Historias%20de%20Usuario/5.png)

![HU6](/Historias%20de%20Usuario/6.png)

![HU7](/Historias%20de%20Usuario/7.png)

![HU8](/Historias%20de%20Usuario/8.png)

![HU9](/Historias%20de%20Usuario/9.png)

## 5. Requerimientos no funcionales
Para el proyecto, se considero los siguientes requerimientos no funcionales:

**5.1. Rendimiento:** El sistema debe ser capaz de responder a las consultas en menos de 2 segundos para garantizar una experiencia fluida y debe poder manejar un aumento en el número de usuarios (padres y profesionales de la salud) y en la cantidad de registros médicos sin comprometer el rendimiento

**5.2. Seguridad:** Toda la información médica y los datos personales de los pacientes deben estar encriptados, tanto en tránsito como en reposo. Además, debe contar con una autenticación y autorización estricta para garantizar que solo los usuarios autorizados (padres y profesionales de la salud) puedan acceder a la información. Finalmente, se debe cumplir con las leyes de protección de datos personales y médicos según la jurisdicción.

**5.3. Fiabilidad:**  El sistema debe contar con mecanismos de tolerancia a fallos para minimizar el impacto en caso de errores o caídas del sistema, además debe tener herramientas de monitoreo para detectar y corregir problemas antes de que afecten a los usuarios.

**5.4. Usabilidad:**  Debe seguir las guías de diseño de material design para Flutter, garantizando que la interfaz sea intuitiva y accesible para todo tipo de usuarios. Además, la aplicación debe ser accesible desde diferentes dispositivos (móviles, tabletas, y computadoras) y navegadores. Debe tener soporte para múltiples idiomas para adaptarse a diferentes regiones geográficas.

**5.5. Disponibilidad:** El sistema debe estar disponible al menos el 99.9% del tiempo, garantizando un acceso constante para los usuarios, tanto padres como profesionales de la salud. Además, debe contar con implementación de planes de respaldo automático y estrategias de recuperación ante desastres para proteger la integridad de los datos.

## 6. Diagrama Entidad Relación ## 
Se presentará el diagrama de entidad-relación del proyecto que modela las distintas entidades clave del sistema y las relaciones entre ellas.

![Diagrama de entidad relación](/Imagenes/EntidadRelacion.png)

 A continuación, se detallan las principales entidades:

**6.1. Entidades Principales**

**padres:**  Contiene la información personal de los padres, como nombre, apellidos, DNI, género y fecha de nacimiento. Los padres están vinculados a usuarios del sistema.

**profesional_salud:** Contiene la información personal de los profesionales de la salud. Estos están vinculados a usuarios del sistema.

**usuarios:** Esta entidad almacena la información de inicio de sesión de los padres y los doctores, como su email y contraseña. Está relacionada con la entidad padres y profesional_salud a través de una clave foránea.

**perfil_pacientes:** Aquí se almacena la información de los pacientes, como nombre, fecha de nacimiento, DNI, género y edad. Está relacionada con los usuarios, permitiendo a los padres gestionar los perfiles de sus hijos.

**registro_medicos:** Esta entidad guarda los registros médicos de cada paciente, como fechas de consultas. Está vinculada al perfil de los pacientes.

**datos_medicos:** Subentidad del registro médico que almacena datos específicos como peso, talla, y la fecha en que fueron registrados.

**vacunas:** Esta entidad contiene información de las vacunas disponibles, incluyendo el nombre, descripción y estado de la vacuna.

**esquema_vacunacion:** Define cuándo una vacuna ha sido aplicada a un paciente, relacionando la vacuna con el perfil del paciente.

**citas_vacunacion:** Guarda la información de las citas futuras de vacunación, permitiendo a los usuarios programar cuándo y dónde se realizarán las vacunaciones.

**6.2 Relaciones entre entidades:**

**padres - usuarios:** Un padre tiene un perfil de usuario en el sistema, lo que le permite acceder al sistema con su email y contraseña.

**profesional_salud - usuarios:** Un doctor tiene un perfil de usuario en el sistema, lo que le permite acceder al sistema con su email y contraseña.

**usuarios - perfil_pacientes:** Cada usuario puede gestionar uno o más perfiles de pacientes, lo que les permite tener un control detallado de la salud de sus hijos.

**perfil_pacientes - registro_medicos** Cada paciente puede tener múltiples registros médicos, los cuales almacenan información médica histórica.

**registro_medicos - datos_medicos:** Cada registro médico puede tener múltiples datos médicos asociados, como peso y talla del paciente en la fecha registrada.

**perfil_pacientes - esquema_vacunacion:** Los pacientes pueden tener un esquema de vacunación que rastrea todas las vacunas aplicadas.

**esquema_vacunacion - vacunas:** El esquema de vacunación se relaciona con las vacunas disponibles en el sistema, permitiendo registrar qué vacuna se ha aplicado a un paciente.

**perfil_pacientes - citas_vacunacion:** Cada paciente puede tener citas futuras programadas para la aplicación de vacunas.

## 7. Caso de Uso ##
A continuación, se presenta el diagrama del caso de uso del proyecto:

![Diagrama de caso de Uso](/CasodeUso/1.png)

## 8. Descripción del Caso de Uso ##
A continuación, se dará una descripción del caso de uso presentado en el punto 6.

**8.1. Actores**

**8.1.1. Padre:**

**Consulta esquema de vacunación:** El padre puede acceder al sistema para revisar el calendario o esquema de vacunación del paciente bajo su cuidado.

**Registra perfil de paciente:** Tiene la capacidad de registrar a un paciente en el sistema, ingresando su perfil básico (nombre, fecha de nacimiento, etc.).

**Consulta información del paciente:** Puede acceder a información detallada del paciente, como su historial médico, vacunación, o información relevante.

**Registra usuario:** En este caso, el padre puede crear nuevos usuarios en el sistema, lo que podría implicar agregar más personas relacionadas con el cuidado del paciente o crear un perfil de usuario para sí mismo.

**8.1.2. Paciente:**

**Consulta su perfil:** El paciente puede ingresar al sistema y revisar su propio perfil, el cual podría contener información como su historial médico, esquema de vacunación, alergias, etc.

**Registrar/actualizar sus datos médicos:** El paciente tiene la capacidad de introducir o actualizar sus propios datos médicos dentro del sistema, como el registro de síntomas, información sobre visitas al médico, resultados de pruebas, entre otros.

**8.1.3. Profesional de la Salud:**

**Registro del profesional:** El profesional de la salud puede registrar su perfil en el sistema, lo que probablemente implica registrar su licencia médica, especialidad y otros datos relevantes.

**Actualiza esquema de vacunación:** Este caso de uso permite al profesional de la salud modificar o actualizar el calendario de vacunación del paciente, agregando información sobre vacunas administradas o programando futuras dosis.

**Programa citas de vacunación:** El profesional puede gestionar y programar las citas de vacunación del paciente, lo que incluye definir la fecha, hora y tipo de vacuna que se administrará.

**8.2. Casos de Uso:**

**Consultar esquema de vacunación:** Caso de uso general que permite a los usuarios (padres, pacientes o profesionales de la salud) visualizar el calendario de vacunación del paciente.

**Registrar paciente:** Permite registrar un nuevo paciente en el sistema, involucrando el ingreso de datos personales como el nombre, edad, dirección, etc.

**Ver perfil de paciente:** Acceso a la información detallada de un paciente, que incluye tanto información personal como su historial médico.

**Registrar usuario:** Función que permite añadir nuevos usuarios al sistema. Esto puede implicar tanto pacientes como profesionales de la salud o administradores.

**Registrar datos médicos:** Caso de uso enfocado en permitir a los pacientes o profesionales introducir y actualizar información médica relevante, como síntomas, diagnósticos o resultados de pruebas.

**Actualizar datos de vacunación:** Permite modificar o agregar información sobre las vacunas del paciente, ya sea la fecha de vacunación, tipo de vacuna administrada, o programar futuras citas.

**Programar citas de vacunación:** El profesional de la salud gestiona las citas de vacunación del paciente, asegurando que el esquema de vacunación esté actualizado y bien planificado.

**Relaciones:**

Los actores están conectados a los casos de uso mediante flechas que indican sus interacciones con el sistema. Estas flechas representan las acciones que cada actor puede realizar dentro del sistema de salud.

Padre tiene acceso a funciones relacionadas con la consulta de información del paciente y la gestión del perfil del mismo, ya que es el responsable del paciente.

Paciente tiene un rol más activo en la gestión de su propio perfil y datos médicos.

Profesional de la salud se centra en tareas administrativas y clínicas relacionadas con el mantenimiento del esquema de vacunación y la gestión de citas

