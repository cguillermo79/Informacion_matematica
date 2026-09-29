# Proyecto integrador FIRELAB_Loja — Matemática

## Propósito

Cada equipo utilizará una base territorial de FIRELAB_Loja para formular y resolver un problema matemático aplicado. El trabajo debe transformar datos reales en cantidades, relaciones, funciones, índices o modelos sencillos que puedan explicarse, calcularse y verificarse.

El proyecto se desarrolla de manera acumulativa: formulación y selección de variables en la Unidad 1, construcción y validación del procedimiento en la Unidad 2, y resultados finales, interpretación y conclusiones en la Unidad 3.

## Base autorizada y alcance

- Fuente: `dataset_maestro_firelab_loja_2019_2025_v1_1_0.csv`.
- SHA-256 de la fuente: `890423faf91207aa271feb9878b1b379e309c156e8e7128af380a5c1afe674b6`.
- Unidad de observación: una **celda espacial de 500 m en un mes**.
- Periodo: enero de 2019 a diciembre de 2024 (72 meses).
- El año 2025 no está incluido y no debe incorporarse al análisis.
- Los archivos conservan los valores originales; toda transformación deberá quedar expresada mediante fórmulas y código reproducible.

## Asignación de equipos

| Equipo | Tema | Zona exclusiva | Registros | Celdas | Columnas | Archivo |
|---:|---|---|---:|---:|---:|---|
| 1 | Relieve y accesibilidad | Norte | 288.072 | 4.001 | 66 | `equipo_01_relieve_zona_norte/base_matematica_equipo_01_relieve_zona_norte_2019_2024.csv` |
| 2 | Relieve y accesibilidad | Sur | 287.712 | 3.996 | 66 | `equipo_02_relieve_zona_sur/base_matematica_equipo_02_relieve_zona_sur_2019_2024.csv` |
| 3 | Cobertura vegetal y uso del suelo | Norte | 288.072 | 4.001 | 53 | `equipo_03_cobertura_zona_norte/base_matematica_equipo_03_cobertura_zona_norte_2019_2024.csv` |
| 4 | Cobertura vegetal y uso del suelo | Sur | 287.712 | 3.996 | 53 | `equipo_04_cobertura_zona_sur/base_matematica_equipo_04_cobertura_zona_sur_2019_2024.csv` |
| 5 | Clima y condiciones atmosféricas | Norte | 288.072 | 4.001 | 57 | `equipo_05_clima_zona_norte/base_matematica_equipo_05_clima_zona_norte_2019_2024.csv` |
| 6 | Clima y condiciones atmosféricas | Sur | 287.712 | 3.996 | 57 | `equipo_06_clima_zona_sur/base_matematica_equipo_06_clima_zona_sur_2019_2024.csv` |
| 7 | Incendios forestales y riesgo | Loja completo | 575.784 | 7.997 | 41 | `equipo_07_incendios_loja_completo/base_matematica_equipo_07_incendios_loja_completo_2019_2024.csv` |

## Regla territorial para los temas compartidos

Los equipos 1–2, 3–4 y 5–6 comparten **tema y estructura de variables**, pero trabajan territorios diferentes:

- **Norte:** `centro_y_m >= 9555250.0` (4.001 celdas).
- **Sur:** `centro_y_m < 9555250.0` (3.996 celdas).
- **Loja completo:** 7.997 celdas; corresponde únicamente al equipo 7.

La base ya está filtrada. No es necesario volver a dividirla ni agregar una columna de zona.

> **Compartir tema no significa compartir trabajo.** Cada equipo formulará su pregunta para su zona, calculará sus propios resultados y entregará tablas, gráficos, interpretación y conclusiones originales. No se deben unir las bases norte y sur, intercambiar resultados ni completar una zona con datos del equipo par. Una comparación norte–sur solo podrá añadirse al final si el docente la solicita; nunca sustituirá el análisis principal de la zona asignada.

## Trabajo obligatorio para todos los equipos

