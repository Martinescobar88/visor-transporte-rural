# Visor de Transporte Rural RM

Visor web (Leaflet) de los recorridos de buses rurales y subsidiados de la Región Metropolitana, corregidos sobre la red vial (octubre 2026). Información referencial, no oficial del MTT.

## Archivos

- `index.html`: el visor completo (diseño y funciones).
- `datos/rutas.geojson`: los 707 recorridos. Campos: `categoria` (Rural corriente, Rural periférico, CTA, CTR, CTE), `servicio`, `nombre`, `operador`, `sentido` (Ida/Regreso), `recorrido` (origen–destino), `comunas`, `zona`, `km`.
- `datos/comunas.geojson`, `datos/perimetros.geojson`, `datos/vias.geojson`: capas de referencia.
- `datos/localidades.geojson`: entidades rurales del Censo 2024 (en el mapa se dibujan solo los caseríos; todas se pueden buscar).

Para actualizar una capa basta con reemplazar su archivo `.geojson`, manteniendo los mismos nombres de campos (WGS84, EPSG:4326). Desde QGIS: clic derecho en la capa > Exportar > Guardar objetos como > GeoJSON.

## Publicar en GitHub Pages

1. Crear una cuenta gratis en github.com.
2. Crear un repositorio nuevo, público (por ejemplo `visor-transporte-rural`).
3. En el repositorio: Add file > Upload files, y arrastrar `index.html` y la carpeta `datos` completa. Commit changes.
4. Settings > Pages > Source: "Deploy from a branch", rama `main`, carpeta `/ (root)`. Guardar.
5. En 1 a 2 minutos el visor queda en `https://<usuario>.github.io/visor-transporte-rural/`.

Abrir `index.html` con doble clic en el computador no funciona (el navegador bloquea la carga de los archivos de datos). Para probar en local: en la carpeta, `python -m http.server` y abrir `http://localhost:8000`.
