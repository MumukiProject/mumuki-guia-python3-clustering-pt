Quando buscamos fazer previsões, geralmente trabalhamos com algoritmos de **aprendizado supervisionado**: métodos que, a partir de dados rotulados, permitem reconstruir as relações entre variáveis e rótulos. Dentro desse conjunto de algoritmos, podemos identificar dois subtipos principais: **regressão** e **classificação**.

|              	  |   	Regressão          | 	 Classificação             |
|-----------------|------------------------|-----------------------------|
|➡️ Variável de saída|Contínuo             	|Discreto                 	 |
|🔧 Ajuste        	|Tentativas de encontrar a linha de melhor ajuste, que prevê a saída com mais precisão|Tentativas de encontrar o limite de decisão, que pode dividir o conjunto de dados em diferentes classes |
|🔮 Previsão    	|Uma quantidade é prevista para as observações | As observações são rotuladas com uma de duas ou mais classes|

Exemplos de regressão são os dois casos em que trabalhamos anteriormente: prever a progressão de uma determinada doença com base nos dados biomédicos dos pacientes :thermometer_face: ou o número de mensagens de texto que serão enviadas em um determinado ano :vibration_mode:. Mesmo problemas como estimar a temperatura do nosso planeta em um futuro próximo podem ser vistos como um problema de regressão 🌡.

Por outro lado, exemplos de classificação são saber se um e-mail é _spam_ ou não :envelope:, ou identificar a partir de uma imagem de uma planta, qual é a sua espécie :sunflower:.  

Mas em certas ocasiões devemos trabalhar com dados para os quais não temos uma quantidade ou rótulo. Nesses casos, teremos que treinar nossos algoritmos de aprendizado automático **sem supervisão**, o que nos permitirá obter informações, sem saber previamente qual será a saída.


> 🤔 Aprender sem supervisão? Como isso é possível? Você consegue pensar em algum aspecto que um algoritmo de aprendizado automático poderia identificar sem supervisão?
