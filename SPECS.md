# SPECS - Panel de Alquiler de Agentes de IA

## 1. Descripción del producto

AgentHub es un panel de administración diseñado para gestionar agentes de inteligencia artificial, sus skills, sus contrataciones y el seguimiento de incidencias operativas. El sistema está orientado a una persona administradora que necesita supervisar el estado general de la plataforma, configurar agentes, revisar usuarios y consultar errores desde una única interfaz.

## 2. Tecnologías y restricciones

El prototipo deberá desarrollarse bajo las siguientes condiciones:

- HTML para la estructura de la interfaz.
- Tailwind CSS cargado exclusivamente mediante CDN.
- JavaScript vanilla para toda la interactividad.
- Sin frameworks frontend.
- Sin jQuery.
- Sin backend.
- Sin herramientas de build.
- Sin archivos CSS personalizados.
- Sin atributos style en línea.
- Todos los datos del prototipo deberán estar hardcodeados.

## 3. Estructura general del panel

La interfaz deberá organizarse como un panel administrativo con estructura consistente entre secciones.

### Layout global

- Una barra lateral persistente con enlaces a las seis secciones principales.
- Una barra superior con contexto de la vista actual y controles globales.
- Un área principal de contenido para renderizar tarjetas, tablas, listas y modales.
- Una distribución responsive que mantenga legibilidad en móvil, tablet y desktop.

### Navegación lateral

- Deberá incluir el nombre o logotipo de AgentHub.
- Deberá mostrar enlaces a Dashboard, Gestión de usuarios, Gestión de agentes, Skills, Contrataciones de agentes y Log de errores.
- Deberá indicar visualmente cuál es la sección activa.
- En desktop deberá permanecer visible.
- En móvil deberá poder colapsarse y expandirse.

### Barra superior

- Deberá mantenerse consistente en todas las secciones.
- Deberá incluir el título de la vista actual.
- Deberá incluir un toggle de modo claro/oscuro.

## 4. Inventario de componentes reutilizables

El prototipo deberá reutilizar, como mínimo, los siguientes componentes:

- Sidebar de navegación.
- Header superior.
- Tarjeta de métrica.
- Tabla base.
- Dropdown de acciones.
- Modal con backdrop.
- Badge de estado.
- Badge de severidad.
- Lista colapsable de skills.
- Toggle de modo claro/oscuro.
- Botones primarios y secundarios.
- Textarea para configuración.
- Bloque visual para gráfico o placeholder.

Todos los componentes deberán mantener consistencia visual en espaciado, bordes, contraste, tipografía y estados interactivos.

## 5. Especificaciones por sección

### Dashboard

- Deberá mostrar cuatro tarjetas de métricas en una cuadrícula responsive.
- Las métricas serán: ingresos totales, pérdidas por descuentos, agentes activos y agentes fallando.
- Cada tarjeta deberá incluir icono, etiqueta y valor hardcodeado.
- Cada tarjeta deberá usar un color de acento distinto según el tipo de métrica.
- Debajo de las tarjetas deberá existir un bloque de ancho completo que represente un gráfico de actividad semanal.
- El gráfico podrá resolverse como placeholder visual, siempre que sea identificable como panel analítico.

### Gestión de usuarios

- Deberá incluir una tabla con al menos 5 usuarios hardcodeados.
- Cada fila deberá mostrar nombre, email, plan y badge de estado.
- Cada fila deberá incluir un dropdown con las opciones Ver detalle y Eliminar.
- La acción Ver detalle deberá abrir un modal con información ampliada del usuario.
- El modal deberá incluir datos completos visibles y consistentes con la fila seleccionada.
- La tabla deberá seguir siendo usable en pantallas pequeñas mediante scroll horizontal si fuera necesario.

### Gestión de agentes

- Deberá incluir un listado con al menos 4 agentes hardcodeados.
- Cada agente deberá mostrar nombre, propietario, badge de estado y skills asociadas.
- Cada agente deberá incluir una lista de skills expandible y colapsable.
- La expansión de skills deberá tener una transición visual suave.
- Cada agente deberá incluir un dropdown con las opciones Configurar y Eliminar.
- La acción Configurar deberá abrir un modal con el prompt de sistema del agente dentro de un textarea editable.

### Skills

- Deberá incluir un catálogo con al menos 4 skills hardcodeadas.
- Cada skill deberá mostrar nombre, descripción breve y número de agentes que la tienen habilitada.
- La sección deberá incluir una explicación breve sobre qué es una skill en el contexto de AgentHub.
- Cada skill deberá incluir un dropdown con las opciones Ver detalle y Eliminar.
- La organización visual deberá ser consistente con el resto del sistema.
- La sección deberá diferenciarse claramente de la vista de agentes, aunque comparta temática relacionada.

### Contrataciones de agentes

