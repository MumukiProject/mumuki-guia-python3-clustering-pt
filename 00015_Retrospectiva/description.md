Para avaliar o quão bem nosso clustering funcionou e se o número de clusters é adequado, podemos calcular o quão compactos são os clusters resultantes. Partindo da base de que um agrupamento é melhor se todos os elementos do grupo estiverem o mais próximo possível do seu centro, podemos somar as distâncias de cada ponto ao seu respectivo centro e usar isso como medida. Este valor é chamado _inertia_ e pode ser obtido fazendo:

```python
ム kmeans.inertia_
139.82049635974974
```

Se treinarmos `KMeans` com diferentes valores de `k` também obteremos diferentes valores de inércia: é claro, quanto maior `k` :arrow_upper_right:, menor será a inércia :arrow_lower_right:. Mas então a resposta para o problema de otimização da inércia não tem solução prática, certo? A inércia será `0` quando `k` for igual ao número de observações! :broken_heart:

Bem, não é necessário ir a tal extremo, o que também nos levaria ao absurdo de cada grupo ter um único elemento. :stuck_out_tongue_closed_eyes: Em vez disso, o que geralmente é aplicado é o _método do cotovelo_, que é encontrar um valor de `k` de modo que a **mudança** na inércia a partir daí seja muito mais lenta. E por que é chamado de método do cotovelo? Isso ocorre porque se plotarmos os valores de inércia para cada um dos `k` no intervalo que estamos procurando...

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guia-python3-clustering/master/assets/iris_elbow_1672638446790.png" alt="iris_elbow_1672638446790.png" width="auto" height="auto">

...encontraremos nosso `k` ótimo no "cotovelo" que é formado (em o exemplo do gráfico é encontrado em `k = 4`).

> Vamos ver se ficou claro: execute o algoritmo `KMeans` novamente em nosso `scaled_iris`, mas tente com (todos) os valores de `k` de `2` a `9` e salve seus valores de inércia em um `DataFrame`. Em seguida, faça um gráfico de linha de `k` vs `inércia`.
>
> Qual é o melhor valor de `k` de acordo com este critério?
>
