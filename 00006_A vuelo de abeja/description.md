Para tener una idea general del comportamiento de los datos podemos graficar _la distribución de frecuencias_ de las distintas variables, empleando un histograma (función `histplot` de `seaborn` 🐚). Por ejemplo, así podemos obtener el histograma de `sepal_length`:


```python
sns.histplot(data = iris, x = "sepal_length", binwidth=0.25, kde = True)
```

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guia-python3-clustering/master/assets/sepal_length_hist_1672517852231.png" alt="sepal_length_hist_1672517852231.png" width="auto" height="auto">

Este gráfico nos muestra una distribución aproximada de la variable `sepal_length`, es decir, cuántas veces se repite un valor en un cierto rango (de tamaño definido por `binwidth`). Por ejemplo, nos muestra que los valores entre (aproximadamente) 4,25 y 4,5 se repiten cerca de 5 veces, mientras que aquellos entre (aproximadamente) 4,75 y 5, se repiten cerca de 20 veces. Podemos pensarlo como una representación gráfica de `value_counts`...

```python
iris["sepal_length"].value_counts().sort_index().plot.bar()
```

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guia-python3-clustering/master/assets/sepal_length_vc_1672518543133.png" alt="sepal_length_vc_1672518543133.png" width="auto" height="auto">

...pero más apta para valores continuos.

> Realizá este gráfico en tu cuaderno, probando con diferentes valores de `binwidth` y respondé: ¿qué sucede si aumentamos el tamaño de los rangos?

