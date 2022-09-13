# Series_temporales
## Resumen
El objetivo de este trabajo es otorgar mayores herramientas para la toma de decisiones a aquellos actores que por su rol social, político o económico, tengan que decidir sobre cuestiones relacionadas a la agenda de impacto climático sobre la variación global del clima de la Tierra. En la actualidad se ha llegado al consenso de que el modo de producir de la
economía y su consumo energético asociado, están generando una modificación climática global, que traerá aparejado graves y profundos impactos tanto sobre la tierra como sobre los sistemas socioeconómicos. <br>
Para lograr dicho objetivo, se han analizado las series temporales de la demanda de electricidad y temperatura, de la provincia de Buenos Aires del periodo de 3 años comprendido entre 2019 y 2021. Para este análisis se comenzará realizando gráficas y tests que permitan identificar la estacionariedad de la serie y establecer si son necesarias transformaciones. Además se realizará la estimación de parámetros e identificación de los modelos que permitan modelar las series, el análisis de sus residuos. Continuando con el análisis y parte del presente trabajo consiste en pronosticar una ventana de tiempo y
realizando una con otros métodos de pronóstico. <br>
El trabajo realizará una primera descomposición de cada una de las series, entendimiento del comportamiento de cada una individualmente, analizando desde distintos modelos si es mejor a través de la visión diaria, semanal o mensual, y luego a través de diferentes análisis que serán desarrollados en el siguiente capítulo del presente trabajo. Finalmente, se
desarrollará un modelo de tipo SARIMA (Seasonal Autoregressive Integrated Moving Average por sus siglas en inglés, o lo que traducido se podría definir como modelo de autoregresión estacional integrado de medias móviles). <br>
Respecto de la estacionalidad a través del análisis gráfico, se concluye que ambas series tienen estacionalidad a lo largo del año, donde se presentan las temperaturas más bajas para julio y las temperaturas más altas para enero, esto es de esperarse por las estaciones del año. Cuando se analiza semanalmente, se suavizan las fluctuaciones intradiarias de la
serie original manteniendo la estacionalidad anual. <br>
Respecto de la estacionalidad de la demanda eléctrica, se concluye en el gráfico que la serie tiene estacionalidad aunque la misma no es tan evidente como en la temperatura. Al igual que para la serie de temperatura, se trabajó con frecuencia semanal. <br>

Respecto de las pruebas de estacionariedad ADF, KPSS, y Phillip-Perrón considerando las distintas regresiones descritas en el marco teórico de este trabajo, se concluye que las series son estacionarias. <br>
Respecto a los modelos SARIMA creados para la serie de temperatura, se concluye que el modelo no necesitó diferenciar la serie siendo consistente con las conclusiones de estacionariedad obtenidas anteriormente. Adicionalmente, se creó el modelo SARIMA manual sin diferenciación en la serie de temperatura utilizando las conclusiones obtenidas en los análisis previos y haciendo alguna sensibilidad sobre la estacionalidad anual. Se concluye que las mejores métricas son las del modelo SARIMA manual lo que indica que diferenciar la serie estacionalmente mejora el poder predictivo del modelo. <br>
Con respecto al consumo eléctrico y al igual que para la serie de la temperatura, el modelo no requirió diferenciar la serie por lo que la serie efectivamente es estacionaria. Del análisis de un modelo SARIMA manual, si bien las métricas obtenidas son mejores, la diferencia obtenida en las predicciones justifica la selección del modelo SARIMA obtenido a partir de criterios de información. <br>
Respecto a la comparación con otros modelos estimados, se compararon ambas series a través de las métricas RMSE y MAPE, entre el mejor modelo encontrado de cada una de ellas y otros métodos de pronóstico como: Naive, Naive Estacional, Promedio móvil, Drift, Modelos SARIMA, definidos por criterio del analista.<br>
Se concluye que los métodos más simples, tales como media móvil, naive o drift no resultan de gran utilidad para este tipo de series. Siendo los modelos que contemplan el componente estacional, en su estructura, los que mayor bondad de ajuste tienen. Respecto de la temperatura, el modelo indicado por el Auto Arima es el que presenta menor error absoluto porcentual, superando el seleccionado bajo criterio del analista por medio punto porcentual. <br>
Respecto del consumo eléctrico, se observa lo importante del componente estacional, ya que los modelos que lo contienen son los que mejor se ajustan. Como ya fue establecido previamente el modelo obtenido vía Auto Arima es el que mejor ajusta.
Respecto del análisis de residuos, se tomó el modelo que tuvo mejor desempeño en la serie de temperatura y de consumo eléctrico. Podemos concluir que los residuos se comportan como ruido blanco en ambas series.

## Datasets utilizados
Los datos que se utilizaron fueron los siguientes:
1. Clima: Windguru. (2022). Clima Buenos Aires. Windguru. Obtenido de la página web el día 25 de Julio de 2022 de https://www.windguru.cz/261. 
2. Demanda Eléctrica: CAMMESA - Compañía Administradora del Mercado Electrico Argentino S.A. (2020). Obtenido de la página web el día 25 de Julio de 2022 de https://cammesaweb.cammesa.com/de.

## Librerías y funciones utilizadas
Los modelos y los análisis fueron realizados íntegramente en Python, y para ello se
utilizaron las siguientes librerías o bibliotecas:
1. Pandas (Manipulación de datos)
2. Numpy (Manipulación de datos)
3. Seaborn (Graficar las series)
4. Matplotlib (Graficar las series)
5. Scipy (Utilización de métricas)
6. Pylab
7. Statsmodels (Creación de modelos y utilización de métricas)
8. Arch (Utilización de métricas)
9. Pmdarima (Encontrar el modelo óptimo para cada serie)
10. Sklearn (Utilización de métricas)
