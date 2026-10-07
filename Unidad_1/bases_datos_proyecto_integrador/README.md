# Proyecto integrador FIRELAB_Loja — Matemática II (Cálculo Integral)

## Propósito

Cada equipo utiliza una base territorial de FIRELAB_Loja para plantear y resolver problemas de **cálculo integral** con datos reales: área bajo un perfil de relieve, longitud de arco, cambio neto acumulado de vegetación, lámina y volumen de lluvia, área acumulada afectada por incendios, y, en la Unidad 3, integrales dobles sobre una región del cantón.

Las bases fueron **delimitadas** para que sean manejables y para que cada integral de la guía pueda plantearse directamente:

- **Ventanas de estudio rectangulares** de celdas contiguas y completas (sin bordes del cantón ni datos faltantes de relieve), en lugar de todas las celdas de la zona.
- Solo las **columnas del tema** del equipo, con sus controles de calidad.
- Coordenadas locales `x_local_m`, `y_local_m` y tiempo `t_mes`, listos para usarse como variables de integración.
- Valores redondeados (2 decimales si el valor es 10 o mayor; 4 decimales si es menor).

## Fuente y alcance

- Fuente: `dataset_maestro_firelab_loja_2019_2025_v1_1_0.csv` (SHA-256 `890423faf91207aa271feb9878b1b379e309c156e8e7128af380a5c1afe674b6`).
- Unidad de observación: **celda de 500 m × 500 m** (25 ha). En las bases mensuales, una celda en un mes.
- Periodo: enero de 2019 a diciembre de 2024 (72 meses). El año 2025 no está incluido y no debe incorporarse.
- Los CSV son de **solo lectura**: toda transformación se hace con código reproducible.
- Los resultados describen la **ventana de estudio** de cada equipo, no toda la zona ni todo el cantón (salvo el equipo 7).

## Asignación de equipos

| Equipo | Tema | Zona | Ventana de estudio | Registros | Columnas | Archivo |
|---:|---|---|---|---:|---:|---|
| 1 | Relieve y accesibilidad | Norte | 20 × 20 celdas (10 × 10 km), una fila por celda | 400 | 17 | `equipo_01_relieve_norte/equipo_01_relieve_norte.csv` |
| 2 | Relieve y accesibilidad | Sur | 20 × 20 celdas (10 × 10 km), una fila por celda | 400 | 17 | `equipo_02_relieve_sur/equipo_02_relieve_sur.csv` |
| 3 | Cobertura vegetal y uso del suelo | Norte | 10 × 10 celdas (5 × 5 km) × 72 meses | 7.200 | 28 | `equipo_03_cobertura_norte/equipo_03_cobertura_norte.csv` |
| 4 | Cobertura vegetal y uso del suelo | Sur | 10 × 10 celdas (5 × 5 km) × 72 meses | 7.200 | 28 | `equipo_04_cobertura_sur/equipo_04_cobertura_sur.csv` |
| 5 | Clima y condiciones atmosféricas | Norte | 10 × 10 celdas (5 × 5 km) × 72 meses | 7.200 | 22 | `equipo_05_clima_norte/equipo_05_clima_norte.csv` |
| 6 | Clima y condiciones atmosféricas | Sur | 10 × 10 celdas (5 × 5 km) × 72 meses | 7.200 | 22 | `equipo_06_clima_sur/equipo_06_clima_sur.csv` |
| 7 | Incendios forestales y riesgo | Loja completo | Serie mensual del cantón | 72 | 14 | `equipo_07_incendios_loja/equipo_07_serie_mensual.csv` |
| 7 | Incendios forestales y riesgo | Loja completo | Resumen por celda (7.997 celdas) | 7.997 | 10 | `equipo_07_incendios_loja/equipo_07_celdas.csv` |

Ubicación de las ventanas (fila y columna de la malla de 500 m):

| Zona | Relieve (equipos 1–2) | Cobertura y clima (equipos 3–6) |
|---|---|---|
| Norte (`centro_y_m >= 9555250.0`) | filas 141–160, columnas 33–52 | filas 142–151, columnas 33–42 |
| Sur (`centro_y_m < 9555250.0`) | filas 53–72, columnas 76–95 | filas 61–70, columnas 77–86 |

La ventana de cobertura y clima está **dentro** de la ventana de relieve de la misma zona, de modo que los equipos de una zona estudian el mismo territorio desde temas distintos. Las ventanas se eligieron por tener el mayor desnivel de la zona entre las ventanas de celdas completas: el norte va de 1.643 a 3.292 m y el sur de 1.614 a 3.560 m.

> **Compartir tema no significa compartir trabajo.** Cada equipo formula su pregunta, ajusta sus funciones, calcula sus integrales y redacta sus conclusiones con **su** base. El contraste norte–sur se realiza al cierre de cada unidad, como indica la guía.

## Variables de integración incluidas en todas las bases de zona

| Columna | Uso en las integrales |
|---|---|
| `x_local_m` | Distancia este–oeste desde la celda de la esquina suroeste de la ventana (0, 500, 1000, … m). Variable de avance $x$ de un transecto oeste–este. |
| `y_local_m` | Distancia sur–norte desde la misma celda (0, 500, … m). Variable de un transecto sur–norte o segunda variable de una integral doble. |
| `t_mes` | Tiempo en meses: 1 = enero de 2019, …, 72 = diciembre de 2024 (solo en bases mensuales). |

En la malla, $\Delta x = \Delta y = 500$ m y cada celda tiene $\Delta A = 250.000$ m² = 25 ha. Una suma doble de Riemann sobre la ventana es $\sum_i \sum_j f(x_i, y_j)\,\Delta A$.

