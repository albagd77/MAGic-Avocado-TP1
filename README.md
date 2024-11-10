# MAGic-Avocado-TP1

Mini Proyecto para el curso Data Scientist impartido por la [UOC](https://www.uoc.edu/), consistente en el análisis del set de datos [Avocado Prices](https://www.kaggle.com/datasets/neuromusic/avocado-prices/data).

Componentes del equipo: 
 - Alba Godoy Domínguez
 - Gustavo Chávez
 - Montserrat López Ibáñez

## EDA (Exploratory Data Analysis)

Iniciamos el análisis realizando un EDA (Exploratory Data Analysis) en el transcurso del cual descubrimos que:
- El dataset tiene 18.249 filas y 11 columnas.
- Los datos están tomados semanalmente, es decir, hay 4/5 mediciones por cada mes.
- El rango de fechas para la columna 'Date' incluye los años 2015 a 2018.
- El año 2018 está incompleto, de modo que sólo tenemos datos de enero a marzo.
- En las columnas de calibre ('4046', '4225', '4770') hay valores a cero (0.0). En concreto, 242 ceros en la columna '4046', 61 ceros en la columna '4225', 5.497 ceros en la columna '4770'. Todos estos registros corresponden a aguacates de tipo orgánico, excepto una fila (df.iloc[2998]) que es de tipo convencional.
- La columna 'Total Bags' tiene 15 filas a cero (0.0), todas correspondientes a aguacates de tipo orgánico.
- Asimismo, las columnas 'Small Bags', 'Large Bags' y 'XLarge Bags' tienen 159, 2.370 y 12.048 filas a cero (0.0) respectivamente.
- La columna 'region' incluye información heterogénea, es decir, una mezcla de ciudades, regiones, regiones ampliadas (*greater regions*), y también registros para el total de Estados Unidos (*TotalUS*).
- La región WestNewMexico tiene 3 filas menos que el resto de regiones.

## 1. Series Temporales

Puesto que las mediciones son semanales (4/5) mediciones por mes, al calcular las series temporales para 'AveragePrice' debemos configurarlas con `period=52`.

![Serie Temporal para 'AveragePrice'](./media/01-01_series_temporales.png)

En la gráfica resultante observamos claramente un patrón repetitivo de año en año: bajada de precio en el mes de febrero , así como un pico de subida en los meses de octubre/noviembre. En septiembre se empieza a acabar la temporada de cosecha del aguacate, y por eso es probable que el precio suba en los meses siguientes. Si añadimos el hecho de que en noviembre se celebra el día de Acción de Gracias, en el cual es muy común utilizar aguacate para hacer guacamole en USA, tenemos el terreno abonado para una subida de precios.


Puesto que el dataset contiene información heterogénea (mezcla de ciudades, regiones, etc.) para el análisis de estacionalidad por región utilizaremos únicamente las regiones ampliadas, **GreaterRegions**, que nos permite un análisis visual más interpretable.

![Estacionalidad de 'AveragePrice' por GreaterRegion](./media/01-02_estacionalidad_por_region.png)

En esta gráfica destaca una caída de precio muy notable y uniforme en todas las regiones, en invierno de 2017. Además, destaca en particular la evolución de tres regiones (California, Northeast y SouthCentral), por los siguientes motivos:
- California tiene los picos más pronunciados en el procio promedio tando en subidas como en caídas, es decir, demuestra gran inestabilidad.
- Northeast es la región con el precio promedio más elevado.
- SouthCentral, en contraposición a Northeast, es la región con el precio promedio más bajo.

Los dos últimos puntos pueden observarse más fácilmente si agrupamos los datos anualmente:

![Evolución anual de precios por GreaterRegion](./media/01-05_evolucion_anual_precios.png)

Sin embargo, en este gráfico quedan enmascaradas las caídas de precio de California, por ser sucesos mensuales.


# (TO DO): gráfica y comentar apartado 01-03

Al evaluar la característica 'Total Volume', filtrando de nuevo por **GreaterRegions**, para ver la tendencia de ventas a lo largo del tiempo, observamos caídas en el volumen de aguacates vendidos just a finales de año, lo cual concuerda con la subida de precio que habíamos observado anteriormente en octubre/noviembre.

![Tendencia de ventas por GreaterRegion](./media/01-04_ventas_por_region.png)

## 2. Gráficos para visualización

## 3. Elasticidad del precio

## 2. Análisis cohortes

## 2. Correlación y regresión






