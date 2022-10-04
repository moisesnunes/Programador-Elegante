---
title: "Integrais com Python"
description: "Numerical Python, Robert Johansson"
lead: ""
date: 2020-10-06T08:49:31+00:00
lastmod: 2020-10-06T08:49:31+00:00
draft: false
images: []
menu:
  docs:
    parent: "traduções"
weight: 110
toc: true
---

*Robert Johansson*, Numerical Python

___

## Integrais 

Cobrimos aqui diferentes aspectos das integrais, com foco principal na integração numérica.
Por razões históricas, integrais também são conhecidas como quadraturas.
Integração é significativamente mais difícil do que sua operação inversa: diferenciação.
Para realizarmos a integração simbólica, podemos usar o __SymPy__, e para calcular as integrais, podemos usar principalmente o módulo *Integrate* do __SciPy__.

___

### Importando os módulos 

Vamos usar de modo usual as bibliotecas __NumPy__ e __Matplolib__ para numeração básica e a ajuda de gráficos e, além disso, usamos o módulo *Integrate* do __SciPy__ e a biblioteca matemática __mpmath__. 

```python
import numpy as np
import matplotlib.pyplot as plt 
import maplotlib as mpl
from scipy import integrate
import sympy
import mpmath
```
Para um output bem formatado do __SymPy__, vamos configurar seu sistema de impressão.

```python
sympy.init_printing()
```
___

### Métodos de Integração Numérica

Nosso foco aqui será em calcular integrais definidas na forma $I(f)= \int_{a}^{b} f(x) dx$, com os limites de integração dados em _a_ e _b_. O intervalo [_a_,_b_] pode ser finito; semi-infinito (em que ambos _a_ = - $\{\infty}\$ ou b = $\{\infty}\$ ); ou infinito (em que ambos _a_ = - $\{\infty}\$ ou b = $\{\infty}\$ ).
A integral $\ I(f)\$ pode ser interpretada como a área entre a curva do integrando $f(x)$ e o eixo _x_, como ilustrado na figura a baixo.


_Interpretação de uma integral entre a área da curva do integrando e o eixo x. A área é tida como positiva onde $f(x) > 0$ (verde) e negativa onde $ f(x) < 0$ (vermelha)._  

Uma estratégia geral para avaliar numericamente uma integral $I (f)$ é esreve-lá como uma soma discreta que aproxima-se do valor da integral: 

$$\begin{equation*} I (f) = \sum_{i=1}^{n} \ w_i \ f(x_i) + r_n \end{equation*}$$

Temos que $w_i$ são os valores das _n_ avaliações de $f(x)$
nos pontos $x_i \in [a,b]$, e que, $r_n$ é o resíduo devido à aproximação. Assumimos na prática que $r_n$ é pequeno, e pode ser ignorado; mas, é importante ter uma estimativa de $\ r_n \$ para sabermos com precisão o quanto a integral está aproximada. Esta formula de adição para $I (f)$ é conhecida como um ponto-_n_ na _regra da quadratura_; 






