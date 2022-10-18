![image.png](attachment:image.png)


# Modelando el comportamiento de los arriendos de biclicleta en Seul según temperatura ambiental

**TRABAJO REALIZADO POR**

1. Catalina Paredes
2. Susana Flores
3. Gloria Henríquez

## 1. Descripción general del proyecto

El Gobierno Metropolitano de Seúl (SMG) a partir del año 2000 ha centrado sus esfuerzos en mejorar la calidad de vida de sus habitantes desarrollando un sistema de transportes centrado en las personas y mejorando la oferta  del transporte público.

En el 2013 el SMG , se compromete a la “Visión 2030” que  propone reinventar Seúl como una ciudad habitable y móvil sin necesidad de automóviles particulares para el año 2030. El sistema avanza creando un sistema de bicicletas compartidas que se populariza en uso.

Debido a su gran crecimiento, este sitema se ha convertido en una gran alternativa para disminuir los problemas de contaminación y congestión en las zonas urbanas, por lo que se ha vuelto necesario poder estudiar la demanda de arriendo de bicicletas y conocer cuánto influyen las condiciones del tiempo en el uso de este transporte y así contribuir en la planificación y gestión del servicio en la ciudad.

### 1.1. Descripción del DataSet

#### Data Set: Registro de arriendo de bicicletas por hora en la ciudad de Seúl, Corea del Sur, entre 01/12/2017 y 30/11/2018 
- Disponibilidad: carpeta public_bikes_2018documentación en https://www.kaggle.com/competitions/seoul-bike-rental-prediction/overview/data-description 
- Fuente: Seoul Bike Rental Prediction

El  conjunto  de  datos incluye información del sistema  de  bicicletas  compartidas  de  Seúl- Cuenta con información  meteorológica:temperatura  (°C),  humedad  (%),  velocidad  del  viento  (m/s),  visibilidad  (10  m),  la  radiación  solar   (MJ/m2),  las  nevadas  (Mm),  las  precipitaciones  (cm), estaciones del año, etc.  Y  además cuenta con información  del  calendario,  para días festivos, días  laborables, y  los  días  Funcionales  del  sistema  de  bicicletas  compartidas. Comienza  desde  el  primer  día  de  diciembre  de  2017  hasta  finales  de  noviembre  de  2018.


### 1.2. Unidad de Análisis

Se analizará, por medio de regresión lineal, la relación entre la cantidad de arriendos diarios de bicicletas y las condiciones del tiempo de cada día.

- Variable  objetivo  Y : Cantidad de bicicletas arrendadas por hora.

- Variable independiente: temperatura, humedad,  velocidad  del  viento,  visibilidad,  radiación  solar,  nevadas,  precipitaciones, estaciones del año. dias festivos y de funcionamiento del sistema.

- Variable Explicativa Principal: Temperatura ambiental por cada hora

Respecto a los periodos en que no hubo funcionamiento del sistema, se realizó la imputación de datos de los días en que no hubo arriendo, ya que esta información correspondería a los días en que no hubo servicio y no a la falta de demanda. Para realizar lo anterior, se realizó en Excel un promedio (por horas) del arriendo del día anterior con el día próximo, esto equivale al 3,37% del total de los arriendos. 

### 1.3. Utilidad

Planificación del stock del servicio de bicicletas según la temperatura esperada y, también, qué días son mejores para llevar a mantenciones programadas y contar con menos disponibilidad

### 1.4. Hipotesis

- Se espera que hayan menos arriendos en los días en que las temperaturas son más bajas.
- Se espera que haya menos arriendos en las horas en que la gente está en su lugar de trabajo o estudio y
    que aumente en las horas en que se desplazan desde o hacia sus viviendas.
- Se espera que haya menos arriendos los días en que hay lluvia o nieve.
- Se espera que haya más arriendos en las estaciones de primavera y verano.

### 1.5. Limitaciones

No existe forma de conocer el comportamiento de los arriendos los días en que el servicio no está disponible.
La muestra solo representa el comportamiento de los usuarios de bicicletas de la ciudad de Seúl.
Hay variables que pudieran haberse omitido y podrían ser relevantes (sesgo de variable omitida), como:
- Variación de precio según horas de alta y baja demanda, por días de la semana, etc.
- Se podría esperar que los días de mayor contaminación del aire haya menos arriendos, pero esta variable tampoco está considerada en el dataset.
- Los días en que hay manifestaciones sociales podrían cambiar el comportamiento en los arriendos.
- El precio del transporte público y/o los combustibles pudieran influir en el arriendo de bicicletas.

