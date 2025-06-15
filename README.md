# 📊 Generación Automatizada del Plan Anual de Capacitación

### Este proyecto automatiza la extracción y consolidación de información a partir de archivos del Diagnóstico de Necesidades de Capacitación (DNC), los cuales contienen evaluaciones de desempeño de trabajadores agrupados por área. A partir de estos datos, se genera una Matriz de Requerimientos y Plan Anual de Capacitación, que permite identificar qué temas deben impartirse y a qué trabajadores, facilitando así una toma de decisiones más ágil y efectiva en la planeación de cursos.

## 🎯 Objetivo

Este sistema permite:

- ✅ Tener un control detallado de las necesidades de capacitación de cada trabajador.
- ⚙️ Automatizar la lectura de archivos y generación del plan anual.
- 📊 Visualizar el avance real en la impartición de cursos.
- 🧠 Apoyar en la toma de decisiones estratégicas en Recursos Humanos o Capacitación.


## Estructura del proyecto

El repositorio está dividido en tres partes principales:

1. **Limpieza_del_DNC.ipynb**  
   - Lee aproximadamente 55 archivos del Diagnóstico de Necesidades de Capacitación (DNC).  
   - Limpia encabezados y elimina columnas innecesarias.  
   - Estandariza y convierte los archivos a formato `.csv` para facilitar su manejo posterior.
    
2. **MatrizDNC.ipynb**
   - Lee los archivos del DNC ya procesados por el archivo anterior.
   - Reemplaza los temas por una clave que agrupa temas similares (por ejemplo, “CTPAT & OEA” y “Certificación CTPAT / OEA” se agrupan como “CTPAT & OEA”).
   - Filtra únicamente los temas cuya modalidad es Curso o Taller.
   - Identifica qué trabajador (por número de nómina) necesita reforzar qué tema.
   - Llena automáticamente la Matriz de Requerimientos y Plan Anual de Capacitación
    (`DNC.xlsx`, hoja `MQ-6201-F06`), donde las columnas son los temas y los renglones las nóminas de los trabajadores. Se marca con una "x" si el trabajador requiere ese curso.

3. **DNC.xlsx**
Libro de Excel con varias hojas:
- **Matriz de Requerimientos y Plan Anual de Capacitación** (`MQ-6201-F06`)  
  Se actualiza automáticamente. Se marca con **"x"** cuando un trabajador requiere un curso. Si la "x" se cambia por **"ok"**, se indica que el curso fue cubierto y el avance se refleja en todo el sistema.

- **Reporte de avance** (`Reporte`)  
  - Muestra una tabla con:  
    - Total de personas que necesitan cada curso.  
    - Total de personas que lo han tomado.  
    - Porcentaje de avance.  
  - Incluye una gráfica de barras que se actualiza automáticamente al marcar capacitaciones como completadas.

- **Hojas por área**  
  Cada área tiene su propia matriz, vinculada a la hoja principal `MQ-6201-F06`. Estas hojas se actualizan automáticamente con cualquier cambio en la matriz principal.


## 📌 Tecnologías utilizadas

- **Jupyter Notebook** – Para el procesamiento y análisis de datos, utilizando:
  - `pandas`, `numpy`, `glob`, `os`
- **Power Query en Excel** – Para vincular hojas y actualizar automáticamente los reportes.
- **Microsoft Excel** – Para la visualización final del plan anual de capacitación.
- **GitHub** – Para control de versiones y documentación del proyecto.

## 🚀 Autora  
**María Belén Flores Landaverde** – Matemática Aplicada  
Apasionada por el análisis de datos y la automatización de procesos administrativos.


