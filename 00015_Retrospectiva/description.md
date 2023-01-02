Para evaluar cuán bien funcionó nuestro agrupamiento y saber si la cantidad de grupos es adecuada, podemos calcular cuán compactos son los grupos obtenidos. Partiendo de la base que un agrupamiento es mejor si todos los elementos del grupo están lo más cerca posible de su centro, podemos sumar las distancias de cada punto a su respectivo centro y usar eso como medida. A este valor se lo denomina _inercia_ y puede obtenerse haciendo:

```python
ム kmeans.inertia_
139.82049635974974
```

Si entrenamos `KMeans` con diferentes valores de `k` obtendremos valores de inercia también diferentes: naturalmente, cuanto más grande `k` :arrow_upper_right:, más pequeña la inercia será :arrow_lower_right:. Pero entonces la respuesta al problema de optimizar la inercia no tiene solución práctica, ¿verdad? ¡La inercia será `0` cuando `k` sea igual al número de observaciones! :broken_heart:

Bueno, no es necesario llegar a tal extremo, que además nos llevaría al absurdo de que cada grupo tuviera un único elemento. :stuck_out_tongue_closed_eyes: Por el contrario, lo que se suele aplicar es el _método del codo_, que consiste en encontrar un valor de `k` tal que el **cambio** en la inercia a partir de allí sea mucho más lento. ¿Y por qué se le llama método del codo? Esto es porque si graficamos los valores de inercia para cada uno de los `k` en el rango en que estamos buscando...

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guia-python3-clustering/master/assets/elbow_1672636555657.png" alt="elbow_1672636555657.png" width="auto" height="auto">

...hallaremos a nuestro `k` óptimo en el "codo" que se forma (en el gráfico de ejemplo se encuentra en `k = 4`).

> Veamos si se va entendiendo: ejecutá nuevamente al algoritmo `KMeans` sobre nuestro `iris_escalado`, pero probando con (todos los) valores de `k` desde `2` a `9` y guardá sus valores de inercia en un `DataFrame`. Luego realizá un gráfico de líneas de `k` vs `inercia`.
>
> ¿Cuál es el mejor valor de `k` según este criterio?
>
