# Editor M3U Pro+ (Modernizado Inter)

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

Un potente editor de listas de reproducción M3U/M3U8 del lado del cliente que se ejecuta completamente en tu navegador web. Carga, edita, organiza, valida, compara y guarda tus listas M3U con una interfaz moderna e intuitiva. No requiere procesamiento del lado del servidor y guarda tu sesión localmente.

## ✨ Características Principales

*   **Operaciones de Archivo:**
    *   Cargar archivos M3U/M3U8 usando el selector de archivos.
    *   Crear nuevas listas de reproducción desde cero (limpiando la sesión anterior).
    *   Guardar listas modificadas localmente (`_editada.m3u`/`_editada.m3u8`), respetando el orden de grupos personalizado.
*   **Edición Avanzada de Canales (Panel Editor):**
    *   Añadir nuevos canales directamente desde la cabecera.
    *   Editar detalles de canales: Nombre, URL, Título de Grupo, Logo TVG, ID TVG, Número de Canal (`ch-number`).
    *   Editar propiedades específicas de KODI (`inputstream.adaptive.license_type`, `inputstream.adaptive.license_key`, `inputstream.adaptive.stream_headers`).
    *   Editar opciones de VLC (`http-user-agent`).
    *   Marcar/desmarcar como **Favorito**.
    *   Marcar/desmarcar como **Oculto** (los canales ocultos no se muestran ni se guardan).
    *   **Acciones de Grupo:**
        *   Aplicar ajustes KODI DRM o VLC User-Agent a todos los canales del mismo grupo.
        *   Mover el canal al principio de su grupo actual.
        *   Mover el canal a un grupo diferente.
        *   Copiar el canal a otro grupo.
    *   Eliminar el canal actual.
    *   Vista previa de logo con opción de ampliar en lightbox.
