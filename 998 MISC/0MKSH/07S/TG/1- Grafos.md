# 📝 Teoria dos Grafos: Fundamentos e Definições

## 👁️ Visão Geral
Este material introduz os conceitos básicos e as propriedades fundamentais da Teoria dos Grafos. Ele aborda desde a definição formal de vértices e arestas até classificações de grafos, conectividade, propriedades matemáticas (como o Lema do Aperto de Mão e a Fórmula de Euler) e aplicações práticas na modelagem de redes, circuitos e relações.

## 🔍 Definições Básicas
* **Grafo:** É uma tripla ordenada $(V, E, g)$, onde $V$ é o conjunto de vértices (nós), $E$ é o conjunto de arestas (arcos) e $g$ é uma função que associa cada aresta aos seus vértices extremos.
* **Adjacência:** Dois vértices são adjacentes se compartilham uma mesma aresta.
* **Laço:** Uma aresta cujos extremos estão no mesmo vértice (conecta o vértice a si mesmo).
* **Arestas Paralelas:** Múltiplas arestas que conectam exatamente o mesmo par de vértices.
* **Grau de um Vértice:** É o número de extremos de arestas conectados àquele vértice (um laço adiciona 2 ao grau).

## 📊 Classificação e Tipos de Grafos
| Tipo de Grafo              | Característica Principal                                                                                                          |
| :------------------------- | :-------------------------------------------------------------------------------------------------------------------------------- |
| **Nulo / Vazio / Trivial** | Vértices vazios / Arestas vazias / Apenas 1 vértice e 0 arestas.                                                                  |
| **Regular**                | Todos os vértices possuem exatamente o mesmo grau.                                                                                |
| **Simples**                | Não possui laços e nem arestas paralelas.                                                                                         |
| **Completo ($K_n$)**       | Grafo simples onde todos os pares de vértices distintos são adjacentes.                                                           |
| **Bipartido**              | Vértices divididos em dois conjuntos separados; arestas só conectam vértices de conjuntos diferentes (não possui ciclos ímpares). |

## 🛣️ Caminhos, Conectividade e Fecho
* **Caminho:** Sequência de vértices e arestas interligadas. O *comprimento* é o número de arestas percorridas.
* **Ciclo:** Um caminho fechado (termina no vértice de origem) sem repetir arestas ou vértices (exceto o inicial/final).
* **Grafo Conexo:** Existe pelo menos um caminho entre quaisquer dois vértices do grafo.
* **Fecho Transitivo Direto (FTD):** Conjunto de vértices que podem ser alcançados partindo de um vértice específico.
* **Fecho Transitivo Inverso (FTI):** Conjunto de vértices a partir dos quais é possível alcançar um vértice específico.

## 📐 Propriedades e Teoremas
* **Lema do Aperto de Mão (Handshake Lemma):** Em qualquer grafo, a soma dos graus de todos os vértices é igual ao dobro do número de arestas. 
  $$\sum_{v \in V} \text{deg}(v) = 2|E|$$
* **Fórmula de Euler:** Para um grafo que seja simples, planar e conexo, a relação entre vértices ($v$), arestas ($a$) e regiões/faces ($r$) é constante:
  $$v - a + r = 2$$

## 🗺️ Planaridade e Isomorfismo
* **Grafo Planar:** É aquele que pode ser desenhado em um plano de forma que suas arestas não se cruzem (tocam-se apenas nos vértices).
* **Isomorfismo:** Dois grafos são isomorfos se são estruturalmente idênticos, mesmo que desenhados de forma diferente. Exige uma função bijetora entre os vértices e arestas que preserve perfeitamente as adjacências.
* *Dica:* Para provar que dois grafos **não** são isomorfos, basta achar uma divergência simples (ex: número diferente de vértices, arestas, ou vértices com graus diferentes).

## ✂️ Tópicos não aprofundados
* **Revisão de Funções Matemáticas:** Detalhes topológicos e definições extensas sobre funções injetoras, sobrejetoras, bijetoras e homeomorfismo (ex: analogia da caneca e do biscoito).
* **Aplicações e Exemplos de Modelagem:** A seção detalhando a Lei das Correntes de Kirchhoff e a topologia física de *backbones* da Internet no Brasil.
* **Resolução de Exercícios:** As respostas detalhadas e os desenhos passo a passo dos grafos propostos nos exercícios finais ($K_5$, $K_{3,3}$ e validação de planaridade).