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
├── bases_datos_proyecto_integrador/     <- Bases oficiales de datos (solo lectura)
├── requirements.txt                     <- Dependencias cientificas de Python
├── GUIA_ESTUDIANTE_CONFIGURACION_ENTORNO.md <- Guia metodologica y practica de terminal
├── Unidad_1/
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

| Equipo | Temática Asignada | Zona Territorial | Subcarpeta en `bases_datos_proyecto_integrador/` |
| :---: | :--- | :---: | :--- |
| **Equipo 1** | Relieve y Accesibilidad | Zona Norte | `equipo_01_relieve_zona_norte/` |
| **Equipo 2** | Relieve y Accesibilidad | Zona Sur | `equipo_02_relieve_zona_sur/` |
| **Equipo 3** | Cobertura Vegetal y Suelo | Zona Norte | `equipo_03_cobertura_zona_norte/` |
| **Equipo 4** | Cobertura Vegetal y Suelo | Zona Sur | `equipo_04_cobertura_zona_sur/` |
| **Equipo 5** | Clima y Atmósfera | Zona Norte | `equipo_05_clima_zona_norte/` |
| **Equipo 6** | Clima y Atmósfera | Zona Sur | `equipo_06_clima_zona_sur/` |
| **Equipo 7** | Incendios y Severidad | Cantón Completo | `equipo_07_incendios_loja_completo/` |

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
