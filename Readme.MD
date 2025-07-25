# Proyecto de Integración de Datos Públicos en Databricks

Este proyecto tiene como objetivo conectar y procesar datos abiertos del gobierno de Colombia utilizando **Databricks**.  
Se integran datos desde APIs públicas y se preparan para análisis y visualización.

---
####  Actualización para que se visualice en el github
## Fuentes de Datos

1. **SECOP (Sistema Electrónico de Contratación Pública)**  
   URL: [https://www.datos.gov.co/resource/rpmr-utcd.csv](https://www.datos.gov.co/resource/rpmr-utcd.csv)  
   Contiene información sobre contratos y procesos de contratación pública.

2. **MEN (Ministerio de Educación Nacional)**  
   URL: [https://www.datos.gov.co/resource/nudc-7mev.csv](https://www.datos.gov.co/resource/nudc-7mev.csv)  
   Contiene información relacionada con instituciones y programas educativos.

---

## Estructura del Notebook en Databricks

### **Celda 1: Lectura de datos desde APIs**
Se cargan los datos directamente desde las URLs públicas usando Spark y Pandas:

```python
# URLs de los datasets
url_secop = "https://www.datos.gov.co/resource/rpmr-utcd.csv"
url_men = "https://www.datos.gov.co/resource/nudc-7mev.csv"

# Lectura con Spark
df_secop = spark.read.format("csv").option("header", "true").load(url_secop)
df_men = spark.read.format("csv").option("header", "true").load(url_men)

# Visualizar primeras filas
display(df_secop.limit(5))
display(df_men.limit(5))
# ultimaactualización
