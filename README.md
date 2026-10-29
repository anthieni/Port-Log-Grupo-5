

# Objetivo

Aplicar conocimientos de versionado, organización y análisis exploratorio de datos con pandas sobre un dataset real de operaciones portuarias.

## Introducción y Contexto del problema

### Sprint 1

El Puerto Fluvial de Rosario es uno de los complejos portuarios más importantes de América del Sur, siendo el principal punto de exportación de granos y derivados de la Argentina. Diariamente ingresan y egresan decenas de buques de distintas banderas con cargas de diverso tipo.

El sistema de registro de movimientos portuarios fue migrado recientemente desde un sistema heredado de los años '90. Ese sistema acumuló durante décadas inconsistencias de formato en fechas, matrículas de buques y valores numéricos fuera de rango, generando registros que no pueden incorporarse directamente al nuevo sistema.

Nuestro equipo fue contratado para analizar y depurar los datos del sistema antiguo.

Descargar el dataset [port_movements](https://raw.githubusercontent.com/HAD141/datasets/refs/heads/main/TrabajosPracticos/port_log/port_movements.csv)  

`https://raw.githubusercontent.com/HAD141/datasets/refs/heads/main/TrabajosPracticos/port_log/port_movements.csv`

---

<!-- SPRINT_2_START -->
## Sprint 2 - Tratamiento de imágenes y validación visual

### Objetivo
Relacionar las imágenes capturadas por el sistema portuario con las infracciones procesadas en Sprint 1 para identificar qué registros poseen evidencia visual válida.

### Flujo de trabajo
1. Descargar y clasificar las imágenes en `plates` y `completes`.
2. Analizar resolución, área y tamaño de los grupos.
3. Preprocesar las imágenes: escala de grises, ecualización, suavizado y Canny.
4. Ejecutar OCR sobre imágenes ecualizadas, conservando Canny como producto de análisis de bordes.
5. Asociar imágenes e infracciones mediante matching uno-a-uno con umbral mínimo del 75 %.
6. Calcular métricas y diagnosticar las condiciones que afectan el reconocimiento.

### Estructura utilizada
- `port_log/data/raw/`: datos e imágenes originales.
- `port_log/data/interim/`: resultados intermedios y `group_images.json`.
- `port_log/data/processed/`: dataset final con asociaciones de imágenes.
- `port_log/reports/`: reportes del proyecto.
<!-- SPRINT_2_END -->

<!-- SPRINT_3_START -->
## Sprint 3

En este sprint se incorpora persistencia relacional con PostgreSQL/Supabase,
versionado de datos con DVC y búsqueda visual de buques con OpenCLIP y ChromaDB.

El modelo considera al radar como un dispositivo móvil: un movimiento ocurre
en un único muelle y un mismo radar puede registrar movimientos en distintos
muelles.

Los archivos pesados y el dataset procesado final se versionan con DVC,
mientras que Git mantiene código, documentación y archivos `.dvc`.
<!-- SPRINT_3_END -->
