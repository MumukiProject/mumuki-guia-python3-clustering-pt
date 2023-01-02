Para ter uma ideia geral do comportamento dos dados, podemos plotar _a distribuição de frequência_ das diferentes variáveis, usando um histograma (função `histplot` de `seaborn` 🐚). Por exemplo, podemos obter o histograma de `sepal_length` assim:


```python
sns.histplot(data = iris, x = "sepal_length", binwidth=0.25, kde = True)
```

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guia-python3-clustering/master/assets/sepal_length_hist_1672517852231.png" alt="sepal_length_hist_1672517852231.png" width="auto" height="auto">

Este gráfico nos mostra um distribuição aproximada da variável `sepal_length`, ou seja, quantas vezes um valor se repete em um determinado intervalo (de tamanho definido por `binwidth`). Por exemplo, mostra-nos que os valores entre (aproximadamente) 4,25 e 4,5 repetem-se cerca de 5 vezes, enquanto os valores entre (aproximadamente) 4,75 e 5 repetem-se cerca de 20 vezes. Podemos pensar nisso como um gráfico de `value_counts`...

```python
iris["sepal_length"].value_counts().sort_index().plot.bar()
```

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guia-python3-clustering/master/assets/sepal_length_vc_1672518543133.png" alt="sepal_length_vc_1672518543133.png" width="auto" height="auto">

...mas mais adequado para valores contínuos.

> Faça esse gráfico no seu cuaderno, experimentando diferentes valores de `binwidth` e responda: o que acontece se aumentarmos o tamanho dos bins?
