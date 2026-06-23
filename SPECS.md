# SPECS - Panel de Alquiler de Agentes de IA

## 1. Estructura base del layout

Definir primero los componentes globales que existen en toda la aplicación:

- `aside` de navegación lateral.
- `header` superior.
- Contenedor principal `main`.
- Sistema general de layout/grid para organizar vistas y bloques.

### Requisitos de layout

- El `aside` debe contener navegación por secciones con estado activo visible.
- El `header` debe permanecer consistente entre vistas.
- `main` debe ser el área de render principal para el contenido de cada sección.
- El grid debe permitir tarjetas, tablas y listas sin romper alineación.

## 2. Componentes globales reutilizables

Componentes compartidos entre múltiples secciones:

- Tarjeta de métrica (`Metric Card`).
- Tabla base.
- Dropdown de acciones.
- Modal.
- Badge de estado.
- Toggle de tema claro/oscuro.
- Lista colapsable de skills.

### Sidebar

- Uso: navegación principal global.
- Contenido: logo, enlaces a secciones y estado activo.
- Comportamiento: persistente en desktop; colapsable en móvil.

### Metric Card

- Uso: Dashboard.
- Contenido: etiqueta, valor e icono opcional.
- Comportamiento: cambia estilo según tipo de métrica.

### Dropdown de acciones

- Uso: tablas y listas.
- Contenido: menú contextual con opciones.
- Comportamiento: abre/cierra con botón y se cierra al hacer clic fuera.

### Modal

- Uso: detalle de usuario, agente, contrato y error.
- Contenido: título, cuerpo principal y cierre.
- Comportamiento: overlay con backdrop clicable y bloqueo de scroll/fondo.

## 3. Componentes por sección

### Dashboard

- Tarjetas de métricas.
- Placeholder de gráfico.

### Gestión de usuarios

- Tabla principal de usuarios.
- Modal de detalle de usuario.

### Gestión de agentes

- Lista de agentes.
- Skills expandibles/colapsables por agente.
- Modal de configuración de agente.

### Skills

- Catálogo/listado de skills.
- Explicación contextual por skill.

### Contrataciones

- Tabla de contratos.
- Modal con desglose del contrato.

### Log de errores

- Tabla o lista de errores.
- Badges por severidad.
- Modal con traza detallada.

## 4. Estados e interacciones

Describir y mantener consistencia en:

- Estados `hover` y `focus` para elementos interactivos.
- Apertura/cierre de dropdowns y modales.
- Transiciones visuales entre estados.
- Backdrop clicable para cerrar modales.
- Estados colapsado/expandido (sidebar y skills).
- Diferencias visuales y de contraste entre modo claro y oscuro.

## 5. Responsive behavior

Definir adaptación por breakpoint (móvil, tablet, desktop):

- Sidebar colapsable en pantallas pequeñas.
- Tablas con scroll horizontal cuando no haya ancho suficiente.
- Tarjetas distribuidas en menos columnas en móvil/tablet.
- Modales legibles, centrados y con márgenes adaptativos.
- Layout general estable sin solapamientos entre header, sidebar y contenido.
