Muito bom! Nem todas as variáveis seguem a mesma distribuição. Na verdade, `sepal_width` segue uma distribuição _normal_ (ou paramétrica), que podemos reconhecer por ter um centro e ser simétrica...

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guia-python3-clustering/master/assets/sepal_with_hist_1672522430362.png" alt="sepal_with_hist_1672522430362.png" width="auto" height="auto">

...enquanto `petal_length` e `petal_width`, não:

<img src="https://raw.githubusercontent.com/MumukiProject/mumuki-guia-python3-clustering/master/assets/petal_length_hist_1672522445222.png" alt="petal_length_hist_1672522445222.png" width="auto" height="auto">

<img src= " https://raw.githubusercontent.com/MumukiProject/mumuki-guia-python3-clustering/master/assets/petal_width_hist_1672522456715.png" alt="petal_width_hist_1672522456715.png" width="auto" height="auto">

Conforme mencionado na lição anterior, isso pode ser verificado mais formalmente usando um teste de normalidade como Shapiro-Wilk...

```python
from scipy import stats

# Nota: as distribuições normais também são conhecidas como paramétricas.
# Da mesma forma, aqueles que não, são conhecidos como não paramétricos
def e_no_parametrica(column):
  return stats.shapiro(iris[column]).pvalue < 0.05
```
...e chamando assim:

``` python
ム e_no_parametrica("sepal_width")
False
ム e_no_parametrica("petal_length")
True
ム e_no_parametrica("petal_width")
True
```

Mas agora que sabemos tudo isso, quantos tipos de plantas você acha que existem? :timer: Reserve alguns minutos para pensar sobre isso e esperamos por você no próximo exercício.
