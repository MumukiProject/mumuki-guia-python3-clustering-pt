Ahora que pudimos observar cómo se comportan las variables, nos puede ser de gran utilidad estudiar la correlación entre las mismas. De este modo sabremos si el comportamiento (crecimiento o disminución) de una variable, se debe o está influenciada por otra. 

Como vimos anteriormente, podemos detectar correlaciones con una matriz de correlación…

```python
iris.corr("spearman")
```

...o un mapa de calor:

```python
sns.heatmap(iris.corr("spearman").abs())
``` 

Pero otra gran herramienta para descubrir correlaciones entre variables es usar los `pairplots`, que producen un gráfico de dispersión por cada par de variables numéricas :open_mouth::

```python
sns.pairplot(iris)
```

> Realizá en tu cuaderno la matriz de correlación y el mapa de calor sobre la tabla `iris` y  contrastá 📈 los resultados contra su `pariplot` correspondiente. ¿Existe alguna correlación entre algunas de las variables?
