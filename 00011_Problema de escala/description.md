Como vimos, é necessário garantir que os dados sejam expressos em _dimensões_ semelhantes. Isso significa que devemos descartar nossos dados quando eles não atendem a essa propriedade?

Não! Felizmente, esse problema tem uma resposta menos radical: _escalonamento de dados_ :person_climbing:. Esse procedimento nos permitirá ajustar os dados e garantir que, mesmo quando algumas variáveis assumem valores maiores, elas não serão usadas como o principal preditor na classificação. :warning: É um procedimento de vital importância e devemos realizá-lo antes deagrupar nossos dados!

O dimensionamento pode ser resolvido facilmente usando o `StandardScaler`, do módulo `scikitlearn` :tada::

```python
scaler = StandardScaler()
iris_escalado = scaler.fit_transform(iris)
```

> Execute este código no seu caderno. Que fez? Como ficaram os dados?