## 2. Estructura de archivos y carpetas

1. Nombre del archivo: **Información_proyecto**
    1. Tipo de archivo: .me
    2. Descripción: Información general del proyecto
    3. Ruta de ubicación: --> Pantalla de inicio 
    
2. Nombre del archivo: **SeoulBikeData**
    1. Tipo de archivo: .csv
    2. Descripción: Dataset original de los arriendos de bicicletas en Seúl
    3. Ruta de ubicación: --> Pantalla de inicio --> Data --> Raw
    
3. Nombre del archivo: **SeoulBikeData_DatosImputados**
    1. Tipo de archivo: .xlsx
    2. Descripción: Dataset con imputación de datos de arriendos de bicicletas los días en que el servicio no estaba disponible
    3. Ruta de ubicación: --> Pantalla de inicio --> Data --> Processed

4. Nombre del archivo: **Bicletas_1_Datos_originales_limpieza_1**
    1. Tipo de archivo: .jpynb
    2. Descripción: Limpieza del dataset original y evaluación de la calidad de la información
    3. Ruta de ubicación: --> Pantalla de inicio --> Notebooks
    
5. Nombre del archivo: **Bicletas_1_Datos_imputados_limpieza_2**
    1. Tipo de archivo: .jpynb
    2. Descripción: Limpieza del dataset con datos imputados y evaluación de la calidad de la información
    3. Ruta de ubicación: --> Pantalla de inicio --> Notebooks
    
6. Nombre del archivo: **Bicletas_1_Datos_imputados_Analisis**
    1. Tipo de archivo: .jpynb
    2. Descripción: Análisis a partir del dataset que incluye imputación de datos y que se limpió en la etapa previa
    3. Ruta de ubicación: --> Pantalla de inicio --> Notebooks
    
7. Nombre del archivo: **Bicletas_1_Datos_imputados_Reporte**
    1. Tipo de archivo: .jpynb
    2. Descripción: Notebook final que contiene los ítems solicitados
    3. Ruta de ubicación: --> Pantalla de inicio --> Notebooks
    
8. Nombre del archivo: **Bicletas_1_Datos_imputados_Reporte**
    1. Tipo de archivo: .html
    2. Descripción: Notebook final que contiene los ítems solicitados
    3. Ruta de ubicación: --> Pantalla de inicio --> Outputs
    

## 3. Guía para recorrer los notebooks

### 3.1. Notebook Bicletas_1_Datos_originales_limpieza_1

Este notebook utiliza la base de datos **SeoulBikeData.csv** que se encuentra en la carpeta Raw, dentro de la carpeta Data. Es el notebook que realiza una limpieza de la base de datos original y en la parte final permite ver, a grandes rasgos, cómo es el comportamiento de los datos, para determinar la necesidad de realizar o no imputación en aquellos que son de interés.

### 3.2	Notebook Bicletas_1_Datos_imputados_limpieza_2

Este notebook utiliza la base de datos **SeoulBikeData_DatosImputados.xlsx** que se encuentra en la carpeta Processed, dentro de la carpeta Data. Es el notebook que realiza una limpieza de la base de datos que tiene imputados aquellos datos de arriendo de bicicletas correspondiente a aquellos días en que el servicio no estuvo disponible. En la parte final permite ver, a grandes rasgos, cómo es el comportamiento de los datos, para compararlo con lo obtenido a partir de la base de datos original.

### 3.3	Notebook Bicletas_1_Datos_imputados_Analisis

Este notebook es la continuación del anterior **Bicletas_1_Datos_imputados_limpieza_2** y en él se realizan los análisis con los datos limpios. Cabe destacar que en el proceso de limpieza ya se habían realizado algunos análisis para determinar la necesidad y utilidad de trabajar con datos imputados asociados a la variable principal (arriendo de bicicletas).

### 3.4	Notebook Bicletas_1_Datos_imputados_Reporte

Este es el notebook del informe final, siendo la última etapa del trabajo. Aquí se entrega la descripción del contexto general de los datos, el proceso de limpieza, los modelos probados y el escogido, el chequeo de supuestos y la interpretación del modelo, junto con las conclusiones y limitaciones finales. Tiene también una versión en formato html.


```python

```
