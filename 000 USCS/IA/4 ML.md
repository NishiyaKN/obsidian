### 📜 Visão Geral
**Aprendizagem de Máquina** (Machine Learning - ML) é um subcampo da Inteligência Artificial focado na criação de algoritmos "treináveis", que aprendem padrões e tomam decisões a partir de dados, em vez de serem explicitamente programados para cada tarefa. Este resumo aborda os três principais paradigmas de aprendizado, introduz algoritmos de classificação e explica as métricas essenciais para avaliar o desempenho de um modelo.

---

### 🧠 Paradigmas de Aprendizagem de Máquina
O tipo de problema e os dados disponíveis definem qual paradigma de aprendizado é o mais adequado.

| Paradigma 💡           | Tipo de Dado Usado                                           | Objetivo Principal                                                                    | Problemas Típicos                                                                                                                     |
| :--------------------- | :----------------------------------------------------------- | :------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------------------------------ |
| **Supervisionado**     | Dados **rotulados** (com a "resposta correta" já conhecida). | Fazer previsões sobre novos dados.                                                    | **Classificação** (prever uma categoria, ex: "spam" ou "não spam") e **Regressão** (prever um valor numérico, ex: preço de uma casa). |
| **Não-Supervisionado** | Dados **não-rotulados**.                                     | Descobrir a estrutura e padrões ocultos nos próprios dados.                           | **Clusterização / Agrupamento** (encontrar grupos naturais de clientes com base em seu comportamento de compra).                      |
| **Por Reforço**        | **Feedback** do ambiente (recompensas e punições).           | Aprender a melhor sequência de ações para maximizar uma recompensa ao longo do tempo. | Treinar um agente para jogar um jogo ou um robô para aprender a andar.                                                                |

---

### 🤖 Algoritmos de Classificação: Exemplos
Classificação é uma das tarefas mais comuns em ML. Dentre os diversos algoritmos, a apresentação destaca:

* **Naive Bayes**: Um classificador probabilístico que utiliza o Teorema de Bayes. Ele é "ingênuo" (*naive*) porque assume que todas as características (features) dos dados são independentes umas das outras. Apesar dessa simplicidade, é muito rápido e funciona bem como um modelo inicial (*baseline*).
* **SVM (Support Vector Machine)**: Um poderoso algoritmo que encontra um "hiperplano" (uma linha ou plano) que melhor separa os dados de diferentes classes. O SVM busca maximizar a margem (distância) entre as classes, o que o torna robusto e eficaz, especialmente para dados complexos.

---

### ✅ Avaliando Modelos de Classificação
Para medir o quão bem um modelo de classificação está funcionando, não basta olhar apenas para a quantidade de acertos. Usamos a **Matriz de Confusão**, que detalha os acertos e erros, para calcular métricas mais informativas.

| Métrica 📊                 | Pergunta que Responde                                                                   | Fórmula                                         |
| :------------------------- | :-------------------------------------------------------------------------------------- | :---------------------------------------------- |
| **Acurácia**               | Qual a porcentagem de previsões corretas no geral?                                      | `(VP + VN) / Total`                             |
| **Precisão**               | De todas as vezes que o modelo previu "Positivo", quantas estavam certas?               | `VP / (VP + FP)`                                |
| **Recall (Sensibilidade)** | De todos os casos que eram realmente "Positivos", quantos o modelo conseguiu encontrar? | `VP / (VP + FN)`                                |
| **F1-Score**               | Qual o equilíbrio entre Precisão e Recall? (Média harmônica)                            | `2 * (Precisão * Recall) / (Precisão + Recall)` |

* **VP**: Verdadeiro Positivo; **VN**: Verdadeiro Negativo; **FP**: Falso Positivo; **FN**: Falso Negativo.

A **acurácia** pode ser enganosa em cenários com dados desbalanceados. Por exemplo, um modelo que prevê "não é fraude" 99% das vezes terá 99% de acurácia, mas será inútil. Por isso, **Precisão, Recall** e, especialmente, o **F1-Score** são métricas mais robustas para avaliar o desempenho real de um classificador.

### 🏁 Conclusão
Machine Learning oferece um conjunto poderoso de ferramentas para criar sistemas que aprendem e se adaptam. A escolha do paradigma (Supervisionado, Não-Supervisionado ou por Reforço) é o primeiro passo e depende da natureza do problema e dos dados. Para tarefas de classificação, a avaliação correta é crucial, e o uso de métricas como Precisão, Recall e F1-Score, derivadas da Matriz de Confusão, é fundamental para entender o verdadeiro desempenho e o valor de um modelo.

### 🗑️ Tópicos não aprofundados
* Detalhes sobre o algoritmo OneR.
* Cálculos matemáticos passo a passo para o Naive Bayes.
* A explicação do "kernel trick" em SVMs para dados não-lineares.
* Os diversos exercícios práticos e exemplos de código em Python.
* Referências e links para vídeos externos.
