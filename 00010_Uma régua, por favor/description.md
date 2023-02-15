Como você provavelmente concluiu, a classificação dos dados é subjetiva, pois depende de como medimos a similaridade entre as observações :straight_ruler:. E há muitas maneiras de fazer isso!

Uma delas é assumir que os dados são pontos no espaço, então se a _distância_ entre os pontos for definida e a separação entre dois registros for medida, pode-se obter a similaridade entre eles. Uma das maneiras mais fáceis de calcular a distância entre dois pontos é a **euclidiana**, baseada no famoso [Teorema de Pitágoras](https://pt.wikipedia.org/wiki/Teorema_de_Pit%C3%A1goras) 📐 que diz nós em um triângulo retângulo...

<a href="https://commons.wikimedia.org/w/index.php?curid=617373" target="_blank"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Rtriangle.svg/346px-Rtriangle.svg.png?20190718074431" alt="Triângulo retângulo, cortesia da Wikipedia" width="250px" height="auto"></a>


...o quadrado do comprimento da hipotenusa é equivalente à soma dos quadrados dos comprimentos de seus catetos:

<pre>
<code>c<sup>2</sup> = a<sup>2</sup> + b<sup>2</sup></code>
</pre>

Por exemplo, se quisermos calcular a distância euclidiana entre dois pontos em um plano, <code>(x<sub>1</sub>, y<sub>1</sub>)</code> e <code>(x<sub>2</sub>, y<sub>2</sub>)</code>, nós pode se basear neste teorema, assim:

<pre>
<code>distância<sup>2</sup> = (x<sub>1</sub> - x<sub>2</sub>)<sup>2</sup> + (y<sub>1</sub> - y<sub>2</sub>)<sup>2</sup></code>
</pre>

Como esta definição é tão útil, a biblioteca `scipy` já a suporta (na forma da função `cdist`):

```python
# cdist retorna um array de comparações entre os pontos do primeiro argumento
# e os do segundo argumento, mas neste caso estamos interessados apenas em seu primeiro e único valor
# portanto usamos [0][0]
ムcdist([(3, 4)], [(4, 5)], 'euclidean')[0][0]
1.4142135623730951 # porque 1.4142135623730951² = (3 - 4)² + (4 - 5)²
```

Mas será que tem algo errado com essa definição?

> O que acontecerá se os valores de `x` e `y` forem expressos em escalas muito diferentes? Por exemplo, e se todos os nossos pontos fossem semelhantes a `(1.05, 200)`, `(1.06, 100)`, `(1.08, 500)`, `(1.06, 300)`, etc?
>
> Para descobrir-lo, tente calcular as distâncias entre todos eles...
>
> ```python
> pontos = [(1.05, 200), (1.06, 100), (1.08, 500), (1.06, 300) ]
> pd.DataFrame(cdist(pontos, pontos, 'euclidean'))
> ```
> ... e estude os resultados.
