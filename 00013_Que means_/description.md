Que coisa? 🤌 Não não, estamos falando de _K-means_! :sweat_smile:

K-means (ou _k-medias_, em portugês) é um método que agrupa as observações nos _melhores_ K grupos distintos, ou seja, os K _clusters_ com a menor variância interna (_intra-cluster variation_) possível. Em outras palavras, as observações são divididas em K clusters de forma que a soma das variâncias internas de todas elas seja mínima.

👣 Este método repete uma série de passos...

 1. Definir o número K de clusters que deseja criar;
 2. Selecionar aleatoriamente k observações do conjunto de dados como [_centróides_](https://pt.wikipedia.org/wiki/Centroide) iniciais, ou seja, os dados aos quais a distância é calculada para delimitar o grupo com a menor variância interna;
 3. Calcular a distância de todos os dados ao centróide, para definir qual deles está mais próximo;
 4. Para cada um dos K clusters, recalcular o seu centróide. A posição do centróide atualiza-se tomando como novo centróide a posição da média das observações pertencentes ao referido grupo;
 5. Repetir os passos 3 e 4 até que os centróides não se movam, ou se movam abaixo de uma distância limite em cada etapa, ou o número de iterações definido antecipadamente seja alcançado.

...até encontrar os melhores k grupos:

<a href="https://commons.wikimedia.org/wiki/File:K-means_convergence.gif" target="_blank"><img src="https://upload.wikimedia.org/wikipedia/commons/e/ea/K-means_convergence.gif" alt="KMeans convergência cortesia da Wikipedia" width="250px" height="auto"></a>

Por exemplo, se nós definir arbitrariamente que vamos procurar 3 grupos...

```python
k = 3
```
... com `scikit-learn` podemos implementar este método usando `KMeans`:

```python
kmeans = KMeans (
  n_clusters = k,
  init="random",
  n_init=10,
  max_iter=300,
  random_state=42
)
kmeans.fit(iris_scaled)
```

Em seguida, podemos consultar qual cluster foi encontrado para cada observação...

``` python
kmeans.labels_
```
...e os centróides:

```python
kmeans.cluster_centers_
```

> 🫵 É a sua vez! Execute o código acima no seu caderno e responda: quantos membros o `KMeans` encontrou em cada grupo?
