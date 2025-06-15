# 📊 Generación Automatizada del Plan Anual de Capacitación

### Este proyecto automatiza la extracción y consolidación de información a partir de archivos del Diagnóstico de Necesidades de Capacitación (DNC), los cuales contienen evaluaciones de desempeño de trabajadores agrupados por área. A partir de estos datos, se genera una Matriz de Requerimientos y Plan Anual de Capacitación, que permite identificar qué temas deben impartirse y a qué trabajadores, facilitando así una toma de decisiones más ágil y efectiva en la planeación de cursos.

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
