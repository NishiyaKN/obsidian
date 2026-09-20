## 👁️ Visão Geral
Este material introduz os conceitos básicos de Análise e Projeto de Algoritmos. O foco principal é explicar a necessidade de se avaliar a eficiência dos algoritmos de maneira teórica, demonstrando que testar um código apenas executando-o em uma máquina (método experimental) é insuficiente e restrito. A abordagem ideal exige um método analítico e matemático.

## 🔍 Definições Fundamentais
* **Algoritmo:** Procedimento passo a passo para a execução de uma tarefa em uma quantidade finita de tempo.
* **Estrutura de Dados:** Uma forma organizada de acessar e armazenar os dados utilizados pelo algoritmo.

## 📊 Critérios de Avaliação de um Algoritmo
Ao analisar um algoritmo, o **desempenho (tempo de execução)** é geralmente o fator mais crítico (especialmente em problemas complexos), mas outros aspectos também podem ser avaliados:
* Espaço ocupado em memória.
* Corretismo (se faz exatamente o que é esperado).
* Comprimento total do código.
* Legibilidade e Robustez.

## ⚖️ Comparação de Métodos de Avaliação
| Característica | Método Experimental (Medição Direta) | Método Analítico (Matemático) |
| :--- | :--- | :--- |
| **Abordagem** | Executa o algoritmo na máquina e cronometra o tempo. | Avalia o comportamento do algoritmo logicamente, sem precisar rodá-lo. |
| **Cobertura de Entradas** | Limitada. Avalia apenas as instâncias testadas. | Completa. Considera todas as entradas e tamanhos de problema possíveis. |
| **Dependência de Hardware** | Alta. O resultado muda dependendo da CPU, memória, Sistema Operacional e compilador. | Nenhuma. É totalmente independente do ambiente de software e hardware. |
| **Necessidade de Código** | Exige que o algoritmo seja totalmente implementado. | Pode ser obtido diretamente da lógica ou pseudocódigo. |

## 💡 Conclusão
O fato de um programa rodar rápido no computador do desenvolvedor não garante que ele seja eficiente. O método experimental possui muitas variáveis ocultas (hardware, SO, compilador) que mascaram a real eficiência do algoritmo. Para a Ciência da Computação, o método analítico é indispensável, pois permite prever como o tempo de execução crescerá à medida que o tamanho do problema aumenta (ex: $n^2$, $n \log n$, $2^n$), antes mesmo de escrevermos a primeira linha de código.

## ✂️ Tópicos não aprofundados
* **Referências Bibliográficas:** A lista de livros recomendados para a disciplina (ex: obras de Goodrich, Levitin, Skiena e Bhasin).
* **Gráfico de Crescimento Assintótico:** O material apresenta um gráfico visual das curvas de tempo ($2^n, n^3, n^2, n \log_2 n, n, \log_2 n$) que não foi detalhado matematicamente nesta introdução.
* **Ilustrações e fluxogramas genéricos:** Imagens lúdicas e fluxogramas básicos de introdução usados nos slides iniciais.
