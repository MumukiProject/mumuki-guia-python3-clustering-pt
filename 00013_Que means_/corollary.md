¡Perfecto! Si quisieramos por ejemplo saber no _cuántos_ miembros fueron asignados a cada grupo, sino _cuáles_, podríamos hacer lo siguiente: 

```python
iris_etiquetado = iris.copy()
iris_etiquetado["cluster"] =  kmeans.labels_ 
iris_etiquetado
```

¡Probalo en tu cuaderno!