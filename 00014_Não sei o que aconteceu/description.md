Talvez os resultados acima não sejam tão óbvios quanto esperávamos :confused:.

Para entendê-los melhor, geralmente é mais útil graficar a distribuição de pontos para os pares de variáveis, pintando cada ponto de acordo com a cor correspondente à marcação :label:. Por exemplo, podemos traçar `petal_length` vs `petal_width` :sparkles::

```python
sns.scatterplot(
  data = label_iris,
  x = "petal_length",
  y = "petal_width",
  hue = "cluster",
  paleta = " tab10", # mais informações sobre cores, aqui: https://seaborn.pydata.org/tutorial/color_palettes.html
  alpha = 0.5
)
```

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guia-python3-clustering/master/assets/petal_vs_petal_1672615508851.png" alt="petal_vs_petal_1672615508851.png" width="auto" height="auto">

> Mas para realmente entender o modelo, vamos precisar graficar cada par de variáveis. Você se atreve a tentar? Que conclusões você pode tirar?
