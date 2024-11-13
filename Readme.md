# Proyecto Individual Num 1 MLOps:
### Sistema de Recomendación de Películas 
Este proyecto, ha sido un gran desafio, ya que asumo, el rol de un Data Enginer, encargado de transformar datos crudos y sin procesar en algo funcional.

## Misión
Nuestro cliente es una start-up que provee servicios de agregación de plataformas de streaming. La información donde almacena los datos nuestro cliente, estan en un estado deficiente, trabajosos, anidados y no estan automatizados.

## Objetivo
El objetivo a cumplir, es desarrollar un sistema de recomendación de peliculas que sea funcional, que satisfaga los minimos requerimientos que se pide y que sea escalable. A su vez, que sea facil de mantener en el entorno de producción.
Para esto, resultara necesario hacer la transformación de datos(ETL) y un Analísis Exploratorio de Datos razonable y entendible.

## Proceso de ETL
En este proceso de ETL (Extracción, Transformación y Carga), se busco detallar paso a paso el como se preparan los datos. La información original, estaban en 2 archivos csv, movies_dataset.csv y credits.csv , los datos de estos archivos estaban anidados, lo que requeria una serie de transformaciones para poder ser entendidos y utilizados.
Empezamos entendiendo los datasets, eliminando columnas redundantes o que en general contenian un gran porcentaje de nulos/vacios, haciendo ams liviano el dataset y quitando la complejidad que esto conllevaba. No todo fue eliminar, tambien se agregaron columnas nuevas a los datasets, como por el ejemplo, el año de lanzamiento, el genero, todo esto a partir de columnas anidadas que tenian esta informacion en diccionarios anidados.
Todo esto se hizo con funciones creadas para desanidar columnas, y asi "liberar" la información que requeriamos. Seguido de esto, se realizó un tratamiento preliminar de valores nulos, datos faltantes y duplicados, asegurando que los datos estuvieran en un estado adecuado para su posterior análisis y uso en las funciones requeridas. Finalmente, toda la información procesada se almacenó en un archivo tipo .parquet. Se ha elegido este formato para almacenar los datos procesados debido a su eficiencia en la compresión y almacenamiento en columnas, lo que permite una lectura rápida y una menor utilización de memoria.

## EDA (Analísis Exploratorio de Datos)
El EDA , se hizo del archivo.parquet, resultante de la limpieza de los 2 datasets en crudo que se nos entrego. El Analísis Exploratorio de Datos, nos permite conocer los datos que estamos trabajando, nos permite entenderlos, encontrar outliers, anomalias, cantidades, porcentajes. Esto claramente explicado y visualizado por medio de graficas, permitiendo que una gran comprensión de los datos mismos. Esto a su vez, nos da una gran perpectiva del comportamiento de nuestro objetivo/clientes , entendemos sus preferencias y tendencias. A su vez, nos da una claro indicador de negocios, como por ejemplo, las ganancias, las inversiones, la rentabilidad de una pelicula. Todo esto, nos da la información necesaria para poder tomar acción o tomar decisiones a cerca del tema.

## Modelo de Recomendación
Al final del archivo EDA, se presenta un análisis detallado del proceso de preparación de datos para el modelo de recomendación. Se optó por utilizar TfidfVectorizer para la vectorización del texto debido a la inconsistencia en los datos numéricos, junto con la similitud del coseno para calcular la similitud entre películas. La función de recomendación devuelve un conjunto de 5 películas relacionadas con el título proporcionado, ordenadas de acuerdo con su puntuación promedio, basada en las valoraciones encontradas en la base de datos en los elementos extraídos del título, género y descripción de la película.

## Herramientas / Librerias 
- Numpy
- Pandas
- Matplotlip
- Seaborn
- String
- re
- NLTK
- sklearn
- Fastapi
- Wordcloud
- Matplotlip.pyplot
