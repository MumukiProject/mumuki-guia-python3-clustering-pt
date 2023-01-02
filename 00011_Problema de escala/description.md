Como vimos, es necesario asegurarnos que los datos estén expresados en _dimensiones_ similares. ¿Eso significa que deberemos descartar nuestros datos cuando no cumplan esta propiedad?

¡No! Afortundamente este problema tiene una respuesta menos radical: el _escalado de los datos_ :person_climbing:. Este procedimiento nos permitirá ajustar los datos y asegurarnos de que aún cuando algunas variables tomen valores más grandes no se usarán como predictor principal a la hora de clasificar. :warning: ¡Es un procedimiento es de vital importancia y debemos realizarlo antes de comenzar agrupar nuestros datos!

El escalado puede ser resuelto muy fácilmente usando el `StandardScaler`, del módulo `scikitlearn` :tada::

```python
scaler = StandardScaler()
iris_escalado = scaler.fit_transform(iris)
```

> Ejecutá este código en tu cuaderno. ¿Qué hizo? ¿Cómo quedaron los datos?

