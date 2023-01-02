Como habrás probablemente concluido, la clasificación de los datos es subjetiva, porque depende de cómo midamos la similitud entre las observaciones :straight_ruler:. ¡Y existen muchas formas de hacerlo! 

Una de ellas consiste en asumir que los datos son puntos en el espacio, por lo que si se define _la distancia_ entre los puntos y se mide la separación entre dos registros, podrá obtenerse la similitud entre estos. Una de las formas más sencillas para calcular la distancia entre dos puntos es la **euclídea**, basada en el famoso [Teorema de Pitágoras](https://es.wikipedia.org/wiki/Teorema_de_Pit%C3%A1goras) 📐 que nos dice en un triángulo rectángulo...

<a href="https://commons.wikimedia.org/w/index.php?curid=617373" target="_blank"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Rtriangle.svg/346px-Rtriangle.svg.png?20190718074431" alt="Triángulo rectángulo, cortesía de Wikipedia" width="250px" height="auto"></a>


... el cuadrado de la longitud de la hipotenusa es equivalente a la suma de los cuadrados de las longitudes de sus catetos:

<pre>
<code>c<sup>2</sup> = a<sup>2</sup> + b<sup>2</sup></code>
</pre>

Por ejemplo, si queremos calcular la distancia euclídea entre dos puntos sobre un plano, <code>(x<sub>1</sub>, y<sub>1</sub>)</code> y <code>(x<sub>2</sub>, y<sub>2</sub>)</code>, podemos basarnos en este teorema, así:

<pre>
<code>distancia<sup>2</sup> = (x<sub>1</sub> - x<sub>2</sub>)<sup>2</sup> + (y<sub>1</sub> - y<sub>2</sub>)<sup>2</sup></code>
</pre>

Como esta definición es tan útil, la biblioteca `scipy` ya cuenta con ella (en la forma de la función `cdist`): 

```python
# cdist devuelve una matriz de comparaciones entre los puntos del primer argumento
# y los del segundo argumento, pero en este caso sólo nos interesa su primer y único valor
# de ahí que usemos [0][0]
ム cdist([(3, 4)], [(4, 5)], 'euclidean')[0][0]
1.4142135623730951 # porque 1.4142135623730951² = (3 - 4)² + (4 - 5)²
```

Pero, ¿puede haber algún problema con esta definición? 

> ¿Qué pasará si los valores de `x` e `y` están expresados en escalas muy diferentes? Por ejemplo, ¿qué sucederá si todos nuestros puntos fueran similares a `(1.05, 200)`, `(1.06, 100)`, `(1.08, 500)`, `(1.06, 300)`, etc?
> 
> Para averiguarlo, probá calcular las distancias entre todos ellos...
>
> ```python
> puntos = [(1.05, 200), (1.06, 100), (1.08, 500), (1.06, 300)]
> pd.DataFrame(cdist(puntos, puntos, 'euclidean'))
> ```
> ... y estudiá los resultados. 



