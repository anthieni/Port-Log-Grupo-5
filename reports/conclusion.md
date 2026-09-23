# Conclusión

## Evaluación de la calidad del dataset heredado

El dataset original contenía **1.500 registros**. Luego del proceso de limpieza,
validación y filtrado quedaron **475 registros correspondientes a infracciones**,
por lo que se excluyeron **1.025 registros, equivalentes al 68,33 % del total
original**. Esta reducción no debe interpretarse únicamente como eliminación de
datos erróneos, ya que el proceso también contempló el filtrado de registros que
no constituían una infracción según el criterio de exceso de velocidad establecido.

Aun dentro del conjunto final se identificaron problemas de calidad. Se detectaron
**31 registros con fecha inválida (6,53 %)** y **27 registros con hora de ingreso
inválida (5,68 %)**. Asimismo, en el dataset original se encontraron valores nulos
en campos relevantes: 24 en `radar_id`, 19 en `matricula`, 16 en
`estado_despacho` y 13 en `hora_egreso`.

Por lo tanto, los principales problemas observados estuvieron relacionados con
fechas y horarios inválidos, además de campos incompletos. Esto evidencia la
necesidad de validar y normalizar la información antes de utilizarla para análisis.

## Patrones de infracción detectados

Sobre las **475 infracciones** analizadas se observaron determinados patrones.
El turno con mayor concentración fue la **Tarde**, con el **26,74 %** de las
infracciones. El **MUELLE-C** presentó la mayor cantidad de casos, concentrando
el **16,84 %**, mientras que **TRIGO** fue el tipo de carga más frecuente entre
los registros infractores, representando el **15,58 %**.

Estos resultados muestran que las infracciones no se distribuyen de manera
completamente uniforme entre los distintos turnos, muelles y tipos de carga.
La identificación de estas concentraciones puede servir como punto de partida
para profundizar el análisis de las operaciones portuarias.

## Impacto de incorporar los datos sin limpieza previa

Incorporar directamente los datos del sistema heredado al nuevo sistema, sin un
proceso previo de limpieza y validación, podría afectar la confiabilidad de los
análisis y reportes. Las fechas y horas inválidas podrían distorsionar los análisis
temporales y la asignación de infracciones por turno, mientras que la ausencia de
matrículas podría dificultar la identificación de buques reincidentes.

Del mismo modo, campos incompletos como `radar_id`, `estado_despacho` o
`hora_egreso` podrían limitar distintos análisis operativos. Migrar los datos sin
controles previos implicaría trasladar al nuevo sistema los problemas existentes
en la fuente original y podría generar indicadores, promedios y rankings basados
en información incompleta o inconsistente.

## Propuesta de mejora

Como mejora concreta se propone incorporar **validaciones automáticas en el
momento de la captura de los datos**. El nuevo sistema debería controlar el
formato y la validez de fechas y horarios, validar el formato de las matrículas
y establecer como obligatorios aquellos campos necesarios para la operación y
los análisis posteriores.

También sería conveniente utilizar listas de opciones predefinidas para variables
categóricas como muelle, tipo de carga, origen y estado de despacho, evitando
diferencias producidas por el ingreso manual de texto.

Finalmente, para variables numéricas como la velocidad de ingreso, podrían
incorporarse controles de rango y reglas automáticas que adviertan sobre valores
anómalos antes de guardar el registro. Estas medidas permitirían mejorar la
calidad de los datos desde su origen y reducir la necesidad de realizar
correcciones posteriores.