*   **Organización y Gestión:**
    *   Ver canales en una tabla clara y ordenable por múltiples columnas (Nombre, URL, ID TVG, Grupo, # Canal, Estado).
    *   **Reordenar arrastrando y soltando** canales directamente en la tabla, incluso entre grupos.
    *   Filtrar canales por `group-title` usando un desplegable autogenerado.
    *   Filtrar para mostrar **Solo Favoritos**.
    *   Búsqueda de texto libre (busca en nombre, URL, grupo, ID TVG).
    *   **Gestión de Grupos:**
        *   Modal dedicado para **reordenar grupos arrastrando y soltando**, afectando la vista de tabla y la estructura del archivo guardado.
        *   **Editar detalles de grupo:** Renombrar `group-title` y asignar/cambiar `group-logo` para todos los canales de ese grupo.
        *   Eliminar grupos (con opción de eliminar también todos sus canales).
        *   Añadir nuevos grupos directamente desde la cabecera o desde el modal de gestión.
        *   Agrupar canales visualmente en la tabla con **cabeceras colapsables** (estado guardado en sesión).
        *   Botones para **Expandir/Colapsar todos los grupos**.
*   **Selección y Edición Múltiple:**
    *   Seleccionar múltiples canales usando checkboxes.
    *   Seleccionar/deseleccionar todos los canales visibles.
    *   **Modal de Edición Múltiple:** Aplicar cambios a todos los canales seleccionados:
        *   Mover a un grupo específico.
        *   Marcar/desmarcar como Favorito.
        *   Marcar/desmarcar como Oculto.
    *   Eliminar todos los canales seleccionados con confirmación.
    *   Limpiar selección actual.
*   **Herramientas y Validación:**
    *   **Validar URLs:** Comprobar el estado de las URLs de canales HTTP/HTTPS (petición HEAD `no-cors`, limitado por servidor; muestra estado Activo/Inactivo/Validando/N/D).
    *   **Buscar Duplicados:** Identificar canales que comparten la misma URL. Modal para ver duplicados y opción para eliminar selectivamente (conservando el primero) o todos los duplicados listados.
    *   **Comparar Listas:** Cargar un segundo archivo M3U para compararlo con la lista actual (basado en URL). Muestra canales únicos en cada lista y canales comunes (resaltando diferencias en nombre/grupo).
    *   **Fusionar Listas:** Opción para añadir canales desde la lista de comparación que faltan (por URL) en la lista actual.
    *   **Asignar Logos/EPG:**
        *   Cargar un archivo EPG XML externo (vía proxy simple) para extraer IDs, nombres y logos.
        *   Comparar nombres de canal M3U con nombres del EPG (usando coeficiente Dice) para encontrar coincidencias.
        *   Mostrar sugerencias de logo basadas en la similitud de nombres (>70%).
        *   Aplicar logos sugeridos individualmente o todos a la vez.
        *   Rechazar sugerencias individuales.
*   **Experiencia de Usuario:**
    *   Interfaz de usuario moderna (fuente Inter, iconos FontAwesome).
    *   Diseño adaptable (responsive).
    *   Notificaciones (toast) para feedback de acciones (éxito, error, info).
    *   **Modales de Confirmación** para acciones destructivas o masivas.
    *   **Persistencia de Sesión Robusta (IndexedDB):** Guarda automáticamente la lista actual, orden de canales/grupos, filtros, grupos colapsados, etc., en la base de datos local del navegador. Pregunta si restaurar la sesión al volver a abrir.
    *   Opción para **limpiar todos los datos de sesión** almacenados.
    *   **Barra Lateral Colapsable:** Menú lateral para acciones principales, cuyo estado (expandido/colapsado) se guarda.
    *   **Visor Lightbox:** Permite ampliar logos de canal (tabla, editor) y logos EPG.

## 🚀 Cómo Usar

1.  **Obtén el Archivo:** Descarga el archivo `editor.html` (y los assets asociados si los hubiera) de este repositorio.
2.  **Abrir en Navegador:** Abre el archivo `editor.html` directamente en un navegador web moderno (Chrome, Firefox, Edge recomendado). No se necesita servidor web.
3.  **Cargar, Crear o Restaurar:**
    *   Al iniciar, si se detecta una sesión guardada, te preguntará si deseas restaurarla.
    *   Haz clic en **"Abrir"** (<i class="fas fa-folder-open"></i>) en la barra lateral para cargar un archivo M3U/M3U8.
    *   Haz clic en **"Nueva"** (<i class="fas fa-file-alt"></i>) para empezar una lista vacía (te pedirá confirmación si hay una lista cargada).
4.  **Editar y Organizar:**
    *   La tabla muestra tus canales. Haz clic en las cabeceras (<i class="fas fa-sort"></i>) para ordenar.
    *   Usa la **búsqueda**, el **filtro de grupo**, y el botón de **Favoritos** (<i class="far fa-star"></i>/<i class="fas fa-star"></i>) para navegar.
    *   Haz clic en una fila de canal para seleccionarla y editarla en el **Panel Editor** de la derecha.
    *   Usa los **checkboxes** para seleccionar múltiples canales y luego los botones **"Multi-Editar"** o **"Eliminar Sel."**.
    *   Arrastra el icono <i class="fas fa-grip-lines"></i> para reordenar canales.
    *   Haz clic en las cabeceras de grupo (<i class="fas fa-chevron-down"></i>/<i class="fas fa-chevron-right"></i>) para colapsar/expandir, o usa los botones globales (<i class="fas fa-expand-arrows-alt"></i> / <i class="fas fa-compress-arrows-alt"></i>).
    *   Usa **"Orden Grupos"** (<i class="fas fa-layer-group"></i>) para gestionar grupos.
5.  **Usar Herramientas:** Accede a **"Validar URLs"** (<i class="fas fa-check-double"></i>), **"Duplicados"** (<i class="fas fa-copy"></i>), **"Comparar"** (<i class="fas fa-exchange-alt"></i>) y **"Asignar EPG/Logos"** (<i class="fas fa-tv"></i>) desde la barra lateral o cabecera.
6.  **Guardar:** Haz clic en **"Guardar"** (<i class="fas fa-save"></i>) para descargar tu lista modificada. La sesión también se guarda automáticamente en segundo plano.
7.  **Otros:** Usa **"Borrar Sesión"** (<i class="fas fa-trash-restore"></i>) para limpiar los datos locales. Usa el botón <i class="fas fa-bars"></i> para colapsar/expandir la barra lateral.

## 🛠️ Tecnologías Utilizadas

*   HTML5
*   CSS3 (con Variables CSS)
*   JavaScript Vanilla (ES6+)
*   **IndexedDB** (para persistencia de sesión principal)
*   LocalStorage (para estado de la barra lateral)
*   [FontAwesome](https://fontawesome.com/) para iconos
*   [SortableJS](https://github.com/SortableJS/Sortable) para arrastrar y soltar

## 🤝 Contribuciones

¡Las contribuciones, issues y solicitudes de características son bienvenidas!

1.  Haz Fork del Proyecto
2.  Crea tu Rama de Característica (`git checkout -b feature/AmazingFeature`)
3.  Confirma tus Cambios (`git commit -m 'Add some AmazingFeature'`)
4.  Empuja a la Rama (`git push origin feature/AmazingFeature`)
5.  Abre un Pull Request
