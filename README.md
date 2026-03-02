# Glossário do projeto QUATi-AI

Nesse arquivos, estão listados e descritos os principais termos, funções, métodos, jargões, utilizados no projeto `quati-ai`.

## Sumário
- [Ativo](#Ativo)
- [Hedge Ratio](#Hedge-Ratio)

### Ativo
São coisas cujo o preço pode variar ao longo do tempo, como qualquer empresa listada na bolsa de valores, ou criptomoedas, ouro, prata, cartinhas do pokémon, casas, etc.

### Pair trading
Pair trading é uma estratégia quantitativa de arbitragem estatística que consiste em negociar simultaneamente dois ativos com forte relação histórica — tipicamente correlação elevada ou cointegração — explorando desvios temporários dessa relação. O investidor monta uma posição long–short, comprando o ativo relativamente subvalorizado e vendendo o relativamente sobrevalorizado, com o objetivo de capturar a reversão à média do spread entre eles, e não a direção absoluta do mercado.

### Long & short
A estratégia Long & Short envolve a compra de um ativo que se espera que aumente de valor (posição longa) e a venda simultânea de outro ativo que se espera que caia de valor (posição curta). O objetivo é lucrar com a diferença entre os preços dos dois ativos durante as operações na Bolsa de Valores.

### Spread
O spread mede o quanto o ativo $𝐴$ está relativamente caro ou barato em relação a $𝐵$. Se os ativos forem cointegrados, o spread tende a ser estacionário e apresentar reversão à média, o que fundamenta a lógica operacional: quando $𝑆_𝑡$ se afasta significativamente da média histórica, abre-se uma posição long–short esperando sua convergência.
Em termos formais, define-se um spread 
$𝑆_𝑡=𝑃_𝐴−\beta*𝑃_𝐵$, onde $\beta$ é o hedge ratio, $P_A$ é o preço real do ativo $A$ e o $P_B$ é o preço real do ativo $B$.

### Hedge Ratio
O hedge ratio é o coeficiente que determina a proporção ideal entre dois ativos em uma estratégia long–short, com o objetivo de neutralizar o risco direcional e isolar apenas o componente relativo (spread). Em termos práticos, ele indica quantas unidades do ativo B devem ser vendidas/compradas para cada unidade do ativo A, de modo que a exposição ao mercado seja minimizada. O Hedge ratio $\beta$ é encontrado via regressão linear (OLS):

$$
P_A = \alpha + \beta*P_B + \epsilon
$$

onde $P_A$ é o preço real do ativo $A$ e o $P_B$ é o preço real do ativo $B$. O hedge ratio é o coeficiente de balanceamento que transforma duas posições direcionais em uma posição estatisticamente neutra.