- Deberá incluir una tabla con al menos 4 contratos hardcodeados.
- Cada contrato deberá mostrar cliente, agente, skills contratadas, fecha de inicio, fecha de fin e importe pagado.
- Cada fila deberá incluir un dropdown con la opción Ver detalle.
- La acción Ver detalle deberá abrir un modal con el desglose completo del contrato.
- El modal deberá mostrar las skills contratadas desglosadas y sus precios individuales.
- El importe pagado deberá tener jerarquía visual suficiente dentro de la tabla o del detalle.

### Log de errores

- Deberá incluir al menos 6 entradas de error hardcodeadas.
- Cada entrada deberá mostrar timestamp, nombre del agente, tipo de error y descripción breve.
- El tipo de error deberá representarse mediante un badge con código de color.
- Cada entrada deberá incluir un dropdown con las opciones Ver detalle y Marcar como resuelto.
- La acción Ver detalle deberá abrir un modal con información ampliada del incidente.
- La sección deberá transmitir visualmente contexto operativo y prioridad.

## 6. Interacciones globales

Toda la interactividad deberá implementarse únicamente con JavaScript vanilla.

### Dropdowns

- Cada dropdown deberá abrirse desde un botón de acciones visible.
- Solo deberá permanecer abierto el menú correspondiente al elemento interactuado.
- Todos los dropdowns deberán cerrarse al hacer clic fuera de su área.

### Modales

- Los modales deberán abrirse desde acciones de detalle o configuración.
- Todos los modales deberán tener botón de cierre visible.
- Todos los modales deberán cerrarse al hacer clic sobre el backdrop.
- Los modales deberán mostrarse centrados y mantenerse legibles en cualquier tamaño de pantalla.

### Elementos colapsables

- La lista de skills por agente deberá poder expandirse y colapsarse.
- El cambio de estado deberá comunicarse mediante una transición visible.
- El componente deberá integrarse visualmente con el resto del panel.

### Modo claro y oscuro

- El panel deberá incluir un toggle de tema en la barra superior.
- El cambio de tema deberá afectar a toda la interfaz.
- El tema seleccionado deberá conservarse al navegar entre secciones.
- El modo oscuro deberá implementarse usando las utilidades dark de Tailwind.

## 7. Comportamiento responsive

El prototipo deberá adaptarse a distintos tamaños de pantalla.

- En desktop, la sidebar deberá permanecer visible y el contenido deberá aprovechar el ancho disponible.
- En tablet, las tarjetas y bloques deberán reorganizarse sin perder alineación ni jerarquía.
- En móvil, la sidebar deberá colapsarse y el contenido deberá apilarse verticalmente.
- Las tablas deberán permitir scroll horizontal cuando no haya ancho suficiente.
- Las tarjetas del dashboard deberán reducir columnas en pantallas pequeñas.
- Los modales deberán respetar márgenes adecuados dentro del viewport.
- No deberá haber solapamientos entre sidebar, header y contenido principal.

## 8. Estados visuales

- Todos los elementos interactivos deberán tener estados hover y focus visibles.
- Los badges deberán mantener contraste suficiente en modo claro y oscuro.
- Las tarjetas, tablas, listas y modales deberán compartir un lenguaje visual consistente.
- La interfaz deberá priorizar legibilidad, jerarquía y claridad escaneable.

## 9. Criterios de aceptación

1. Existe un archivo SPECS.md en la raíz del repositorio.
2. La especificación describe qué es AgentHub y quién es la persona usuaria administradora.
3. La especificación declara explícitamente el uso de HTML, Tailwind vía CDN y JavaScript vanilla.
4. La especificación declara explícitamente que no se permiten frameworks, backend, estilos inline ni CSS personalizado.
5. La especificación incluye un inventario de componentes reutilizables.
6. Cada una de las seis secciones funcionales contiene al menos tres especificaciones concretas y verificables.
7. El Dashboard define cuatro métricas concretas y un bloque de actividad semanal.
8. La Gestión de usuarios define una tabla con al menos 5 filas y un modal de detalle.
9. La Gestión de agentes define al menos 4 agentes, una lista de skills colapsable y un modal de configuración.
10. La sección Skills define al menos 4 skills y una explicación contextual dentro de la vista.
11. La sección Contrataciones define al menos 4 contratos con modal de desglose.
12. La sección Log de errores define al menos 6 entradas con badges por tipo de error.
13. La especificación incluye comportamientos verificables para dropdowns.
14. La especificación incluye comportamientos verificables para modales.
15. La especificación incluye comportamientos verificables para elementos colapsables.
16. La especificación incluye el comportamiento del modo claro/oscuro a nivel global.
17. La especificación define requisitos responsive para móvil, tablet y desktop.
18. Todos los datos del prototipo quedan definidos como hardcodeados.
