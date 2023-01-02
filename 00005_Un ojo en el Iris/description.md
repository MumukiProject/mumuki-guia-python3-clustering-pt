Para entender cómo funciona el clustering, vamos a recurrir a otro ejemplo bien conocido,  [el dataset Iris](https://en.wikipedia.org/wiki/Iris_flower_data_set), generado por en 1936 📅 por Ronald Fischer, que consiste en un conjunto de observaciones realizadas sobre las característica de distintas especies de plantas con flores  🌼.

Para empezar, vamos a importar y configurar las bibliotecas `scikit-learn`, `pandas`, `scipy` y `seaborn`, como lo hemos hecho previamente: 

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

from scipy.spatial.distance import cdist

from sklearn.cluster import KMeans
from sklearn.preprocessing import StandardScaler
from sklearn.metrics import silhouette_samples, silhouette_score 

plt.rcParams['image.cmap'] = "bwr"
plt.rcParams['savefig.bbox'] = "tight"
plt.style.use('ggplot')
``` 

👀 En esta ocasión, si mirás atentamente y lo comparás con nuestros `imports` de regresión lineal, notarás que estamos importando otros módulos como `sklearn.cluster` y `sklearn.preprocessing`. Como veremos más adelante, ¡esto es intencional!  :wink: 

Por otro lado, nuevamente el lote de datos que nos interesa viene con `scikit-learn` , y podemos cargarlo de la siguiente forma:

```python
from sklearn import datasets

iris = datasets.load_iris(as_frame=True)
print(iris['DESCR'])

iris = iris["data"]
iris.columns = [col.replace(" (cm)", "").replace(" ", "_") for col in iris.columns]
iris
``` 

>  ¡Ahora te toca a vos! Cargá en un nuevo cuaderno este lote de datos y  respondé cuáles de las siguientes afirmaciones son correctas:
