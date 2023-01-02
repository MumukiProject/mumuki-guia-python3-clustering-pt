¡Muy bien! No todas las variables siguen la misma distribución. De hecho, `sepal_width` sigue una _distribución normal_ (o paramétrica), la cual podemos reconocer por tener un centro y ser simétrica... 

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guia-python3-clustering/master/assets/sepal_with_hist_1672522430362.png" alt="sepal_with_hist_1672522430362.png" width="auto" height="auto">

...mientras que `petal_length` y `petal_width`, no:

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guia-python3-clustering/master/assets/petal_length_hist_1672522445222.png" alt="petal_length_hist_1672522445222.png" width="auto" height="auto">

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guia-python3-clustering/master/assets/petal_width_hist_1672522456715.png" alt="petal_width_hist_1672522456715.png" width="auto" height="auto">

Como mencionamos en la lección anterior, esto se puede comprobar de forma más formal utilizando una prueba de normalidad como la de Shapiro-Wilk...

```python
from scipy import stats

def es_no_parametrica(columna):
  return stats.shapiro(iris[columna]).pvalue < 0.05
```
...e invocándola así:

```python
ム es_no_parametrica("sepal_width")
False
ム es_no_parametrica("petal_length")
True
ム es_no_parametrica("petal_width")
True
```

Pero ahora que sabemos todo esto, ¿cuántos tipos de plantas crees que existen? :timer: Tomate unos minutos para pensarlo y te esperamos en el siguiente ejercicio. 

