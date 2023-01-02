Perfeito! Se quiséssemos saber, por exemplo, não _quantos_ membros foram atribuídos a cada grupo, mas _quais_, poderíamos fazer o seguinte:

```python
iris_rotulado = iris.copy()
iris_rotulado["cluster"] = kmeans.labels_
iris_rotulado
```

Experimente no seu caderno!