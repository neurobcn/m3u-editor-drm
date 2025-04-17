# Editor M3U Pro+ (Modernizado Inter)

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT) 

Un potente editor de listas de reproducción M3U/M3U8 del lado del cliente que se ejecuta completamente en tu navegador web. Carga, edita, organiza, valida, compara y guarda tus listas M3U con una interfaz moderna e intuitiva. No requiere procesamiento del lado del servidor.

## ✨ Características Principales

*   **Operaciones de Archivo:**
    *   Cargar archivos M3U/M3U8 usando el selector de archivos.
    *   Crear nuevas listas de reproducción desde cero.
    *   Guardar listas modificadas localmente (`_editada.m3u`/`_editada.m3u8`).
*   **Edición de Canales:**
    *   Añadir nuevos canales manualmente.
    *   Editar detalles de canales existentes: Nombre, URL, Título de Grupo, Logo TVG, ID TVG.
    *   Editar propiedades opcionales de KODI (`inputstream.adaptive.license_type`, `inputstream.adaptive.license_key`, `inputstream.adaptive.stream_headers`).
    *   Eliminar canales individuales o múltiples canales seleccionados.
    *   Menú contextual para acciones rápidas (Editar, Favorito, Cambiar Grupo, Validar, Copiar URL, Eliminar).
*   **Organización y Gestión:**
    *   Ver canales en una tabla clara y ordenable.
    *   **Reordenar arrastrando y soltando** canales directamente en la tabla.
    *   Asignar o cambiar `group-title` para canales (individualmente o en lote para seleccionados).
    *   Marcar/desmarcar canales como **Favoritos** y filtrar la vista para mostrar solo favoritos.
    *   Filtrar canales por `group-title`.
    *   **Gestionar Orden de Grupos:** Interfaz dedicada para reordenar grupos arrastrando y soltando, afectando la vista de tabla y la estructura del archivo guardado.
    *   Editar detalles de grupo globalmente (renombrar `group-title` en todos los canales de ese grupo, establecer `group-logo`).
    *   Agrupar canales visualmente en la tabla con cabeceras colapsables.
*   **Herramientas y Validación:**
    *   **Validar URLs:** Comprobar el estado de las URLs de canales HTTP/HTTPS (comprobación básica con petición HEAD; *puede estar limitado por CORS*).
    *   **Buscar Duplicados:** Identificar canales que comparten exactamente la misma URL y opcionalmente eliminar duplicados, conservando la primera aparición.
    *   **Comparar Listas:** Cargar un segundo archivo M3U para compararlo con la lista actual (basado en URL), mostrando canales únicos en cada lista y canales comunes (resaltando diferencias en nombre/grupo).
    *   **Fusionar Listas:** Opción para añadir canales desde la lista de comparación que faltan en la lista actual.
*   **Experiencia de Usuario:**
    *   Interfaz de usuario moderna inspirada en aplicaciones web contemporáneas (fuente Inter, iconos FontAwesome).
    *   Diseño adaptable (responsive) para usabilidad en diferentes tamaños de pantalla.
    *   Notificaciones (toast) para feedback sobre acciones realizadas.
    *   Indicador de carga para operaciones largas.
    *   **Persistencia de Sesión:** Guarda automáticamente la lista actual y el estado de la interfaz (filtros, orden, grupos colapsados) en el LocalStorage del navegador. Pregunta si restaurar la sesión en la próxima visita.
    *   Opción para borrar los datos de sesión local guardados.

## 🚀 Cómo Usar

1.  **Obtén el Archivo:** Descarga el archivo `editor.html` de este repositorio.
2.  **Abrir en Navegador:** Abre el archivo `editor.html` directamente en un navegador web moderno (como Chrome, Firefox, Edge). No se necesita servidor web.
3.  **Cargar o Crear:**
    *   Haz clic en el botón **"Abrir"** para cargar un archivo M3U o M3U8 existente desde tu ordenador.
    *   Haz clic en el botón **"Nueva"** para empezar una lista vacía.
4.  **Editar y Organizar:**
    *   Usa la tabla para ver los canales. Haz clic en las cabeceras de columna (Nombre, Grupo) para ordenar.
    *   Usa la barra de búsqueda y el desplegable de grupo para filtrar.
    *   Haz clic en los botones de la barra de herramientas o en los botones de acción (<i class="fas fa-edit"></i>, <i class="far fa-star"></i>/<i class="fas fa-star"></i>, <i class="fas fa-trash"></i>) en cada fila para modificar canales.
    *   Haz clic derecho en una fila para el menú contextual.
    *   Arrastra el icono <i class="fas fa-grip-lines"></i> para reordenar canales.
    *   Usa **"Orden Grupos"** para reordenar grupos enteros o editar sus propiedades.
5.  **Usar Herramientas:** Utiliza funciones como **"Validar URLs"**, **"Duplicados"**, y **"Comparar"** mediante los botones de la barra de herramientas.
6.  **Guardar:** Haz clic en el botón **"Guardar"** para descargar tu lista de reproducción modificada como un nuevo archivo.

## 🛠️ Tecnologías Utilizadas

*   HTML5
*   CSS3 (con Variables CSS para tematización)
*   JavaScript Vanilla (ES6+)
*   [FontAwesome](https://fontawesome.com/) para iconos
*   [SortableJS](https://github.com/SortableJS/Sortable) para funcionalidad de arrastrar y soltar

## 🤝 Contribuciones

¡Las contribuciones, issues y solicitudes de características son bienvenidas!

1.  Haz Fork del Proyecto
2.  Crea tu Rama de Característica (`git checkout -b feature/AmazingFeature`)
3.  Confirma tus Cambios (`git commit -m 'Add some AmazingFeature'`)
4.  Empuja a la Rama (`git push origin feature/AmazingFeature`)
5.  Abre un Pull Request
