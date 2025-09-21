#  resumo sobre métodos preditivos e estatística

### 📝 Visão Geral
Este resumo aborda os conceitos fundamentais de estatística aplicados a estudos preditivos. O objetivo de um estudo preditivo é analisar dados do passado e do presente para construir modelos, como os de regressão, que possam prever resultados futuros. A base para isso está na diferenciação entre estatística descritiva e inferencial, com destaque para as abordagens clássica (frequentista) e bayesiana.

### 📊 Estatística: Descritiva vs. Inferencial
A estatística é uma ferramenta essencial para a análise de dados, dividida principalmente em duas áreas:

* **Estatística Descritiva:** Focada em analisar e descrever um conjunto de dados finito, geralmente uma população inteira que está sendo estudada no momento.
* **Estatística Inferencial:** Trabalha com uma amostra de dados para fazer inferências e tirar conclusões sobre uma população maior. Na prática, não existe uma amostra "perfeita".

A estatística inferencial se divide em duas grandes abordagens:

| Abordagem                   | Base                                                                | Tamanho da Amostra (n) | Aplicação Comum      |
| :-------------------------- | :------------------------------------------------------------------ | :--------------------- | :------------------- |
| **Bayesiana**               | Probabilidade condicional; infere a partir de dados pré-existentes. | Pequeno (`n` pequeno). | Estimativas.         |
| **Frequentista (Clássica)** | Análise da frequência de ocorrências.                               | Grande (`n` grande).   | Testes de hipóteses. |

### 📈 O Processo Preditivo
A construção de um modelo preditivo geralmente segue um fluxo que combina as diferentes áreas da estatística:

1.  **Estudo do Passado:** Utiliza-se uma massa gigante de dados históricos para realizar uma análise descritiva e construir um modelo de regressão. A análise inferencial clássica pode ser usada para identificar diferenças significativas nos dados.
2. **Modelos de Regressão:** O modelo de regressão pode ser de diferentes tipos, como univariado, multivariado ou múltiplo
3.  Validação e Predição:** O modelo criado é aplicado aos dados do presente para verificar sua eficácia. Se o modelo funcionar bem, ele é considerado válido para fazer predições sobre o futuro.

### ⏳ Análise de Dados Temporais
Para dados que evoluem com o tempo, a visualização é fundamental.
* Ao estudar dados ao longo do tempo, o uso de **gráficos de linhas** é obrigatório para observar a evolução dos dados.

### 🏁 Conclusão
Métodos preditivos são uma aplicação prática da estatística para prever o futuro. Eles se baseiam na análise descritiva de grandes volumes de dados passados para construir modelos de regressão. A estatística inferencial, seja pela abordagem frequentista ou bayesiana, ajuda a validar e refinar esses modelos. Uma vez validado com dados atuais, o modelo torna-se uma ferramenta poderosa para a tomada de decisões baseada em previsões.

### 🚫 Tópicos não aprofundados
A lista abaixo contém tópicos presentes no material de origem que não foram incluídos ou foram abordados superficialmente neste resumo:
* Conceitos de probabilidade como árvores, processo estocástico e Cadeia de Markov.
* Detalhes técnicos sobre os modelos de regressão (univariado, multivariado e múltiplo).
* Definição e aplicação de "boxplot" e "hipótese de variabilidade".