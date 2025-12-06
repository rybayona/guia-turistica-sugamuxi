# guia-turistica-sugamuxi
Proyecto web para gestionar sitios turísticos en Sugamuxi (Boyacá), con frontend en HTML/CSS/JS (Bootstrap, DataTables, Chart.js, SweetAlert), backend en Flask (Python) y análisis con Pandas. 

Estructura de Archivos:
- index.html: Interfaz principal (forms, tabla, indicadores, gráfico, modals, footer).
- styles.css: Estilos (colores azul oceánico, responsivo).
- SitioTuristico.py: Clase para objetos de sitios (nombre, id, tipo, dificultad, días, notas, provincia).
- app.py: Backend Flask (endpoints CRUD, cálculos max/min/promedio/cantidad).

Explicación del Código:
- Frontend (JS): obtenerDatos() carga lista de sitios, actualiza tabla y gráfico. guardar() crea nuevo via POST. editar() llena modal. actualizar() envía PUT (id no editable para evitar errores). eliminar() envía DELETE. Indicadores se cargan con fetch a endpoints.
- Backend: Lista sitios en memoria (para simpleza; escalar a BD como SQLite). Endpoints: GET lista/cantidad/max/min/promedio (con Pandas para mean), POST crear, PUT actualizar (busca por id), DELETE eliminar.
- Base de Datos: En memoria (lista Python). Para real, agrega SQLite con sqlite3 en app.py (crea tabla, insert/update con queries).

Guía de Uso:
1. Instala dependencias: pip install flask flask-cors pandas.
2. Corre backend: python app.py (puerto 5000).
3. Abre index.html en navegador.
4. Registra sitios: Llena forms, click "Registrar".
5. Edita: Click "Editar" en tabla, modifica (id no cambia), "Guardar cambios".
6. Ve indicadores y gráfico actualizados automáticamente.
