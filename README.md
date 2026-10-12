# Ejercicio 19 - Modelo Entidad-Relación de un Sistema de Crowdfunding

## Descripción
Este ejercicio consiste en diseñar un modelo Entidad-Relación (DER) para un sistema de financiamiento colectivo (crowdfunding). El modelo permite administrar usuarios, proyectos, recompensas asociadas e inversiones o aportes monetarios.

## Entidades y atributos

### 1. Usuario
Representa a los miembros registrados en la plataforma, ya sean creadores o inversores.
- **id_usuario**: identificador único del usuario.
- **nombre**: nombre y apellido del usuario.
- **pais**: país de residencia.
- **correo**: correo electrónico de contacto.
- **datos bancarios**: información financiera para transacciones.

### 2. Proyecto
Representa las iniciativas creativas o empresariales que buscan financiamiento.
- **id_proyecto**: identificador único del proyecto.
- **id_creator**: identificador del usuario creador.
- **titulo**: título principal del proyecto.
- **categoria**: categoría o temática de la iniciativa.
- **descripcion detallada**: explicación amplia de los objetivos del proyecto.
- **objetivo**: meta económica a recaudar.
- **fecha inicio**: fecha de lanzamiento de la campaña.
- **fecha fin**: fecha límite de recaudación.
- **estado**: estado actual de la campaña (ej. activo, financiado, finalizado).

### 3. Recompensa
Representa los incentivos o contraprestaciones ofrecidas a cambio de los aportes.
- **id_recompensa**: identificador único de la recompensa.
- **id_proyecto**: identificador del proyecto asociado.
- **titulo recompensa**: nombre del incentivo.
- **descripcion**: detalle de lo que incluye la recompensa.
- **valor minimo**: monto mínimo de aporte requerido para acceder a la recompensa.
- **cupo maximo**: límite de unidades disponibles de la recompensa.

### 4. Aporte
Representa la contribución económica realizada por un inversor hacia un proyecto y su recompensa elegida.
- **id_aporte**: identificador único del aporte.
- **id_inversor**: identificador del usuario que realiza la inversión.
- **id_proyecto**: identificador del proyecto financiado.
- **id_recompensa**: identificador de la recompensa seleccionada.
- **fecha hora**: marca temporal de la transacción.
- **monto aportado**: valor monetario de la contribución.

## Relaciones y cardinalidades
- **Usuario – Proyecto (Funda / 1:N)**: un usuario puede crear y liderar múltiples proyectos en la plataforma.
- **Proyecto – Recompensa (Ofrece / 1:N)**: un proyecto ofrece distintas recompensas escalonadas para incentivar a los mecenas.
- **Usuario – Aporte (Invierte / 1:N)**: un usuario inversor puede realizar diversas contribuciones financieras.
- **Proyecto – Aporte (Recolecta / 1:N)**: un proyecto recibe múltiples aportes económicos a lo largo de su campaña.
- **Recompensa – Aporte (Canjea / 1:N)**: una recompensa puede ser seleccionada y adquirida a través de varios aportes de los inversores.

## Objetivo
Diseñar una base de datos para una plataforma de crowdfunding que permita administrar los perfiles de los usuarios, gestionar la creación y publicación de proyectos con sus respectivas metas financieras, configurar un sistema de recompensas por aportes, y llevar un registro detallado de las transacciones e inversiones realizadas por la comunidad.
