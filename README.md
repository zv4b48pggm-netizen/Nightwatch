# Nightwatch · Centro de inteligencia urbana

Dashboard que analiza incidentes de crimen de Chicago con datos abiertos reales: mapa de calor, las 5 zonas más calientes por vecindario y un puntaje de riesgo según la hora del día.

## Cómo correrlo
- **Local:** abre `index.html` en el navegador, o corre `python -m http.server` y entra a `http://localhost:8000`.
- **En línea:** súbelo a un repo de GitHub y activa **GitHub Pages**. Carga los datos en vivo del [Chicago Data Portal](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2).
- Si no hay conexión al portal, usa datos de ejemplo generados para que el demo siempre funcione.

## Funciones (Fase 1)
- Descarga hasta 6,000 incidentes recientes desde la API Socrata
- Mapa dibujado en Canvas (sin librerías), en modo calor o puntos
- Zonas calientes agrupadas por vecindario
- Riesgo por hora: compara la actividad de una hora (±1 hora) con el promedio del día
- Filtro por tipo de incidente y carga de tus propios datos en CSV

## Plan del proyecto
| Fase | Qué se agrega |
|---|---|
| 1 | Dashboard en el navegador con datos abiertos (este repo) |
| 2 | API en FastAPI + PostgreSQL/PostGIS, carga diaria de datos, endpoints `/incidents` y `/hotspots` |
| 3 | Modelo predictivo por celda y hora (scikit-learn / LightGBM), evaluado con semanas que no vio |
| 4 | React + Mapbox, alertas en tiempo real (WebSockets), cuentas de usuario, pruebas, Docker y CI/CD |

## Tecnología
HTML, CSS, JavaScript (Canvas, Fetch API, ResizeObserver) y la API de datos abiertos Socrata.
