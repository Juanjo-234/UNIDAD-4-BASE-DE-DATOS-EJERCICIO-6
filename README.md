# UNIDAD-4-BASE-DE-DATOS-EJERCICIO-6
1. Estructura de las Tablas Principales
proyecto

Almacena la información macro de cada proyecto corporativo o de desarrollo.

Campos: id_proyecto (identificador único), presupuesto (monto monetario asignado), nombre_comercial, fecha_inicio y fecha_finalizacion.

fases

Desglosa cada proyecto en etapas o fases del ciclo de vida del desarrollo de software (ej. análisis, diseño, desarrollo, pruebas).

Campos: id_fase, id_proyecto (clave foránea que vincula la fase a su proyecto correspondiente), nombre, estado, descripcion y estimacion_horas.

tarea

Contiene las actividades específicas o tareas concretas que componen cada fase del proyecto.

Campos: id_tarea, id_fase (clave foránea que asocia la tarea a una fase), descripcion, horas_trabajadas y estado.

empleado

Registra al personal técnico y profesional disponible para la ejecución de los proyectos.

Campos: legajo (número de identificación interna del empleado), dni, nombre, apellido, perfil_tecnico y categoria_laboral.

recursos

Controla los recursos físicos, hardware o equipamientos asignables dentro de la organización.

Campos: numero_inventario (identificador único del recurso), marca, modelo, costo y estado.

2. Tablas Intermedias (Relaciones Muchos a Muchos)
usa

Tabla asociativa que resuelve la relación de muchos a muchos entre los recursos tecnológicos/materiales y los proyectos en los que se emplean.

Campos: numero_inventario y id_proyecto.

asignacion_tarea

Tabla asociativa que vincula a los empleados con las tareas que deben realizar, permitiendo registrar el esfuerzo invertido por cada trabajador.

Campos: id_tarea, legajo y horas_trabajadas.

3. Claves Primarias y Restricciones de Integridad (Foreign Keys)
El script establece de forma estricta las reglas de integridad referencial para asegurar la consistencia de los datos mediante claves primarias (PRIMARY KEY) compuestas o simples, y claves foráneas (FOREIGN KEY):

proyecto_pkey: Define id_proyecto como clave primaria en la tabla proyectos.

fases_pkey y fk_fases_proyecto: Asocian lógicamente las fases a sus respectivos proyectos.

tarea_pkey y fk_tarea_fase: Garantizan que cada tarea pertenezca de forma estructurada a una fase válida.

empleado_pkey y recursos_pkey: Identifican unívocamente a cada empleado y recurso mediante sus respectivos campos de identificación (legajo y numero_inventario).

usa_pkey, fk_usa_recurso y fk_usa_proyecto: Establecen una clave primaria compuesta (numero_inventario, id_proyecto) para controlar qué recursos se destinan a cada proyecto.

asignacion_tarea_pkey, fk_asignacion_tarea y fk_asignacion_empleado: Establecen una clave primaria compuesta (id_tarea, legajo) junto con restricciones para asegurar que las tareas solo se asignen a empleados y tareas existentes.

IMAGEN DE EJEMPLO DE CONSULTA:
<img width="1118" height="361" alt="image" src="https://github.com/user-attachments/assets/6d35fbd9-c677-4786-aec6-b9197e41cf33" />
