###### Bubble Sort
- Altera os elementos localmente, não precisa criar um novo array
- Compara os dois primeiros valores e faz swap se o primeiro for maior que o segundo
- Depois de completar uma varredura, o maior valor do array estará no fim dela, **ele sobe como uma bolha**
- Melhor caso: O(n) - sendo n = quantidade de elementos no vetor. Lista já está ordenada, algoritmo só passa em todos para confirmar
- Pior caso: O(n^2)
- Fácil de implementar mas muito mal otimizado
###### Insertion Sort
- Compara os dois primeiros valores e faz swap se o primeiro for maior que o segundo
- Diferença com o bubble sort é que, após o swap, ele compara o elemento que ficou a esquerda com o elemento anterior. Se o anterior for menor, segue com o próximo par, mas se não, faz o swap e compara com o anterior. Não tem mais de uma varredura
- Melhor caso: O(n)
- Pior caso O(n^2)
###### Merge Sort
- O(n log n)
- Consiste em dividir uma coleção de elementos pela metade recursivamente, até que todos estejam em pares, e fazer uma comparação entre os elementos adjacentes para realizar a combinação, até que todos estejam juntos e ordenados
###### Quick Sort
- O(n^2) pior caso
- O(n log n) melhor e caso medio
- Pivot deve ser, de preferência, um número que divida a array na metade para que tenha a melhor performance
###### Selection Sort


![[Pasted image 20241012154257.png]]
![[Pasted image 20241012154727.png]]
Para cálculo do fibonacci, se usar o método recursivo fica O(2^n), outros métodos fican O(n)