### 1. Formulación matemática

- Plantear una pregunta vinculada con el tema, la zona y el periodo asignados.
- Definir las magnitudes que intervendrán, sus unidades, dominio y restricciones.
- Escribir las fórmulas antes de programarlas y explicar qué representa cada símbolo.
- Proponer al menos una relación, indicador, función o regla de clasificación que contribuya a responder la pregunta.

### 2. Preparación y validación

- Verificar dimensiones, tipos, valores faltantes, duplicados y rango temporal.
- Comprobar que todos los registros cumplen la regla de la zona asignada.
- Revisar las columnas de calidad antes de usar una medición: cobertura, número de píxeles, disponibilidad, soporte, observabilidad o validez.
- Conservar el CSV original. La limpieza, normalización o agregación debe realizarse mediante código y quedar justificada.

### 3. Desarrollo

- Calcular medidas descriptivas que permitan conocer escalas y rangos.
- Mostrar al menos un cálculo manual representativo y verificar que coincide con el resultado del código.
- Aplicar las transformaciones matemáticas seleccionadas: razones, proporciones, tasas, estandarización, funciones, clases o índices compuestos, según corresponda.
- Analizar la sensibilidad del resultado ante un parámetro, umbral o elección de fórmula.
- Interpretar el resultado con sus unidades y dentro de la zona asignada.

### 4. Productos mínimos

- Informe acumulativo con problema, formulación, procedimiento, resultados, limitaciones y conclusiones.
- Script o cuaderno que regenere todas las tablas y figuras.
- Tabla de variables y unidades; tabla de resultados principales; al menos tres visualizaciones pertinentes.
- Evidencia de verificación de fórmulas y control de calidad.
- Defensa individual del procedimiento y de un resultado del equipo.

## Actividades específicas por equipo

### Equipo 1 — Relieve y accesibilidad, zona norte

- Caracterizar elevación, pendiente, orientación, distancia a asentamientos y distancia a vías en las 4.001 celdas del norte.
- Construir un indicador matemático de accesibilidad o dificultad territorial. Si combina variables con escalas distintas, normalizarlas y justificar los pesos.
- Clasificar las celdas en niveles interpretables y analizar cómo cambia el indicador con la pendiente o la elevación.
- Entregar la fórmula completa, un ejemplo manual, distribución del indicador, relación entre dos magnitudes y representación espacial del norte.

### Equipo 2 — Relieve y accesibilidad, zona sur

- Realizar el mismo eje temático exclusivamente con las 3.996 celdas del sur.
- Diseñar y justificar su propio indicador de accesibilidad o dificultad; no copiar coeficientes, cortes ni resultados del equipo 1.
- Evaluar la influencia de pendiente, elevación, vías y asentamientos dentro del sur y comprobar la sensibilidad del indicador a sus pesos o umbrales.
- Entregar la fórmula completa, un ejemplo manual, distribución del indicador, relación entre dos magnitudes y representación espacial del sur.

> Para los equipos 1 y 2, las variables del bloque son estáticas y se repiten durante los 72 meses. El análisis territorial debe usar una sola fila por `cell_id`; repetir cada celda 72 veces no agrega información matemática.

### Equipo 3 — Cobertura vegetal y uso del suelo, zona norte

- Describir la composición de las nueve proporciones MAATE en la zona norte y verificar que su suma sea coherente.
- Construir un indicador justificable de cobertura natural, intervención o condición de vegetación usando proporciones e índices NDVI, NDMI, NBR o NDWI.
- Modelar el comportamiento mensual o anual de al menos un índice y comparar periodos o clases de cobertura.
- Evaluar cómo cambia el resultado al modificar un umbral o la combinación de variables; incluir serie temporal y representación espacial del norte.

### Equipo 4 — Cobertura vegetal y uso del suelo, zona sur

