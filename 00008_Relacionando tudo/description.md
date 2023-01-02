Agora que conseguimos observar como as variáveis se comportam, pode ser muito útil estudar a correlação entre elas. Desta forma saberemos se o comportamento (crescimento ou diminuição) de uma variável é devido ou influenciado por outra.

Como vimos anteriormente, podemos detectar correlações com uma matriz de correlação…

```python
iris.corr("spearman")
```

...ou um mapa de calor:

```python
sns.heatmap(iris.corr("spearman").abs())
```

Mas outra ótima ferramenta para descobrir correlações entre variáveis é usar `pairplots`, que produz um gráfico de dispersão para cada par de variáveis numéricas :open_mouth::

```python
sns.pairplot(iris)
```

> Faça a matriz de correlação e o mapa de calor na tabela `íris` em seu caderno e compare 📈 os resultados com o `pairplot` correspondente. Existe uma correlação entre algumas das variáveis?
