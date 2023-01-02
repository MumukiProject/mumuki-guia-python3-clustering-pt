Graficar todas as variáveis manualmente pode ser tedioso, e generalizar essa tarefa também não é trivial 😰. Como ajuda, deixamos o código já resolvido:

```python
colores = "tab10" 
colunas = iris.columns

for indice_1 in range(0, len(colunas)):
  for indice_2 in range(indice_1 + 1, len(colunas)): 

    print(colunas[indice_1], "vs", colunas[indice_2])
    sns.scatterplot(
        x = iris_escalado[:,indice_1], # esta sintaxe nos permite acessar a enésima coluna
        y = iris_escalado[:,indice_2], # de uma matriz
        hue = kmeans.labels_, 
        palette = colores, 
        alpha = 0.5
    )
    sns.scatterplot(
        x = kmeans.cluster_centers_[:,indice_1], 
        y = kmeans.cluster_centers_[:,indice_2],  
        palette = colores, 
        hue = range(0, k), 
        legend = False, 
        s=200
    )
    plt.show()
```

Como você verá, é semelhante ao que já apresentamos, mas:

1. Estamos graficando as variáveis escaladas;
2. Sobrepomos um segundo grafo com os centróides de cada cluster.
 