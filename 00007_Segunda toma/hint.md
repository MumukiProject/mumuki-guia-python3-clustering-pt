Para responder sobre la segunda afirmación quizás te sea útil utilizar la operación `describe` (si es que no lo hiciste ya). 

🥱 Y si no querés hacer 4 veces el mismo gráfico, quizás te convenga utilizar una repetición, pero procurando invocar `plt.show()` luego de cada gráfico para que no se superpongan: 

```python
for column in iris.columns:
 # ...tu gráfico acá...
 plt.show()
```
