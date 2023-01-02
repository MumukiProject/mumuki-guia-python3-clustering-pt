Cuando buscamos hacer predicciones, normalmente trabajamos con algoritmos **aprendizaje supervisado**: métodos que a partir de datos etiquetados, nos permiten reconstruir las relaciones entre las variables y las etiquetas. Dentro de este conjunto de algoritmos, podemos identificar dos grandes subtipos: **regresión** y **clasificación**. 

|                  |       Regresión         |     Clasificación           |
|:-----------------|-------------------------|-----------------------------|
|➡️ Variable de salida|Continua                 |Discreta                     |
|🔧 Ajuste            |Se intenta encontrar la línea de mejor ajuste, que prediga la salida con mayor precisión|Se intenta encontrar el límite de decisión, que puede dividir el conjunto de datos en diferentes clases |
|🔮 Predicción        |Se predice una cantidad para las observaciones  | Se etiquetan las observaciones con una de dos o más clases|

Ejemplos de regresión son los dos casos que trabajamos anteriormente: predecir el avance de una cierta enfermedad en función de datos biomédicos de los pacientes :thermometer_face:, o la cantidad de mensajes de texto que se enviarán en cierto año :vibration_mode:. Incluso problemas como estimar la temperatura de nuestro planeta en el futuro cercano pueded ser encarado como un problema de regresión 🌡. 

Por otro lado, ejemplos de clasificación son saber si un correo electrónico es _spam_ o no :envelope:, o identificar a partir de una imágen de una planta, cuál es su especie :sunflower:.  

Pero en ciertas ocasiones debemos trabajar con datos para los que no contamos con una cantidad o etiqueta. En estos casos, deberemos entrenar a nuestros algoritmos de aprendizaje automático **sin supervisión**, que nos permitirán obtenerobtener información, sin conocer previamente cuál será la salida. 


> 🤔 ¿Aprender sin supervisión? ¿Cómo es eso posible? ¿Se te ocurre algún aspecto que un algoritmo de aprendizaje automático podría identificar sin supervisión?

