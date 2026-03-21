# 📝 Resumo: Teoremas de Euler e Hamilton, Representações e Árvores

## 👁️ Visão Geral
Este material aborda os conceitos avançados de Teoria dos Grafos focados em percursos (ciclos e caminhos de Euler e Hamilton), métodos computacionais de armazenamento na memória (matrizes e listas) e a estrutura fundamental das Árvores. O foco principal é fornecer base teórica para a implementação eficiente de estruturas de dados e algoritmos de busca e otimização em Ciência da Computação.

## 🔍 Teoremas de Percurso

### Grafos Eulerianos (Foco nas Arestas)
O problema original baseia-se nas Sete Pontes de Königsberg. O objetivo é percorrer todas as arestas sem repetição.
* **Ciclo Euleriano:** Um ciclo que passa por **todas as arestas** exatamente uma vez e retorna ao ponto de partida.
* **Teorema (Grafo Euleriano):** Um grafo é euleriano se, e somente se, é conexo e **todos** os seus vértices possuem grau par.
* **Caminho Euleriano (Grafo Atravessável):** Percorre todas as arestas uma única vez, mas começa e termina em vértices diferentes.
* **Teorema (Caminho Euleriano):** Ocorre se, e somente se, o grafo for conexo e possuir **exatamente dois** vértices de grau ímpar (o caminho obrigatoriamente começa em um e termina no outro).

### Grafos Hamiltonianos (Foco nos Vértices)
* **Ciclo Hamiltoniano:** Um ciclo que visita **todos os vértices** exatamente uma vez.
* **Teorema de Hamilton (Condição Suficiente):** Se um grafo tem ordem $p \ge 3$ e todo vértice $v$ possui $grau(v) \ge p/2$, então ele é hamiltoniano. 
* *Nota:* Esta condição não é obrigatória; grafos em formato de anel simples (ciclo) não atendem a essa regra de grau, mas ainda assim são hamiltonianos.

## 📊 Representação Computacional de Grafos
A escolha de como armazenar o grafo afeta diretamente o consumo de memória e a velocidade dos algoritmos.

| Estrutura                | Como Funciona                                                                               | Prós                                                                                      | Contras                                                                                |
| :----------------------- | :------------------------------------------------------------------------------------------ | :---------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------- |
| **Matriz de Adjacência** | Matriz $N \times N$ (vértices). Valor **1** se há aresta entre $i$ e $j$, senão **0**.      | Acesso direto e rápido para verificar se existe uma aresta específica.                    | Desperdício de memória em grafos esparsos (muitos zeros).                              |
| **Matriz de Incidência** | Matriz Vértices $\times$ Arestas. Usa **+1** (chega), **-1** (parte) e **0** (sem conexão). | Boa para representar grafos orientados e modelagem matemática.                            | Alto custo computacional de armazenamento.                                             |
| **Lista de Adjacência**  | Cada vértice possui uma lista encadeada (ou vetor) de seus vizinhos.                        | Altamente eficiente em memória para grafos esparsos. Rápido para achar todos os vizinhos. | Lento para verificar se uma aresta específica $(i, j)$ existe (requer busca na lista). |

*Observação sobre Simetria:* Em grafos **não orientados**, a Matriz de Adjacência é simétrica. Para economizar espaço, computacionalmente pode-se armazenar apenas a diagonal principal e sua porção triangular inferior.

## 🌲 Árvores
Uma árvore é um grafo acíclico e conexo. Se for acíclico mas desconexo, é chamado de **Floresta**.
* **Raiz:** Vértice inicial designado. O caminho da raiz para qualquer outro vértice é único.
* **Profundidade:** Comprimento do caminho da raiz até um vértice (profundidade da raiz é 0).
* **Altura:** Maior profundidade encontrada na árvore.
* **Folha:** Vértice que não possui filhos (grau 1).
* **Nós Internos:** Vértices que possuem filhos.
* **Árvore Binária:** Cada nó interno tem no máximo dois filhos (esquerda e direita). Se todos os nós internos têm exatos dois filhos e as folhas estão na mesma profundidade, é uma **Árvore Binária Completa**.

## 💻 Exemplo: Representação de Árvore com Vetores
Uma árvore binária pode ser facilmente representada usando um array de registros (ou estruturas) contendo ponteiros.
```c
// Exemplo conceitual da estrutura
struct NoArvore {
    int valor;
    int indice_filho_esquerda;
    int indice_filho_direita;
};
```

## 💡 Conclusão
A compreensão entre as condições de Euler (arestas) e Hamilton (vértices) evita confusões teóricas clássicas. Além disso, a decisão de engenharia sobre qual estrutura usar (Matrizes vs. Listas) deve ser baseada na densidade do grafo: grafos densos favorecem matrizes para acesso em tempo $O(1)$, enquanto grafos esparsos e aplicações em árvores exigem listas de adjacência ou ponteiros diretos para otimizar o uso da RAM.

## ✂️ Tópicos não aprofundados
* **Problemas lúdicos e charadas:** O "Problema do desenho da casa" (traçar sem levantar o lápis) e o mistério policial de "Count Van Diamond / Sherlock Gomes" usados didaticamente para explicar a utilidade de rastrear graus pares/ímpares de vértices.
* **Aplicações Práticas (Índice):** O material lista que a teoria serve base para algoritmos de Caminho Mínimo (Dijkstra, Bellman-Ford) e Árvores Geradoras Mínimas (Kruskal, Prim), mas não detalha o funcionamento matemático destes algoritmos no documento fornecido.
* **Passo a passo das resoluções:** As respostas exatas dos exercícios propostos nos slides finais sobre conversão visual do grafo para matriz.