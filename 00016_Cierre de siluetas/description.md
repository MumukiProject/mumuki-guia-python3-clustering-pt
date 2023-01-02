Otra propiedad que nos puede interesar de una agrupación es que todos los puntos de un grupo estén bien _juntitos_ :hugging:  pero a la vez bien separados del resto de los puntos en otros grupos :dash:. 

Esta idea se puede encontrar en el coeficiente de _silhouette_ (:bust_in_silhouette silueta, en inglés), que para miembro del cluster nos dice si está cerca de su cluster y lejos del resto (coeficiente cercano a `1`) o si está lejos de su cluster y cerca del resto (coeficiente cercano a `-1`). :person_gesturing_no: Esto nos da dos heurísticas para _rechazar_ (pero no así elegir) valores concretos de `k`: 

  1. Si hay clusters donde todos los coeficientes de silhouette de sus miembros están por debajo del valor promedio general, o bien
  2. si hay clusters donde muchos de sus miembros tiene un valor inferior a cero (que indica un miembro mal clasificado).

Con `scikit-learn` podemos calcular tanto el promedio general de silhouette... 
  
```python
silhouette_score(iris_escalado, kmeans.labels_)
```

...como el valor de este coeficiente para cada observación:

```python
silhouette_samples(iris_escalado, kmeans.labels_)
```

No obstante, resulta mucho más cómodo realizar este análisis gráficamente. Para ello vamos a instalar una nueva biblioteca llamada `yellowbrick`...

```python
!pip install yellowbrick
```

...y utilizar su `SilhouetteVisualizer` así (para `k = 3`):

```python
from yellowbrick.cluster import SilhouetteVisualizer

kmeans = KMeans(n_clusters=3, init='random', n_init=10, max_iter=300, random_state=42)
visualizer = SilhouetteVisualizer(kmeans, colors='yellowbrick')
visualizer.fit(iris_escalado)
```

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guia-python3-clustering/master/assets/silhouette_k3_1672641063335.png" alt="silhouette_k3_1672641063335.png" width="auto" height="auto">


:eyes: En este gráfico podemos observar que: 
 
 1. Ninguno de los clusters tiene a la totalidad de sus miembros debajo del promedio (línea roja punteada);
 2. Sólo el tercer cluster tiene algunos (pocos) miembros por debajo de `0`

> ¡Terminemos nuestro trabajo y terminemos de definir si nos quedamos con `3` o `5` como valor de `k`! 
>
> Realizá las gráficas de silhouette para `k`, desde `2` a `6`. :x: ¿Cuáles `k` deberíamos **descartar** según las mismas? 


