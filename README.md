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
- La región WestNewMexico tiene 3 filas menos que el resto de regiones.

## 1. Series Temporales



![alt text](image.jpg)



