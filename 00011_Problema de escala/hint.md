Probablemente hayas notado que `iris_escalado` no paracer ser un DataFrame. Si no te terminás de dar cuenta, podés convertirlo a uno haciendo lo siguiente: 

```python
pd.DataFrame(iris_escalado, columns=iris.columns)
``` 

O incluso:

```python
pd.DataFrame(iris_escalado, columns=iris.columns).describe()
```