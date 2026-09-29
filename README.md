# Objetivo

Aplicar conocimientos de tratamiento de imágenes y programación limpia sobre el contexto del sistema portuario.

## Introducción y Contexto del problema


### Sprint 2 — Desarrollar

Los radares ubicados en los accesos a los muelles capturan evidencia fotográfica de las infracciones de velocidad. Las cámaras asociadas toman fotografías de la zona de proa donde está pintada la matrícula del buque. En algunos casos el sistema recorta automáticamente la zona de matrícula (`plates`); en otros, entrega la imagen completa (`completes`).

El sistema presenta las siguientes limitaciones:
- No todas las infracciones tienen imagen asociada.
- No todas las imágenes corresponden a una infracción real (falsos positivos del radar).
- Puede haber errores de detección óptica: imágenes borrosas, nocturnas o tomadas a gran distancia.

El objetivo es: **¿qué infracciones tienen evidencia visual válida?**

Datasets necesarios:
- Dataset procesado en Sprint 1.
- [Dataset de imágenes](https://github.com/HAD141/datasets/raw/refs/heads/main/TrabajosPracticos/port_log/port_log_images.zip): `https://github.com/HAD141/datasets/raw/refs/heads/main/TrabajosPracticos/port_log/port_log_images.zip`
