# Predicción-Fraude-Tarjetas 💳🕵️‍♂️💻

Este repositorio tiene por objeto mostrar, a golpe de vistazo rápido, las fases de preprocesamiento y modelado de machine learning para la predicción de fraude en transacciones con tarjetas de crédito.
Con objeto de simplificar al máximo, buscando hacer posible ese vistazo rápido, el repositorio contiene un único script listo para ser ejecutado, previa descarga de la base de datos.

El problema a resolver es la **predicción del fraude en una transacción con tarjeta de crédito a partir de datos sobre la propia transacción y sobre la tarjeta de crédito con la que se realiza**.

## Base de datos
**Nota:** no es objeto de este repositorio mostrar las tareas de limpieza, mergeado ni análisis exploratorio de las distintas bases de datos utilizadas para la obtención del dataset de trabajo. El script muestra únicamente el preprocesado final (del dataset de trabajo) previo al modelado, aprendizaje y predicción. 

El **dataset de trabajo** puede descargarse [aquí](https://drive.google.com/file/d/1CSqUq_aPHoFNEbhUoD7RR7N1ybD8rOYV/view).


Partimos de un dataset base descargado de kaggle, al que se puede acceder desde [aquí](https://www.kaggle.com/datasets/dermisfit/fraud-transactions-dataset). Es recomendable pinchar el enlace para entender, también de un vistazo rápido, el tipo de información contenida en las variables de este dataset base.

A modo de resumen apuntamos que este dataset contiene variables con información del titular de la tarjeta con la que se ha hecho la transacción e información sobre la propia transacción, así como la variable "is_fraud" que indica si se trata o no de una transacción fraudulenta.

A este dataset base se le han añadido nuevas variables, las cuales se detallan a continuación.
+ Tasa de desempleo por estado, dataset de kaggle que puede descargarse [aquí](https://www.kaggle.com/datasets/justin2028/unemployment-in-america-per-us-state), entendiendo que el desempleo podría guardar relación con el fraude.
+ Cierre de la bolsa (S&P 500), datos de marketwatch que pueden descargarse [aquí](https://www.marketwatch.com/investing/index/spx/download-data), entendiendo que la bolsa y su impacto en la economía podrían guardar relación con el fraude.
+ Tipo de cambio euro/dólar, datos del Banco Central Europero que pueden descargarse [aquí](https://data.ecb.europa.eu/data/datasets/EXR/EXR.D.USD.EUR.SP00.A), entendiendo que el par euro/dólar podría guardar relación con el fraude.
+ Tasa de criminalidad por estado, datos de la oficina federal de investigación de EEUU que pueden descargarse [aquí](https://cde.ucr.cjis.gov/LATEST/webapp/#/pages/explorer/crime/crime-trend), entendiendo que el nivel de criminalidad podría guardar relación con el fraude.
+ Festivo sí/no, entendiendo que los días festivos podrían guardar relación con el fraude.
+ Además, a partir de la variable del dataset base “trans_date_trans_time”, se han generado nuevas variables como año, mes, día y hora de la transacción, entendiendo que las mismas podrían guardar relación con el fraude.
+ A partir de las variables "lat", "long", "merch_lat" y "merch_long" se han generado las variables "dist_lat" y "dist_long", entendiendo que la distancia del lugar de la transacción respecto al domicilio del titular de la tarjeta podría guardar relación con el fraude.
+ Por último, a partir de la variable del dataset base “dob” (Date of birth of the card holder) se ha generado la variable “age”, entendiendo que la edad del titular de la tarjeta podría guardar relación con el fraude.

El dataset resultante de añadir todas estas variables al dataset base sería el dataset de trabajo enlazado arriba.
