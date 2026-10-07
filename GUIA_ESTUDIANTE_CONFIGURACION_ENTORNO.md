# Guía Paso a Paso para Estudiantes: GitHub, Visual Studio Code, Entorno Virtual Python (venv) y Bases del Proyecto Integrador

**Universidad Nacional de Loja**  
**Facultad Agropecuaria y de Recursos Naturales Renovables**  
**Carrera de Ingeniería Ambiental**  
**Asignatura:** Matemática II: Cálculo Integral Aplicado a la Ingeniería Ambiental  
**Período Académico:** Septiembre 2026 – Febrero 2027  
**Docente:** Dr. Guillermo Chuncho  
**Repositorio Oficial:** [https://github.com/cguillermo79/Informacion_matematica](https://github.com/cguillermo79/Informacion_matematica)

---

## 1. Presentación y Propósito de la Guía

Esta guía proporciona a todos los estudiantes y equipos de trabajo las instrucciones exactas, secuenciales y reproducibles para:
1. Clonar el repositorio oficial del curso en su computadora personal.
2. Abrir el proyecto en **Visual Studio Code (VS Code)**.
3. Crear y activar un **entorno virtual aislado de Python (`venv`)** desde la terminal.
4. Instalar las dependencias científicas necesarias (`numpy`, `pandas`, `scipy`, `matplotlib`, `seaborn`, `jupyter`).
5. Acceder, auditar y verificar las **bases de datos geoespaciales y climáticas** asignadas a su equipo.
6. Organizar y subir de forma ordenada los entregables de cada unidad académica (**Unidad 1, Unidad 2 y Unidad 3**) mediante comandos de **Git**.

---

## 2. Requisitos Previos e Instalación del Software Base

Antes de ejecutar comandos en la terminal, asegúrese de tener instaladas las siguientes herramientas gratuitas:

### 2.1 Git (Sistema de Control de Versiones)
* **Descarga:** [https://git-scm.com/downloads](https://git-scm.com/downloads)
* En Windows, ejecute el instalador dejando las opciones por defecto recomendadas (permitir Git desde la consola de Windows).
* Compruebe la instalación abriendo una terminal y ejecutando:
  ```bash
  git --version
  ```

### 2.2 Python 3 (Versión 3.10, 3.11 o 3.12 recomendada)
* **Descarga:** [https://www.python.org/downloads/](https://www.python.org/downloads/)
* ⚠️ **¡PASO CRÍTICO EN WINDOWS!**  
  Al abrir el instalador, en la primera pantalla, **marque obligatoriamente la casilla inferior:**  
  `☑ Add python.exe to PATH` antes de hacer clic en **Install Now**.  
  *(Si omite este paso, el comando `python` no funcionará en la terminal).*
* Compruebe la instalación ejecutando:
  ```bash
  python --version
  ```

### 2.3 Visual Studio Code (VS Code)
* **Descarga:** [https://code.visualstudio.com/Download](https://code.visualstudio.com/Download)
* **Extensiones recomendadas dentro de VS Code** (instálelas desde la barra lateral izquierda `Ctrl + Shift + X`):
  * **Python** (de Microsoft).
  * **Jupyter** (de Microsoft, para ejecutar cuadernos `.ipynb`).
  * **GitLens** (opcional, excelente para trazabilidad de código).

---

## 3. Protocolo Paso a Paso en la Terminal: Del Repositorio a su PC

Abra su terminal favorita:
* **En Windows:** Terminal de Windows o PowerShell.
* **En macOS / Linux:** Terminal (Bash / Zsh).

---

### Paso 1: Configurar su identidad en Git (Solo si es la primera vez)
Configure su nombre completo y su correo electrónico personal (el mismo asociado a su cuenta de GitHub):
```bash
git config --global user.name "Nombres y Apellidos del Estudiante"
git config --global user.email "correo.personal@gmail.com"
```
Verifique la configuración con:
```bash
git config --list
```

---

### Paso 2: Crear una carpeta de trabajo local y ubicarse en ella
Se recomienda trabajar en una ruta limpia y sin caracteres especiales, por ejemplo dentro de `Documentos`:

```powershell
# En Windows (PowerShell):
cd $HOME\Documents
mkdir Matematica_UNL
cd Matematica_UNL
```

```bash
# En Linux / macOS:
cd ~/Documents
mkdir Matematica_UNL
cd Matematica_UNL
```

---

### Paso 3: Clonar el repositorio oficial desde GitHub
Ejecute el comando `git clone` con la URL del curso:

```bash
git clone https://github.com/cguillermo79/Informacion_matematica.git
```

Una vez finalizada la descarga, ingrese a la carpeta del repositorio:
```bash
cd Informacion_matematica
```

---

### Paso 4: Abrir el proyecto en Visual Studio Code
Dentro de la carpeta `Informacion_matematica`, ejecute:

```bash
code .
```
*(El punto `.` indica que VS Code se abrirá en la carpeta actual).*

> **Nota alternativa:** Si el comando `code` no abre el editor, abra Visual Studio Code manualmente, vaya al menú superior **File $\rightarrow$ Open Folder...** (o *Archivo $\rightarrow$ Abrir carpeta...*) y seleccione la carpeta `Informacion_matematica`.

---

### Paso 5: Abrir la terminal integrada en VS Code
Dentro de VS Code, abra la terminal integrada usando:
* El atajo de teclado: `Ctrl + Shift + ` ` (tecla de tilde/acento grave).
* O desde el menú superior: **Terminal $\rightarrow$ New Terminal**.

---

### Paso 6: Crear el entorno virtual de Python (`venv`)
Un entorno virtual es un espacio aislado para que las librerías del proyecto no interfieran con otras asignaturas o con el sistema operativo.

Ejecute en la terminal de VS Code:

```bash
# En Windows (PowerShell o CMD):
python -m venv .venv

# En Linux o macOS:
python3 -m venv .venv
```
Este comando creará una carpeta llamada `.venv/` en la raíz del proyecto.

---

### Paso 7: Permisos de ejecución en Windows PowerShell (Solución a error común)
Si al intentar activar el entorno virtual en PowerShell le aparece el error:
> *"File ... Activate.ps1 cannot be loaded because running scripts is disabled on this system"*

Debe habilitar la ejecución de scripts locales ejecutando **una sola vez** en la terminal:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```
Presione `Y` (Sí) y luego `Enter`.

---

### Paso 8: Activar el entorno virtual (`venv`)
Ejecute el comando correspondiente a su sistema operativo:

```powershell
# En Windows PowerShell:
.\.venv\Scripts\Activate.ps1
```

```cmd
# En Windows CMD (Símbolo del sistema):
.\.venv\Scripts\activate.bat
```

```bash
# En macOS / Linux (Bash o Zsh):
source .venv/bin/activate
```

#### ¿Cómo verificar que el entorno virtual está activo?
Al inicio de su línea de comandos en la terminal debe aparecer el prefijo `(.venv)`, por ejemplo:
```text
(.venv) PS C:\Users\Estudiante\Documents\Matematica_UNL\Informacion_matematica>
```

---

### Paso 9: Seleccionar el Intérprete en Visual Studio Code
Para que VS Code y los notebooks de Jupyter ejecuten el código usando el entorno virtual que acaba de crear:
1. Presione `Ctrl + Shift + P` (o `Cmd + Shift + P` en Mac).
2. Escriba: `Python: Select Interpreter` y presione Enter.
3. Seleccione la opción que contiene `(.venv): .venv\Scripts\python.exe` (o `.venv/bin/python`).
4. En la barra de estado inferior derecha de VS Code confirmará: `3.1x.x ('.venv': venv)`.

---

### Paso 10: Actualizar pip e instalar las librerías científicas
Con el entorno virtual activo `(.venv)`, actualice el instalador de paquetes e instale todas las dependencias del curso:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Si no dispone del archivo `requirements.txt`, ejecute directamente:
```bash
pip install numpy scipy pandas matplotlib seaborn jupyter pyarrow fastparquet openpyxl
```

---

## 4. Localización y Auditoría de Bases de Datos por Equipo

Todas las bases oficiales están en la carpeta `Unidad_1/bases_datos_proyecto_integrador/` (archivos CSV pequeños, de 5 KB a 1 MB). Cada equipo debe trabajar exclusivamente con su base asignada; el significado de cada columna está en `DICCIONARIO_VARIABLES.csv`:

| Equipo | Temática Asignada | Zona Territorial | Subcarpeta Asignada | Dimensión de Datos |
| :---: | :--- | :---: | :--- | :--- |
| **Equipo 1** | Relieve y Accesibilidad | **Zona Norte** | `Unidad_1/bases_datos_proyecto_integrador/equipo_01_relieve_norte/` | 400 celdas (20×20), 400 reg, 17 col |
| **Equipo 2** | Relieve y Accesibilidad | **Zona Sur** | `Unidad_1/bases_datos_proyecto_integrador/equipo_02_relieve_sur/` | 400 celdas (20×20), 400 reg, 17 col |
| **Equipo 3** | Cobertura y Suelo | **Zona Norte** | `Unidad_1/bases_datos_proyecto_integrador/equipo_03_cobertura_norte/` | 100 celdas (10×10) × 72 meses, 7.200 reg, 28 col |
| **Equipo 4** | Cobertura y Suelo | **Zona Sur** | `Unidad_1/bases_datos_proyecto_integrador/equipo_04_cobertura_sur/` | 100 celdas (10×10) × 72 meses, 7.200 reg, 28 col |
| **Equipo 5** | Clima y Atmósfera | **Zona Norte** | `Unidad_1/bases_datos_proyecto_integrador/equipo_05_clima_norte/` | 100 celdas (10×10) × 72 meses, 7.200 reg, 22 col |
| **Equipo 6** | Clima y Atmósfera | **Zona Sur** | `Unidad_1/bases_datos_proyecto_integrador/equipo_06_clima_sur/` | 100 celdas (10×10) × 72 meses, 7.200 reg, 22 col |
| **Equipo 7** | Incendios y Severidad | **Cantón Loja Completo** | `Unidad_1/bases_datos_proyecto_integrador/equipo_07_incendios_loja/` | Serie mensual (72 reg) y resumen por celda (7.997 reg) |

### Script de prueba rápida en Python
Para comprobar que su entorno virtual lee correctamente la base de datos de su equipo, cree un archivo `test_datos.py` y ejecute:

```python
import pandas as pd
from pathlib import Path

# Modifique la ruta segun la subcarpeta de su equipo:
ruta = Path("Unidad_1/bases_datos_proyecto_integrador/equipo_01_relieve_norte/equipo_01_relieve_norte.csv")

if ruta.exists():
    df = pd.read_csv(ruta)
    print("Lectura exitosa de la base de datos!")
    print(f"Dimensiones: {df.shape[0]} filas x {df.shape[1]} columnas")
    print(f"Celdas unicas de 500m (cell_id): {df['cell_id'].nunique()}")
    print("\nPrimeras variables:")
    print(df.columns[:10].tolist())
else:
    print(f"Archivo no encontrado en: {ruta}")
```

---

## 5. Estructura de Carpetas para Entregables por Unidad

El repositorio organiza el ciclo académico en tres unidades, con subcarpetas homologadas para cada fase de evaluación:

```text
Informacion_matematica/
├── requirements.txt                     <- Dependencias cientificas de Python
├── GUIA_ESTUDIANTE_CONFIGURACION_ENTORNO.md <- Esta guia practica
├── Unidad_1/
│   ├── bases_datos_proyecto_integrador/ <- Bases oficiales (solo lectura)
│   ├── 01_formulacion_3pct/             <- Fase 1: Problema, hipotesis, objetivos y variables
│   ├── 02_avance_4pct/                  <- Fase 2: Scripts, notebooks exploratorios y tablas
│   ├── 03_producto_tecnico_10pct/       <- Fase 3: Informe formal en LaTeX y PDF (APA 7ma ed.)
│   ├── 04_defensa_individual_8pct/      <- Fase 4: Presentacion y diapositivas de sustentacion
│   └── 05_Guias/                        <- Guias oficiales de la catedra (.pdf y .tex)
├── Unidad_2/
│   ├── 01_formulacion_3pct/             <- Fase 1 U2: Modelos continuos no lineales
│   ├── 02_avance_4pct/                  <- Fase 2 U2: Integracion analitica y numerica
│   ├── 03_producto_tecnico_10pct/       <- Fase 3 U2: Informe de Metodologia en LaTeX y PDF
│   ├── 04_defensa_individual_8pct/      <- Fase 4 U2: Material de sustentacion
│   └── 05_Guias/
└── Unidad_3/
    ├── 01_formulacion_3pct/             <- Fase 1 U3: Modelacion fisica y balances
    ├── 02_avance_4pct/                  <- Fase 2 U3: Integrales dobles y serie temporal
    ├── 03_producto_tecnico_10pct/       <- Fase 3 U3: Informe Final Consolidado (LaTeX y PDF)
    ├── 04_defensa_individual_8pct/      <- Fase 4 U3: Sustentacion individual final
    └── 05_Guias/
```

---

## 6. Flujo de Trabajo con Git: Actualizar y Subir sus Entregables

### 6.1 Antes de iniciar cada jornada de trabajo (Actualizar cambios del docente)
Para descargar nuevas guías o avisos que el docente comparta en el repositorio:
```bash
git pull origin main
```

### 6.2 Al terminar o avanzar su trabajo (Guardar y confirmar cambios)
Coloque sus archivos en la subcarpeta correspondiente (ejemplo: `Unidad_1/01_formulacion_3pct/`):
```bash
# 1. Comprobar que archivos ha creado o modificado:
git status

# 2. Agregar los archivos de su entrega:
git add Unidad_1/01_formulacion_3pct/

# 3. Registrar el commit con un mensaje formal:
git commit -m "Equipo 01: Entrega de Fase 1 Formulacion de Proyecto Unidad 1"

# 4. Enviar los cambios al repositorio en GitHub:
git push origin main
```

### 6.3 Archivos excluidos automáticamente (`.gitignore`)
El repositorio cuenta con un archivo `.gitignore` configurado para **no** subir archivos innecesarios o pesados:
* La carpeta `.venv/` (cada estudiante tiene su propio entorno local).
* Archivos `__pycache__/` y temporales de Jupyter `.ipynb_checkpoints/`.
* Archivos auxiliares de LaTeX (`.aux`, `.log`, `.out`, `.toc`, etc.). **Solo se suben el `.tex` y el `.pdf` final**.

---

## 7. Tabla Rápida de Comandos (Cheatsheet)

| Acción | Comando Windows (PowerShell) | Comando Linux / macOS |
| :--- | :--- | :--- |
| **Clonar repositorio** | `git clone <URL>` | `git clone <URL>` |
| **Abrir en VS Code** | `code .` | `code .` |
| **Crear entorno virtual** | `python -m venv .venv` | `python3 -m venv .venv` |
| **Habilitar scripts (1 vez)** | `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser` | No aplica |
| **Activar entorno virtual** | `.\.venv\Scripts\Activate.ps1` | `source .venv/bin/activate` |
| **Desactivar entorno** | `deactivate` | `deactivate` |
| **Instalar librerías** | `pip install -r requirements.txt` | `pip install -r requirements.txt` |
| **Bajar cambios de GitHub** | `git pull origin main` | `git pull origin main` |
| **Revisar estado de cambios** | `git status` | `git status` |
| **Agregar archivos a entrega**| `git add <carpeta o archivo>` | `git add <carpeta o archivo>` |
| **Confirmar entrega local** | `git commit -m "Mensaje formal"` | `git commit -m "Mensaje formal"` |
| **Subir entrega a GitHub** | `git push origin main` | `git push origin main` |

---

## 8. Preguntas Frecuentes y Solución de Problemas (FAQ)

1. **¿Qué hago si al escribir `python` me abre la tienda de Windows (Microsoft Store)?**  
   * Solución: Abra el menú Inicio de Windows $\rightarrow$ *Administrar alias de ejecución de aplicaciones* $\rightarrow$ Desactive los interruptores para "Instalador de Python" y "python.exe". Luego vuelva a instalar Python marcando la opción *"Add python.exe to PATH"*.

2. **¿Debo subir la carpeta `.venv` a GitHub?**  
   * **No, jamás.** La carpeta `.venv` está excluida en el `.gitignore`. Cada compañero de equipo debe generar su propio entorno virtual local con `python -m venv .venv` y ejecutar `pip install -r requirements.txt`.

3. **¿Cómo abro un cuaderno interactivo de Jupyter?**  
   * Con el entorno virtual activo, dentro de VS Code cree un archivo con extensión `.ipynb` (ejemplo: `exploracion_datos.ipynb`). Al abrirlo, en la esquina superior derecha del cuaderno elija el kernel `Python Environments...` y seleccione `(.venv)`.

---
*Universidad Nacional de Loja — Educación con rigor científico y pertinencia ambiental.*
