Para fazer um gráfico de linha você pode usar o método `plot.line` de `pandas` :panda_face:. Por exemplo, se sua tabela de inércia é chamada `inertias` e tem duas colunas `k` e `inertia`, você pode fazer assim:

```python
inertias.plot.line(x = "k", y = "inertia"))
```

Alternativamente, você pode fazer o mesmo (mas melhor :star2:) com `seaborn` usando `pointplot`:

```python
sns.pointplot(data = inertias, x = "k", y = "inertia")
```

Por outro lado, lembre-se que você pode criar um `DataFrame` do zero usando `pd.DataFrame()` e então adicionar suas colunas, uma a uma. :arrows_counterclockwise: E se isso ficar complicado, você também pode converter uma lista de dicionários em um `DataFrame` assim:

```python
ム pessoas = pd.DataFrame([
  {"name": "Dani", "age ": 31},
  {"nome": "Feli", "idade": 48},
  {"nome": "Umi", "idade": 25}
])
ム pessoas
	nome idade
0 Dani 31
1 Feli 48
2 Umi 25
```
