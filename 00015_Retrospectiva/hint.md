Para hacer un gráfico de líneas podés usar el método `plot.line` de `pandas` :panda_face:. Por ejemplo, si tu tabla de inercias se llama `inercias` y tiene dos columnas `k` e `inercia`, podés hacerlo así:

```python
inercias.plot.line(x = "k", y = "inercia")
```

Alternativamente, podés hacer lo mismo (pero más bonito :star2:) con `seaborn` usando `pointplot`: 

```python
sns.pointplot(data = inercias, x = "k", y = "inercia")
```

Por otro lado, recordá que podés crear un `DataFrame` desde cero usando `pd.DataFrame()` y luego agregarle, una a una, sus columnas. :arrows_counterclockwise: Y si eso se vuelve complicado, también podés convertir una lista de diccionarios en un `DataFrame` de la siguiente forma: 

```python
ム personas = pd.DataFrame([
  {"nombre": "Dani", "edad": 31}, 
  {"nombre": "Feli", "edad": 48}, 
  {"nombre": "Umi", "edad": 25}
])
ム personas
    nombre 	edad
0 	Dani 	  31
1 	Feli 	  48
2 	Umi 	  25
```