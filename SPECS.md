## Descripción general

La tarea a realizar consiste en la creación de un panel de administración para una plataforma SaaS en desarrollo de la startup Agenthub. Se debe generar un prototipo HTML del panel de administración. La startup se dedica al alquiler de agentes de IA equipados con diferentes skills para su despliegue en negocios específicos. El panel será utilizado internamente por el administrador para gestionar directamente el alquiler de los agentes.

Las secciones a incluir son:

1) Dashboard

2) Gestión de usuarios

3) Gestión de agentes

4) Skills

5) Contrataciones de agentes

6) Log de errores

## Estructura general del panel

El panel debe incluir una serie de secciones accesibles desde una barra de navegación lateral persistente y un toggle que permita cambiar entre un modo claro y un modo oscuro (usando las utilidades dark: de Tailwind).

## Descripción de funciones de cada sección

Dashboard: debe imprimir en pantalla los ingresos totales generados este mes, pérdida total por descuentos y cupones, número de agentes activos en todos los clientes, y número de agentes actualmente marcados como fallando. Cada indicador debe ser una tarjeta de métrica visible y debajo de ellas debe aparecer un marcador de posición para un gráfico de actividad semanal.

Gestión de usuarios: lista de usuarios registrados (nombre, email, plan, estado) que incluya un dropdown de acciones ("Ver detalle" y "Eliminar"). Al seleccionar "Ver detalle" debe abrirse un modal con overlay con el registro completo del usuario y debe cerrarse mediante un botón y haciendo clic en el backdrop.

Gestión de agentes: listado de todos los agentes registrados, mostrando nombre del agente, propietario, estado actual (activo / inactivo / fallando) y una lista de skills colapsada. Las skills asociadas a cada agente están ocultas por defecto; hacer clic en un control expandible las revela con una transición suave. Cada agente también tiene un dropdown de acciones con las opciones "Configurar" — que abre un modal con el prompt de sistema del agente — y "Eliminar".

Skills: catálogo de skills disponibles. Cada skill tiene un nombre, una descripción breve, y un indicador de cuántos agentes la tienen habilitada actualmente. Se debe incluir una sección que explique qué es una skill en el contexto de Agenthub. Cada skill debe tener un dropdown con las opciones "Ver detalle" y "Eliminar".

Contrataciones de agentes: tabla que muestra todos los contratos de alquiler activos y pasados. Cada fila debe mostrar el cliente, el agente alquilado, las skills contratadas, las fechas del contrato y el importe total pagado. Cada fila tiene un dropdown de acciones. Al elegir "Ver detalle" se abre un modal con el desglose completo del contrato, incluyendo la lista desglosada de skills contratadas y sus precios individuales.

Log de errores: registro de errores de ejecución de los agentes — mostrando timestamp, nombre del agente, tipo de error y una descripción breve. Los errores deben categorizarse visualmente por tipo o gravedad usando badges con código de color. Cada entrada tiene un dropdown de acciones con "Ver detalle" (abre un modal con la traza completa del error) y "Marcar como resuelto".

## Descripción de estructura de cada sección

Dashboard: el dashboard constará de 4 tarjetas de métricas en una cuadrícula responsive 2 x 2 y una tarjeta con el gráfico de actividad semanal que ocupará el ancho de dos tarjetas con la altura de una. Cada tarjeta tendrá una sombra leve que facilite su visualización, una etiqueta y un ícono. 

Gestión de usuarios: esta sección constará de una tabla en la que se listarán los usuarios registrados con sus datos específicos. La tabla tendrá un título y una descripción con un ícono en cada columna. Sobre su extremo derecho cada fila (usuario) tendrá un menú desplegable (dropdown) que incluirá las opciones de "Ver detalles" y "Eliminar" con sus correspondientes íconos, las que abrirán un modal que se superpondrá a la tabla. La tabla será responsive y tendrá colores de fondo que contrasten con el fondo. Las columnas de la tabla tendrán dos tonos de un mismo color (gris claro y gris oscuro) que se alternarán para facilitar su lectura. Al abrirse el modal el contenido de fondo deberá transicionar a colores más discretos para centrar la atención en el nuevo elemento en pantalla. 

Gestión de agentes: en esta sección encontraremos una nueva tabla con encabezado y una descripción e ícono en cada columna (nombre, propietario, estado actual y lista de skills). Las skills asociadas a cada agente están ocultas por defecto; hacer clic en un control expandible las revela con una transición suave. La tabla será responsive y tendrá colores de fondo que contrasten con el fondo. Las columnas de la tabla tendrán dos tonos de un mismo color (gris claro y gris oscuro) que se alternarán para facilitar su lectura. Sobre su extremo derecho cada fila (agente) tendrá un menú desplegable (dropdown) que incluirá las opciones de "Configurar" y "Eliminar" con sus correspondientes íconos, las que abrirán un modal que se superpondrá a la tabla.

Skills: esta sección constará de un div con un fondo que contraste con el fondo general de la página, que contendrá una cuadrícula de 4 x 2 tarjetas pequeñas con las diferentes skills configurables. Cada tarjeta contendrá un nombre, una descripción breve y un indicador de cuántos agentes la tienen equipada en ese momento. Por otra parte, cada tarjeta tendrá una sombra leve que facilite su visualización, una etiqueta y un ícono. Debajo de las tarjetas habrá un recuadro con borde fino y un color de fondo más oscuro que explicará brevemente qué es una skill en el contexto de la empresa. Toda la sección será responsive.

Contrataciones de agentes: esta sección contendrá una tabla del mismo estilo que las anteriores. Cada fila debe mostrar el cliente, el agente alquilado, las skills contratadas, las fechas del contrato y el importe total pagado. También incluirá un dropdown similar a los anteriores que tendrá una única opción ("Ver detalle") que desplegará un modal similar a los anteriores en el que se mostrarán los detalles del contrato en cuestión. El funcionamiento y la estética del modal será igual que los descriptos previamente. 

Log de errores: esta sección constará de una tabla en que se podrán visualizar los errores de ejecución de los agentes. La tabla seguirá la misma estética general que las anteriores para mantener uniformidad en la aplicación. Esto implica que tendrá un título, encabezado e ícono en cada columna y un dropdown sobre su extremo derecho. Este menú incluirá dos opciones: "Ver detalle" (abre un modal con la traza completa del error) y "Marcar como resuelto". Además, esta tabla integrará una columna en la que se indique si el error fue resuelto o si continúa pendiente de resolución, mostrada como una lista de verificación, y badges de colores que indiquen la gravedad del error y su tipo.

## Lista de componentes

- Toggle de cambio de modo oscuro/claro
- Sidebar
- Tarjeta de métricas
- Dropdown de acciones
- Modal 
- Tabla de datos
- Badges de estado
- Lista de verificación


## Stack tecnológico y limitaciones

El prototipo debe utilizar solamente HTML, Tailwind vía CDN y Javascript Vanilla, sin recurrir a frameworks ni backend.

## Otras especificaciones

Todos los datos deben incluirse en el código (hardcodeados), ya que el prototipo no se conectará a API ni backend, y el proyecto debe estar completo.