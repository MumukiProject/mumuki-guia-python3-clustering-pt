Perfeito! Se quiséssemos saber, por exemplo, não _quantos_ membros foram atribuídos a cada grupo, mas _quais_, poderíamos fazer o seguinte:

```python
iris_labeled = iris.copy()
iris_labeled["cluster"] = kmeans.labels_
iris_labeled
```

Experimente no seu caderno!