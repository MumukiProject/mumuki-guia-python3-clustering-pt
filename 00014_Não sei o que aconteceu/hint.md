Plotar todas as variáveis manualmente pode ser tedioso, e generalizar essa tarefa também não é trivial 😰. Como ajuda, deixamos o código já resolvido:

```python
colores = "tab10" 
columnas = iris.columns

for indice_1 in range(0, len(columnas)):
  for indice_2 in range(indice_1 + 1, len(columnas)): 

    print(columnas[indice_1], "vs", columnas[indice_2])
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

Como verás, es similar al que ya te habíamos presentado, pero: 

1. Estamos graficando las variables escaladas;
2. Superponemos un segundo gráfico con los centros de cada cluster.
 