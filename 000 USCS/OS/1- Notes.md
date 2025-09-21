### 📝 Visão Geral
Este resumo aborda as técnicas de gerenciamento de memória utilizadas por sistemas operacionais, um processo fundamental para permitir a execução simultânea de múltiplos programas[cite: 2]. A evolução dessas técnicas mostra uma transição de métodos estáticos e rígidos para abordagens dinâmicas e flexíveis, como segmentação e paginação, que são a base dos sistemas modernos.

### 🔑 Conceitos Fundamentais de Endereçamento
Para que um processo seja executado, ele primeiro precisa ser alocado na memória principal por um componente do sistema operacional chamado **Loader**[cite: 2, 3]. O gerenciamento desse espaço envolve dois tipos de endereços:

* **Endereço Físico:** A localização real e específica na memória onde um programa ou dado é armazenado[cite: 23, 39]. O processador só entende endereços físicos[cite: 17, 31].
* **Endereço Lógico (ou Relativo):** A posição de uma instrução dentro do próprio programa, independentemente de onde ele esteja na memória física[cite: 39]. O compilador gera esses endereços, geralmente considerando que o programa começa na posição 0[cite: 29, 40]. A posição específica é chamada de **deslocamento (offset)**[cite: 30].

Para proteger a memória, o sistema utiliza registradores de **base** e **limite** para cada processo, que delimitam seu espaço de endereçamento válido[cite: 8]. Uma tentativa de acesso fora dessa faixa causa uma falha de violação de acesso (*access violation*)[cite: 8].

### ➗ Alocação Particionada
Foi a primeira técnica que permitiu a execução de vários processos ao mesmo tempo, dividindo a memória em partições[cite: 4].

1.  **Particionamento Estático Absoluto:**
    * Uma abordagem antiga onde os endereços físicos eram fixados pelo programador no momento da compilação[cite: 5, 13, 21, 22].
    * **Problema:** Exigia que a região de memória específica estivesse sempre livre, o que restringia muito a execução[cite: 15, 25]. Hoje não é mais utilizada[cite: 6, 26].

2.  **Particionamento Estático Relocável:**
    * O compilador gera endereços lógicos (relativos)[cite: 29].
    * Quando o programa é carregado na memória, o **Loader** calcula o endereço físico final somando o endereço base da partição com o deslocamento da instrução (`endereço físico = base + deslocamento`)[cite: 32].

3.  **Particionamento Dinâmico:**
    * As partições são criadas dinamicamente, com o tamanho exato que cada programa necessita[cite: 37].
    * Isso resolve o problema de fragmentação interna[cite: 38].

### 🧩 Problema da Fragmentação
A alocação de memória pode levar ao desperdício de espaço de duas formas:

* **Fragmentação Interna:** Ocorre quando um processo é menor que a partição alocada para ele, gerando um espaço não utilizado *dentro* da partição[cite: 34, 35].
* **Fragmentação Externa:** Ocorre no particionamento dinâmico. Conforme processos são terminados, "buracos" de memória livre aparecem entre processos alocados, dificultando a alocação de novos processos que precisam de memória contígua[cite: 38, 40].

### 📂 Gerenciamento Moderno: Segmentação e Paginação
Para resolver os problemas da alocação particionada, surgiram técnicas mais avançadas.

| Técnica | Divisão do Programa | Fragmentação | Endereçamento |
| :--- | :--- | :--- | :--- |
| **Segmentação** | Em partes lógicas de tamanhos variáveis (código, dados, pilha, heap)[cite: 6, 41]. | Resolve a interna, mas ainda sofre com a **fragmentação externa**[cite: 41]. | `(base do segmento + deslocamento)` para cada segmento[cite: 41]. |
| **Paginação** | Em blocos de tamanho fixo chamados **páginas** (ex: 4KB)[cite: 7, 42]. | Resolve a **fragmentação externa**, mas pode ter **fragmentação interna** na última página[cite: 42]. | `(frame da página + deslocamento)` calculado via hardware[cite: 43, 44]. |

### 🏁 Conclusão
O gerenciamento de memória evoluiu de um sistema rígido de endereçamento físico para um modelo flexível baseado em endereçamento lógico e relocação dinâmica. Técnicas como particionamento introduziram a multiprogramação, mas trouxeram problemas de fragmentação. A segmentação e, principalmente, a paginação se tornaram as soluções padrão em sistemas operacionais modernos, pois resolvem o problema da fragmentação externa e permitem um uso muito mais eficiente e seguro da memória principal.

### 🚫 Tópicos não aprofundados
A lista abaixo contém tópicos presentes no material de origem que não foram incluídos ou foram abordados superficialmente neste resumo:
* As técnicas de `swap` e `memória virtual`, que usam o disco rígido como uma extensão da memória principal[cite: 8].
* Detalhes sobre o funcionamento do **TLB (Translation Lookaside Buffer)**, um hardware que acelera o cálculo de endereços na paginação[cite: 42].
* O **Princípio da Localidade**, que explica por que alocar segmentos próximos pode melhorar o desempenho de cache[cite: 42].
* A estrutura detalhada de um processo na memória (texto, dados, pilha e heap)[cite: 8, 41].

