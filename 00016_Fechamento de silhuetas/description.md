Outra propriedade que pode nos interessar em um agrupamento é que todos os pontos de um grupo estão bem _juntos_ :abraçados: mas ao mesmo tempo bem separados do restante dos pontos de outros grupos :traço :.

Essa ideia pode ser encontrada no coeficiente de _silhouette_ (:bust_in_silhouette silhouette, em inglês), que para um membro do cluster nos diz se ele está próximo de seu cluster e distante dos demais (coeficiente próximo a `1`) ou se é longe de seu cluster.cluster e perto do resto (coeficiente próximo a `-1`). :person_gesturing_no: Isso nos dá duas heurísticas para _rejeitar_ (mas não escolher) valores concretos de `k`:

  1. Se houver clusters onde todos os coeficientes de silhueta de seus membros estão abaixo do valor médio geral, ou
  2. se houver são clusters onde muitos de seus membros têm um valor menor que zero (indicando um membro mal classificado).

Com `scikit-learn` podemos calcular tanto a média geral da silhueta...
 
```python
silhouette_score(iris_escalado, kmeans.labels_)
```

...como o valor deste coeficiente para cada observação:

```python
silhouette_samples(iris_escalado, kmeans.labels_)
```

No entanto, é muito mais conveniente realizar esta análise graficamente. Para fazer isso vamos instalar uma nova biblioteca chamada `yellowbrick`...

```python
!pip install yellowbrick
```

...e usar seu `SilhouetteVisualizer` assim (para `k = 3`):

` ``python
from yellowbrick.cluster import SilhouetteVisualizer

kmeans = KMeans(n_clusters=3, init='random', n_init=10, max_iter=300, random_state=42)
visualizer = SilhouetteVisualizer(kmeans, colors='yellowbrick')
visualizer.fit (iris_scaling)
` ``

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guide-python3-clustering/master/assets/silhouette_k3_1672641063335.png" alt="silhouette_k3_1672641063335.png" width="auto " height=" auto">


:eyes: Neste gráfico podemos ver que:
 
 1. Nenhum dos clusters tem todos os seus membros abaixo da média (linha vermelha pontilhada);
 2. Apenas o terceiro cluster tem alguns (poucos) membros abaixo de `0`

> Vamos terminar nosso trabalho e terminar de definir se ficamos com `3` ou `5` como o valor de `k`!
>
> Faça os gráficos de silhueta para `k`, de `2` a `6`. :x: Qual `k` devemos **eliminar** com base neles?
