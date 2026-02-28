
### 📜 Visão Geral
O gerenciamento de memória é uma função central do sistema operacional, responsável por organizar o uso da memória principal para maximizar a quantidade de processos em execução e, ao mesmo tempo, proteger seus espaços de endereçamento. Este resumo aborda as técnicas iniciais de **alocação contígua**, incluindo o particionamento estático e dinâmico, e discute os problemas de fragmentação e os tipos de endereçamento associados.

### 🛡️ Proteção de Memória
Em um ambiente de multiprogramação, é vital que o sistema operacional impeça um processo de acessar a memória de outro. Isso é feito através de hardware, utilizando dois registradores especiais:
* **Registrador Base**: Armazena o endereço físico inicial da área de memória de um processo.
* **Registrador Limite**: Armazena o tamanho (ou o endereço final) dessa área.

Toda vez que um programa tenta acessar um endereço de memória, o hardware verifica se ele está dentro do intervalo `[base, base + limite]`. Qualquer tentativa de acesso fora desses limites gera uma interrupção de hardware (falha de segmentação), e o sistema operacional encerra o processo infrator.

### 📦 Alocação Particionada
Para permitir que múltiplos processos residam na memória simultaneamente (multitarefa), a técnica de particionamento divide a memória principal em várias seções. Existem duas abordagens principais para isso.

📊 **Comparativo: Particionamento Estático vs. Dinâmico**

| Característica | Particionamento Estático | Particionamento Dinâmico |
| :--- | :--- | :--- |
| **Como Funciona** | A memória é dividida em partições de **tamanho fixo** na inicialização do sistema. | As partições são criadas **sob demanda**, com o tamanho exato necessário para cada processo. |
| **Principal Vantagem** | Simplicidade de implementação e gerenciamento. | Uso eficiente do espaço, pois não há desperdício *dentro* da partição. |
| **Principal Desvantagem** | **Fragmentação Interna**: Ocorre quando um processo é menor que a partição que ocupa, desperdiçando o espaço restante dentro dela. | **Fragmentação Externa**: Com o tempo, a memória se enche de pequenos "buracos" não contíguos, que podem ser insuficientes para alocar novos processos, mesmo que a soma do espaço livre seja grande. |

### 📍 Endereçamento Absoluto vs. Relocável
A forma como um programa se refere a endereços de memória impacta sua flexibilidade de alocação.
* **Endereçamento Absoluto**: O código do programa é compilado com **endereços físicos fixos**. Isso o torna extremamente rígido, pois ele só pode ser carregado e executado naquele local específico da memória.
* **Endereçamento Relocável**: O programa é compilado com endereços **relativos ao seu próprio início (deslocamento)**. Quando o sistema operacional (Loader) carrega o programa em uma partição, ele calcula o endereço físico final somando o endereço base da partição ao deslocamento relativo da instrução. Isso permite que o mesmo programa seja carregado em qualquer partição livre que seja grande o suficiente.

### 🏁 Conclusão
As técnicas de alocação contígua são a base do gerenciamento de memória, mas sofrem com o problema crônico da **fragmentação**. O particionamento estático, embora simples, leva ao desperdício por fragmentação interna. Já o particionamento dinâmico, embora mais eficiente no uso do espaço, sofre com a fragmentação externa, que pode exigir operações custosas de compactação de memória. Essas limitações motivaram o desenvolvimento de técnicas mais avançadas e não contíguas, como a segmentação e a paginação.

### 🗑️ Tópicos não aprofundados
* Diagramas de layouts de memória e exemplos de alocação de processos.
* Soluções para fragmentação externa, como algoritmos de alocação (First-fit, Best-fit, etc.) e compactação.
* Técnicas de gerenciamento de memória mais avançadas, como Segmentação, Paginação e Memória Virtual.
* Detalhes sobre o funcionamento do `Loader` do sistema operacional.
* Referências bibliográficas e links para vídeos externos.
