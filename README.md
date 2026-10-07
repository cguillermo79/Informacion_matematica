# Matemática II: Cálculo Integral Aplicado a la Ingeniería Ambiental
### Proyecto Integrador de Asignatura — Ciclo Septiembre 2026 – Febrero 2027
**Universidad Nacional de Loja (UNL)**  
**Facultad Agropecuaria y de Recursos Naturales Renovables**  
**Carrera de Ingeniería Ambiental**  
**Docente:** Dr. Guillermo Chuncho  

---

## 📌 Guías Oficiales del Curso

1. 🚀 **[Guía Paso a Paso para Estudiantes: GitHub, VS Code, venv y Terminal](GUIA_ESTUDIANTE_CONFIGURACION_ENTORNO.md)**  
   *Consulte este documento para instalar herramientas, clonar el repositorio, crear el entorno virtual y configurar VS Code.*
2. 📄 **[Guía General del Proyecto Integrador (PDF)](Unidad_1/05_Guias/guia_general_proyecto_integrador_matematica.pdf)** y código fuente **[.tex](Unidad_1/05_Guias/guia_general_proyecto_integrador_matematica.tex)**.
3. 📄 **[Guía Práctica de Entorno y GitHub para Estudiantes (PDF)](Unidad_1/05_Guias/guia_estudiante_entorno_github_vscode.pdf)** y código fuente **[.tex](Unidad_1/05_Guias/guia_estudiante_entorno_github_vscode.tex)**.

---

## 📂 Estructura del Repositorio

```text
Informacion_matematica/
├── requirements.txt                     <- Dependencias cientificas de Python
├── GUIA_ESTUDIANTE_CONFIGURACION_ENTORNO.md <- Guia metodologica y practica de terminal
├── Unidad_1/
│   ├── bases_datos_proyecto_integrador/ <- Bases oficiales de datos (solo lectura)
│   ├── 01_formulacion_3pct/             <- Entrega Fase 1: Delimitacion, hipotesis y variables
│   ├── 02_avance_4pct/                  <- Entrega Fase 2: Scripts y analisis exploratorio
│   ├── 03_producto_tecnico_10pct/       <- Entrega Fase 3: Informe formal de Formulacion (LaTeX/PDF)
│   ├── 04_defensa_individual_8pct/      <- Entrega Fase 4: Presentacion y diapositivas
│   └── 05_Guias/                        <- Guias oficiales de la catedra (.pdf y .tex)
├── Unidad_2/
│   ├── 01_formulacion_3pct/             <- Entrega Fase 1 U2: Modelos continuos no lineales
│   ├── 02_avance_4pct/                  <- Entrega Fase 2 U2: Integracion analitica y numerica
│   ├── 03_producto_tecnico_10pct/       <- Entrega Fase 3 U2: Informe de Metodologia (LaTeX/PDF)
│   ├── 04_defensa_individual_8pct/      <- Entrega Fase 4 U2: Material de sustentacion
│   └── 05_Guias/
└── Unidad_3/
    ├── 01_formulacion_3pct/             <- Entrega Fase 1 U3: Modelacion fisica y balances
    ├── 02_avance_4pct/                  <- Entrega Fase 2 U3: Integrales dobles y serie temporal
    ├── 03_producto_tecnico_10pct/       <- Entrega Fase 3 U3: Informe Final Consolidado (LaTeX/PDF)
    ├── 04_defensa_individual_8pct/      <- Entrega Fase 4 U3: Sustentacion individual final
    └── 05_Guias/
```

---

## 📊 Asignación de Equipos y Bases de Datos

Las bases están en [`Unidad_1/bases_datos_proyecto_integrador/`](Unidad_1/bases_datos_proyecto_integrador/README.md). Son **ventanas de estudio** pequeñas, preparadas para plantear integrales directamente (transectos, series de 72 meses y regiones rectangulares); ver la [guía de las bases](Unidad_1/bases_datos_proyecto_integrador/README.md) y el [diccionario de variables](Unidad_1/bases_datos_proyecto_integrador/DICCIONARIO_VARIABLES.csv).

| Equipo | Temática Asignada | Zona Territorial | Subcarpeta | Tamaño |
| :---: | :--- | :---: | :--- | :--- |
| **Equipo 1** | Relieve y Accesibilidad | Zona Norte | `equipo_01_relieve_norte/` | 400 celdas (20×20), 400 reg, 17 col |
| **Equipo 2** | Relieve y Accesibilidad | Zona Sur | `equipo_02_relieve_sur/` | 400 celdas (20×20), 400 reg, 17 col |
| **Equipo 3** | Cobertura y Suelo | Zona Norte | `equipo_03_cobertura_norte/` | 100 celdas (10×10) × 72 meses, 7.200 reg, 28 col |
| **Equipo 4** | Cobertura y Suelo | Zona Sur | `equipo_04_cobertura_sur/` | 100 celdas (10×10) × 72 meses, 7.200 reg, 28 col |
| **Equipo 5** | Clima y Atmósfera | Zona Norte | `equipo_05_clima_norte/` | 100 celdas (10×10) × 72 meses, 7.200 reg, 22 col |
| **Equipo 6** | Clima y Atmósfera | Zona Sur | `equipo_06_clima_sur/` | 100 celdas (10×10) × 72 meses, 7.200 reg, 22 col |
| **Equipo 7** | Incendios y Severidad | Cantón Completo | `equipo_07_incendios_loja/` | Serie mensual (72 reg) y resumen por celda (7.997 reg) |

---

## ⚡ Comandos Rápidos para Empezar

```bash
# 1. Clonar el repositorio
git clone https://github.com/cguillermo79/Informacion_matematica.git
cd Informacion_matematica

# 2. Abrir en VS Code
code .

# 3. Crear entorno virtual (en la terminal de VS Code)
python -m venv .venv

# 4. Activar entorno virtual
# En Windows PowerShell:
.\.venv\Scripts\Activate.ps1
# En Linux/macOS:
source .venv/bin/activate

# 5. Instalar dependencias cientificas
pip install -r requirements.txt
```
