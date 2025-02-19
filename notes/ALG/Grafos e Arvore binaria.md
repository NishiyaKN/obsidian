### Grafos
- Dígrafo - grafo com arestas direcionadas
- Grafo não direcionado é chamado simplesmente de grafo
- Grau de um vértice - número arestas incidentes (vizinhos)
- Grau de um grafo - maior grau de um de seus vértices
- Para resolver problemas de travessias usando grafos, primeiro se identificam os estados (nós/vértices) e depois as transições entre eles (arestas), culminando na busca pela solução

### Árvore Binária
- O(log n)
- Não é possível fazer uma busca binária com listas ligadas (não há como encontrar o meio)
- Estrutura para busca binária com alocação dinâmica de memória -> árvore binária
![[Pasted image 20241010145750.png]]
- Nó -> cada elemento individual da árvore 
- Grau -> número de subárvores que o nó possui. Acima, todos são de grau 2 exceto os da base
- Folhas -> nós que estão na base (grau 0)
- Nós internos -> nós que não são a raiz nem são folhas
- Descendentes -> nós abaixo de um determinado nó. Todos são descendentes da raiz 
- Nível: (raiz é nível 0)
![[Pasted image 20241010150620.png]]
 - Altura de um nó -> maior distância entre o nó e a folha mais distante (folha tem altura 0, raiz no exemplo tem altura 3).
 - Altura da árvore -> altura da raiz
 - Profundidade de um nó -> distância entre o nó e a raiz (raiz em si tem profundidade 0)
 - Árvore balanceada -> simétrica:
  ![[Pasted image 20241010150245.png]]
- Endereço da árvore -> endereço da raiz

Em uma árvore binária, abaixo de cada nó existem de 0 a 2 subárvores, ou seja, o grau de cada nó é 0, 1 ou 2.

###### Travessia
Em **ordem**: esquerda, raiz, direita (bolinha embaixo)
Em **pré-ordem**: raiz, esquerda, direita (bolinha na esquerda)
Em **pós-ordem**: esquerda, direita, raiz (bolinha na direita)

- Número máximo de elementos de uma árvore de n níveis é de 2^n -1
	- Árvore de 10 níveis terá 2^10 - 1 = 1024 - 1 = 1023
- Altura de uma árvore é a quantidade de níveis contados após a raiz
	- Pode ser contado também a quantidade de **arestas** da raiz até a folha mais embaixo
- Árvore balanceada é quando a diferença entre as alturas das subárvores seja no máximo 1
- Árvore completa é quando todos os penultimos nodes possuem duas folhas