# Registro de cambios — S-IT-3Copiar

Todos los cambios reseñables de S-IT-3Copiar, los más recientes primero.

## v3.3.2.9 — agosto de 2026 · Edición internacional

- **Nuevo:** la herramienta habla cuatro idiomas: alemán, inglés, francés y español. El idioma se elige durante la instalación y puede cambiarse en cualquier momento en ⚙; la selección muestra la bandera correspondiente a cada idioma. El nombre del programa cambia con él: 3Kopier, 3Copy, 3Copier, 3Copiar.
- Están traducidos la interfaz, todos los cuadros de diálogo, los mensajes que aparecen durante la copia, el programador y los registros. Cada idioma tiene su propia página de ayuda; las páginas están enlazadas entre sí.
- Los nombres de archivo y los ajustes son iguales en todos los idiomas (`3Kopier.ini`, perfiles con extensión `.3ko`, carpeta `Logs`): cambiar de idioma no altera los perfiles, filtros ni ajustes existentes.
- **Mejorado:** los ajustes (⚙) se presentan ahora en dos columnas: idioma y escala a la izquierda, conservación y nivel de detalle de los registros a la derecha. La ventana es así bastante más baja y cabe entera en pantalla incluso con una escala alta.
- **Mejorado:** los botones de la barra de perfiles se ajustan a la longitud de su texto, para que quede margen suficiente en cualquier idioma.

## v3.3.2.8 — agosto de 2026

- **Nuevo:** tolerancia de marcas de tiempo frente a las desviaciones en unidades NAS y de red: en el modo «solo si es más reciente», los archivos sin cambios ya no se toman por error como más nuevos a causa de diferencias de segundos ni se copian de nuevo en cada ejecución (tolerancia de 2 segundos, como en Robocopy /FFT).
- **Nuevo:** símbolo 🛡 por perfil (junto a 🚫): ajusta esa tolerancia (Automático / Siempre / Desactivado); «Automático» solo actúa en rutas de red `\\` y viene preseleccionado, «Siempre» ayuda con las unidades de red asignadas a una letra (`X:`, `Y:` …).
- **Mejorado:** las rutas del resumen de tareas ya no se cortan por el borde, sino que se muestran acortadas con limpieza (principio…final); la ruta completa aparece en la información emergente.
- **Corregido:** la ventana de ejecución no podía minimizarse cuando se iniciaba desde la ventana del programador abierta; la cruz de cierre (X) actúa ahora como ⏹ Parar e interrumpe limpiamente solo esa ejecución.

## v3.3.2 — julio de 2026

- **Nuevo:** indicación de velocidad: durante la copia, la línea de estado muestra la tasa de transferencia del momento (por ejemplo `157.4 MB/s`), también en la ventana de progreso del programador.
- **Nuevo:** filtro por tarea (🔰): exclusiones adicionales solo para esa tarea o una regla SOLO («copiar únicamente determinados tipos de archivo»), por ejemplo la tarea 1 solo con `*.pdf`. El símbolo 🔰 se pone verde en cuanto hay una regla definida; las exclusiones de todo el perfil siguen aplicándose además.
- **Nuevo:** nivel de detalle del registro seleccionable (⚙): Compacto (predeterminado) con una línea de resumen por tarea, Detallado con una línea por carpeta; los errores se registran siempre por completo.
- **Nuevo:** cola para el programador: las ejecuciones que coinciden ya no se pierden, sino que se suceden una tras otra; las ventanas de resultado no bloquean la siguiente ejecución y ⏹ Parar solo interrumpe la que está en curso. La ventana de ejecución aparece también en el modo de área de notificación y puede minimizarse; las interrupciones figuran en el registro como «FAZIT (ABGEBROCHEN)».

## v3.3.1 — julio de 2026 · Cambio a Python

- Cambio completo de AutoIt a Python: manejo y funcionamiento sin variación, los archivos `3Kopier.ini` y los perfiles `.3ko` existentes siguen funcionando sin ajuste alguno.
- Las copias se realizan en segundo plano: la interfaz sigue respondiendo incluso con muchísimos archivos o unidades de red lentas; copia por bloques, «Parar» surte efecto de inmediato.
- **Nuevo:** programador automático: ejecutar perfiles según un horario en segundo plano, con modo silencioso y funcionamiento en el área de notificación con inicio automático.
- **Nuevo:** lista de exclusiones: dejar fuera de la copia archivos y carpetas enteras (cachés de navegador, archivos temporales, formatos de imagen grandes); con valores predeterminados de fábrica, adaptables por perfil.
- **Nuevo:** suspensión después de copiar como alternativa al apagado (ambas opciones se excluyen mutuamente).
- Nuevos ajustes (⚙): escala del 90 al 200 %, conservación de los registros (de 1 día a ilimitado) con limpieza inmediata; los registros son ahora un archivo propio por ejecución en la carpeta `Logs`.
- Ventana de resultado renovada (una columna por tarea); la lista desplegable de perfiles carga de inmediato, sin botón «Cargar»; las rutas muy largas se muestran acortadas (principio…final), con la ruta completa en la información emergente.
- Rutas de red y NAS (UNC) mejoradas, cálculo del volumen de datos sin bloqueos; el balance figura ahora arriba; correcciones menores de disposición; se adjunta `Lizenz.txt`.

## v3.2.1 — versión AutoIt

- Tratamiento automático de rutas largas (MAX_PATH): las rutas de destino a partir de 260 caracteres se acortan automáticamente, primero el nombre del archivo y, si hace falta, también la última subcarpeta. Los nombres acortados reciben la marca `-3k`.
- El volumen de datos se tiene en cuenta correctamente también con rutas largas, tanto en la indicación como en la barra de progreso.
- Tamaño del registro limitado automáticamente a 512 KB: se eliminan las entradas más antiguas y se conservan las ejecuciones actuales.

## v3.2.0 — versión AutoIt

- Las opciones de sobrescribir y mover por tarea se guardan ahora tanto en el archivo INI como en los perfiles `.3ko`.
- Las carpetas de destino se crean antes de la comprobación; las rutas de red se omiten al calcular el volumen de datos, sin bloqueos.
- Correcciones visuales: espaciado del encabezado, anchos de las etiquetas y posición de las casillas de verificación revisados.

---

© 2026 Sattler IT-Service, Greifenstein · Autor: Hans Udo Sattler