## Qué permite calcular cada base

### Equipos 1 y 2 — Relieve (norte y sur)

- **Transecto:** filtre una fila de la ventana (`y_local_m` constante) y ordene por `x_local_m`; obtiene 20 puntos $(x, z)$ con $z$ = `alos_elevacion_m_mean`. También puede usar una columna (`x_local_m` constante, avance en $y$).
- **Unidad 1:** ajuste $z = f(x)$ y calcule $A = \int_a^b f(x)\,dx$; compare con las sumas de Riemann de los 20 puntos.
- **Unidad 2:** longitud de arco $L = \int_a^b \sqrt{1 + [f'(x)]^2}\,dx$; la pendiente observada (`alos_pendiente_grados_mean`) sirve para verificar $f'(x)$.
- **Unidad 3:** volumen sobre la ventana por secciones $V = \int A(x)\,dx$ o integral doble $\iint z(x,y)\,dA$ (por ejemplo, sobre una cota base).
- Las variables son estáticas: la base trae **una fila por celda** (se comprobó que no cambian entre meses).

### Equipos 3 y 4 — Cobertura vegetal (norte y sur)

- **Serie temporal:** promedie `s2_ndvi_mean` (u otro índice) de las celdas válidas para cada `t_mes`; obtiene $V(t)$ para 72 meses.
- **Unidad 1:** tasa de cambio $r(t) = dV/dt$ y cambio neto $\int_{t_1}^{t_2} r(t)\,dt = V(t_2) - V(t_1)$ (Teorema Fundamental).
- **Unidad 2:** ajuste de funciones armónicas (seno/coseno) a la estacionalidad e integración por partes.
- **Unidad 3:** integral doble del cambio sobre la ventana, $\iint_\Omega I_{\text{cambio}}(x, y)\,dA$, en hectáreas.
- **Calidad:** use solo los registros con `sentinel_t1_missing = 0`; cuando vale 1 (mes nublado o sin imagen) los índices están vacíos. `disponible_sentinel_t1` solo indica si existe mes fuente de Sentinel-2 (vale 0 únicamente en enero de 2019). Las proporciones MAATE son fijas (mapa 2018) y su suma por celda es 1.

### Equipos 5 y 6 — Clima (norte y sur)

- **Serie temporal:** `chirps_precipitacion_acumulada_t1_mm` es la lámina de lluvia de cada mes, $p(t)$ en mm/mes.
- **Unidad 1:** lámina acumulada $H = \int_{t_a}^{t_b} p(t)\,dt$ y volumen por celda $V = 250.000\ \text{m}^2 \times 10^{-3} \times H$ (m³).
- **Unidad 2:** modelos de eventos extremos o estiaje con funciones exponenciales o polinómicas.
- **Unidad 3:** volumen sobre la ventana $\iint_\Omega P(x, y)\,dA$.
- **Atención:** `prev2m` y `prev3m` son acumulados de los 2 y 3 meses **anteriores**; se solapan entre meses consecutivos y no deben sumarse a `t1` para obtener totales. Verifique `chirps_historia_3m_completa` y `chelsa_historia_3m_completa`.

### Equipo 7 — Incendios (Loja completo)

- **`equipo_07_serie_mensual.csv`:** para cada mes del cantón, las celdas válidas, las celdas con incendio (`y_incendio_ge7_obs90`, definición principal) y su área en hectáreas. Es directamente la tasa $r_{\text{fuego}}(t)$ [ha/mes].
- **Unidad 1:** área acumulada $A(t) = \int_0^t r_{\text{fuego}}(\tau)\,d\tau$. La columna `area_incendio_acumulada_ha_ge7_obs90` permite **verificar** el cálculo, no reemplazarlo.
- **Unidad 2:** ajuste logístico o sigmoide del acumulado en temporadas críticas (agosto–noviembre concentra la mayoría de los eventos).
- **Unidad 3:** `equipo_07_celdas.csv` trae, por celda, sus coordenadas y los meses con incendio, para mapas de recurrencia e integrales sobre el territorio.
- **Sensibilidad:** compare la definición principal con `ge8_obs90`, `ge7_obs80`, `ge7_obs95` y `ge7_obs100`.
- **Advertencia:** el área corresponde a **celdas con incendio detectado por satélite** (VIIRS). No es un área quemada medida en campo, y una misma celda puede contarse en varios meses.

## Archivos auxiliares

- `DICCIONARIO_VARIABLES.csv`: significado, unidad, tipo y valores esperados de cada columna. Es el punto de partida para el marco de variables del informe.
- `MANIFIESTO_BASES.csv`: inventario, ventana de estudio, dimensiones, tamaño y huellas SHA-256 de cada archivo.
- `dataset_maestro_diccionario_grupos_v1_1_0.json` y `dataset_maestro_validacion_v1_1_0.json`: referencia del dataset maestro completo (incluyen columnas que no están en las bases delimitadas).

## Lista de comprobación

- [ ] Se usa únicamente la base y la zona del equipo, en el periodo 2019–2024.
- [ ] El CSV original no fue modificado (la huella SHA-256 coincide con el manifiesto).
- [ ] Se revisaron las columnas de calidad y los meses sin dato antes de integrar.
- [ ] Cada integral tiene función, límites, variable de integración y unidades definidos.
- [ ] Existe un cálculo manual (por ejemplo, una suma de Riemann o una celda) que coincide con el código.
- [ ] Los resultados se interpretan dentro de la ventana de estudio, con sus unidades.
