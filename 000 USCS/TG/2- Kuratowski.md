# 📝 Teorema de Kuratowski e Fórmula de Euler

## 👁️ Visão Geral
Este material aborda as condições matemáticas e estruturais que definem a planaridade na Teoria dos Grafos. O conteúdo foca em dois pilares: o Teorema de Kuratowski, que estabelece a regra definitiva para identificar quando um grafo não pode ser desenhado num plano sem cruzamentos, e a Fórmula de Euler, que modela a relação constante entre os componentes de um grafo planar.

## 🔍 Teorema de Kuratowski
Define a condição exata de não-planaridade de um grafo baseando-se em suas subestruturas.

* **Regra Principal:** Um grafo é **não-planar** se, e somente se, contém um subgrafo que seja homeomorfo a $K_5$ (grafo completo de 5 vértices) ou a $K_{3,3}$ (grafo bipartido completo $3 \times 3$).
* **Homeomorfismo de Grafos:** Dois grafos são considerados homeomorfos se puderem ser obtidos a partir de um mesmo grafo base através de uma sequência de subdivisões elementares (como adicionar um vértice no meio de uma aresta existente).
* **Exemplo Clássico:** O Grafo de Petersen é classificado como não-planar justamente por conter, em sua estrutura, um subgrafo que é homeomorfo a $K_{3,3}$.

## 📐 Fórmula de Euler
Estabelece uma constante matemática universal para qualquer grafo que seja conexo e planar (desenhado no plano sem que suas arestas se cruzem).

* **A Equação:** $v - a + r = 2$
  * $v$ = número de vértices
  * $a$ = número de arestas
  * $r$ = número de regiões (incluindo a região exterior infinita)
* **Demonstração por Indução:** A fórmula é tradicionalmente provada por indução com base no número de arestas ($a$). 
* **Caso Base:** Quando $a = 0$, o grafo possui apenas 1 vértice ($v = 1$) e 1 região exterior ($r = 1$). Aplicando na fórmula: $1 - 0 + 1 = 2$, provando a regra inicial.

## 📊 Comparativo de Aplicação
| Conceito | Objetivo Principal | Aplicação / Elementos-Chave |
| :--- | :--- | :--- |
| **Teorema de Kuratowski** | Testar e provar a *não-planaridade*. | Busca por subgrafos específicos ($K_5$ ou $K_{3,3}$) e uso de homeomorfismo. |
| **Fórmula de Euler** | Relacionar componentes de um grafo *planar*. | Cálculo envolvendo Vértices, Arestas e Regiões ($v - a + r = 2$). |

## 💡 Conclusão
O estudo conjunto de Kuratowski e Euler fornece o ferramental teórico completo para a análise de planaridade. Enquanto Euler permite validar as propriedades geométricas de um grafo que já sabemos ser planar, Kuratowski atua como o teste definitivo para descartar a planaridade de redes complexas, conceitos vitais para áreas aplicadas como o desenho de placas de circuitos impressos (PCBs).

## ✂️ Tópicos não aprofundados
* **Contexto Histórico e Biografia:** A história de vida de Kazimierz Kuratowski (1896-1980), seus estudos na Escócia interrompidos pela 1ª Guerra Mundial, seu trabalho clandestino durante a ocupação alemã na 2ª Guerra, e sua participação no grupo da "Cafeteria Escocesa" em Lviv.
* **Demonstrações Visuais Detalhadas:** O passo a passo gráfico ilustrando a inserção de vértices (subdivisão elementar) e o processo de remoção de arestas/vértices utilizado para ilustrar a prova por indução de Euler nas figuras da apresentação.
* **Referências Externas:** Links de blogs citados no material original.