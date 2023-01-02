Quizás los resultados anteriores no sean tan evidentes como esperábamos :confused:. 

Para entenderlos mejor resulta en general más útil graficar la distribución de puntos de los pares de variables, pintando cada punto según el color correspondiente al etiquetado :label:. Por ejemplo, así podemos graficar `petal_length` vs `petal_width` :sparkles::

```python
sns.scatterplot(
  data = iris_etiquetado,
  x = "petal_length", 
  y = "petal_width", 
  hue = "cluster", 
  palette = "tab10", # más información sobre colores, acá: https://seaborn.pindice_2data.org/tutorial/color_palettes.html 
  alpha = 0.5
)
```

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guia-python3-clustering/master/assets/petal_vs_petal_1672615508851.png" alt="petal_vs_petal_1672615508851.png" width="auto" height="auto">


> Pero para entender realmente al modelo, vamos a necesitar graficar cada par de variables. ¿Te animás a intentarlo? ¿Qué conclusiones podés sacar?