- Desarrollar el análisis exclusivamente para la zona sur y comprobar soporte MAATE y disponibilidad Sentinel-2.
- Construir un indicador propio de cobertura natural, intervención o condición de vegetación; sus parámetros y conclusiones deben derivarse de los datos del sur.
- Modelar el comportamiento temporal de al menos un índice y relacionarlo con una cobertura dominante.
- Evaluar la sensibilidad a un umbral o fórmula; incluir serie temporal y representación espacial del sur.

> Las proporciones MAATE son una referencia basal y no cambian mensualmente. Los índices Sentinel-2 sí varían en el tiempo, pero deben analizarse junto con `disponible_sentinel_t1`, `sentinel_t1_missing`, cobertura válida y `lag_meses`.

### Equipo 5 — Clima y condiciones atmosféricas, zona norte

- Construir perfiles mensuales de precipitación, días secos, días húmedos y viento para la zona norte.
- Formular una función o índice de condición seca/ventosa usando variables compatibles y unidades claramente definidas.
- Comparar el mes actual con los resúmenes `prev2m` y `prev3m` y explicar matemáticamente la diferencia entre valor mensual, promedio o acumulado.
- Identificar máximos, mínimos y periodos críticos; evaluar la sensibilidad del índice y representar su evolución temporal y espacial.

### Equipo 6 — Clima y condiciones atmosféricas, zona sur

- Repetir el eje temático únicamente para la zona sur, con cálculos y parámetros propios.
- Formular una función o índice de condición seca/ventosa y justificar su escala y sus puntos de corte a partir de los datos del sur.
- Analizar valores actuales y antecedentes de dos y tres meses sin sumarlos indebidamente.
- Identificar extremos, evaluar sensibilidad y representar evolución temporal y distribución espacial del sur.

> Para los equipos 5 y 6, los resúmenes móviles comparten meses entre observaciones consecutivas. Además, deben comprobarse `chirps_historia_3m_completa`, `chelsa_historia_3m_completa`, días válidos y disponibilidad antes de calcular el indicador.

### Equipo 7 — Incendios forestales y riesgo, Loja completo

- Usar `y_incendio_ge7_obs90` como definición principal de incendio y calcular frecuencias, proporciones o tasas por mes, año y celda válida.
- Formular un índice de recurrencia o una clasificación matemática de riesgo histórico, explicando denominador, escala y puntos de corte.
- Comparar el resultado principal con los umbrales alternativos `ge7`/`ge8` y `obs80`/`obs95`/`obs100`.
- Presentar un ejemplo manual, serie temporal, distribución espacial y análisis de sensibilidad a los umbrales.

> El análisis principal debe respetar `y_principal_valida`. Las columnas VIIRS de cobertura, disponibilidad y evidencia se conservan para trazabilidad y no deben confundirse con factores causales ni usarse para predecir el resultado del que proceden.

## Archivos auxiliares

- `MANIFIESTO_BASES.csv`: inventario, regla territorial, dimensiones y huellas SHA-256.
- `dataset_maestro_diccionario_grupos_v1_1_0.json`: agrupación de variables, controles de calidad y respuesta de incendios.
- `dataset_maestro_validacion_v1_1_0.json`: validaciones del dataset maestro.

## Estructura mínima recomendada

```text
equipo_XX/
├── README.md          # integrantes, pregunta, zona e instrucciones de ejecución
├── informe/           # PDF y fuente del informe
├── src/               # código reproducible
└── resultados/
    ├── tablas/
    └── figuras/
```

## Lista de comprobación final

- [ ] El análisis utiliza únicamente la zona asignada y el periodo 2019–2024.
- [ ] La pregunta, fórmulas, variables y unidades están definidas.
- [ ] El archivo original no fue modificado.
- [ ] Se revisaron faltantes y variables de calidad.
- [ ] Existe un ejemplo manual que coincide con el código.
- [ ] Los parámetros, pesos y umbrales están justificados y se evaluó su sensibilidad.
- [ ] Tablas, gráficos y conclusiones proceden de la zona del equipo.
- [ ] El trabajo es reproducible y cada integrante puede defenderlo.
