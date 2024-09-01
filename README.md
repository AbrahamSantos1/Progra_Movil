# Aplicación dedicada al Control de la Salud Infantil 

## 1. Introducción

El propósito de este documento es proporcionar una descripción detallada del diseño del software para el Proyecto Control Salud. Este documento está destinado a desarrolladores, arquitectos y otras partes interesadas para comprender la estructura y el comportamiento del sistema.

## 1.1. Visión general del sistema
El Proyecto Salud es un sistema diseñado para gestionar perfiles de pacientes y sus registros médicos. El sistema está orientado a padres y profesionales de la salud, proporcionando una interfaz para registrar, actualizar y consultar información médica de los pacientes. Los usuarios principales del sistema son padres que desean llevar un registro detallado de la salud de sus hijos y profesionales de la salud que necesitan acceder y actualizar estos registros.

## 2. Requerimientos funcionales - Historias de Usuario
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

## 3. Requerimientos no funcionales
Para el proyecto, se considero los siguientes requerimientos no funcionales:

**3.1. Rendimiento:** La aplicación debe cargar la pantalla principal en menos de 3 segundos, además debe ser eficiente en el consumo de memoria y procesador, especialmente en dispositivos con hardware limitado.

**3.2. Seguridad:** Debe contar con autenticación segura (PIN o contraseña) para proteger la información del usuario y toda la información sensible, tanto en tránsito como en reposo, debe estar cifrada.

**3.3. Escalabilidad:** La aplicación debe ser capaz de manejar un aumento del 100% en la base de usuarios sin una degradación significativa del rendimiento, además debería ser compatible con diferentes versiones de Android e iOS, garantizando una experiencia de usuario consistente.

**3.4. Usabilidad:**  Debe seguir las guías de diseño de material design para Flutter, garantizando que la interfaz sea intuitiva y accesible para todo tipo de usuarios. Además, debería soportar múltiples idiomas para adaptarse a diferentes mercados.

**3.5. Disponibilidad:** La aplicación debe estar operativa durante las 24 horas del día sin tener que caerse.

## 4. Diagrama Entidad Relación
![Diagrama de entidad relación](/Imagenes/EntidadRelacion.png)

## 5. Caso de Uso



## 6. Mockups