Para entender como funciona o clustering, vamos nos voltar para outro exemplo bem conhecido, [o conjunto de dados Iris](https://pt.wikipedia.org/wiki/Conjunto_de_dados_flor_Iris), gerado por em 1936 📅 de Ronald Fischer, que consiste num conjunto de observações feitas sobre as características de diferentes espécies de plantas com flores 🌼.

Para começar, vamos importar e configurar as bibliotecas `scikit-learn`, `pandas`, `scipy` e `seaborn`, como fizemos anteriormente:

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn como sns

de scipy.spatial.distance importar cdist

de sklearn.cluster importar KMeans
de sklearn.preprocessing importar StandardScaler
de sklearn.metrics importar silhouette_samples, silhouette_score

plt.rcParams['image.cmap'] = "bwr"
plt.rcParams['savefig .bbox'] = "tight"
plt.style.use('ggplot')
```

👀 Desta vez, se você olhar de perto e comparar com nossa regressão linear `imports`, notará que estamos importando outros módulos como `sklearn.cluster` e `sklearn.preprocessing`. Como veremos mais adiante, isso é intencional! :wink:

Por outro lado, novamente o lote de dados em que estamos interessados vem com `scikit-learn` , e podemos carregá-lo assim:

```python
from sklearn import datasets

iris = datasets.load_iris(as_frame=True )
print (iris['DESCR'])

iris = iris["data"]
iris.columns = [col.replace(" (cm)", "").replace(" ", "_") for col in iris .columns ]
iris
```

> Agora é a sua vez! Carregue este lote de dados em um novo notebook e responda qual das seguintes afirmações está correta:
