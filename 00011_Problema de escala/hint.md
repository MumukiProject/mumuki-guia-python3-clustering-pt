Você provavelmente notou que `iris_escalado` não parece ser um DataFrame. Se você não percebeu, pode convertê-lo em um fazendo o seguinte:
 
```python
pd.DataFrame(iris_escalado, columns=iris.columns)
```
 
Ou ainda:
 
```python
pd.DataFrame(iris_escalado, columns=iris.columns).describe()
```