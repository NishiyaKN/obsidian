# 🤖 Resumo: Aprendizagem Não Supervisionada - Agrupamento (Clustering)

### 📝 Visão Geral
Este resumo explora a Aprendizagem Não Supervisionada, uma área do Machine Learning focada em encontrar padrões e estruturas em dados não rotulados. Diferente da aprendizagem supervisionada, seu objetivo não é prever um rótulo, but sim organizar os dados. O foco principal é o algoritmo de agrupamento (clustering) **K-Means**, uma técnica fundamental para segmentar dados em grupos de similaridade.

### ⚙️ Aprendizagem Não Supervisionada
É utilizada quando temos um grande volume de dados, mas sem rótulos ou categorias pré-definidas. A principal motivação é descobrir estruturas ocultas. É a base para muitas aplicações, como:
- **Sistemas de Recomendação:** (Netflix, Spotify, Amazon) Agrupar usuários com gostos semelhantes para recomendar novos itens.
- **Segmentação de Clientes:** Identificar diferentes perfis de clientes com base em seu comportamento de compra.
- **Análise de Padrões:** Encontrar tendências e anomalias em dados complexos.

### 🔍 Algoritmo K-Means
O K-Means é um dos algoritmos de agrupamento mais populares. Seu objetivo é particionar um conjunto de dados em **k** clusters (grupos) distintos, onde cada ponto de dado pertence ao cluster com o centróide (o "centro" do cluster) mais próximo.

O algoritmo funciona de forma iterativa em 5 passos:
1.  **Escolher o número de clusters (k):** Você define previamente quantos grupos deseja encontrar nos dados.
2.  **Inicializar os centróides:** `k` pontos são escolhidos aleatoriamente no espaço de dados para serem os centróides iniciais.
3.  **Atribuir pontos aos clusters:** Cada ponto do dataset é atribuído ao cluster cujo centróide está mais próximo (geralmente usando a distância euclidiana).
4.  **Atualizar os centróides:** A posição de cada centróide é recalculada para ser a média de todos os pontos atribuídos a ele no passo anterior.
5.  **Repetir até a convergência:** Os passos 3 e 4 são repetidos até que os centróides não mudem mais de posição significativamente, indicando que os clusters estão estáveis.

### 📊 Avaliando o K-Means
A principal limitação do K-Means é a necessidade de definir o valor de `k` antecipadamente, sem uma garantia de que o número escolhido é o ideal. Para lidar com isso, usamos métricas e métodos de avaliação.

| Métrica / Método                      | Descrição                                                                                                                                                                                                                                                                                  |
| :------------------------------------ | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Inércia**                           | Corresponde à soma das distâncias ao quadrado de cada ponto de dados ao centróide de seu respectivo cluster. Um valor de inércia baixo indica que os clusters são densos e bem definidos. <br><br> **Fórmula:** `$I = \sum_{i=1}^{k} \sum_{x_j \in C_i} \|x_j - \mu_i\|^2$`                |
| **Método do Cotovelo (Elbow Method)** | É uma técnica para encontrar o número ideal de clusters (`k`). Consiste em rodar o K-Means para diferentes valores de `k` e plotar a inércia de cada resultado. O valor ideal de `k` é o "cotovelo" da curva, o ponto onde a diminuição da inércia se torna significativamente mais lenta. |

### 💡 Aplicações Práticas
Além da recomendação e segmentação, o K-Means tem aplicações interessantes, como a **Quantização de Cores em Imagens**. Nessa técnica, o algoritmo é usado para reduzir o número de cores de uma imagem, agrupando cores similares em um único centróide de cor. Isso pode diminuir drasticamente o tamanho do arquivo da imagem com uma perda mínima de qualidade visual.

### 🏁 Conclusão
O K-Means é um algoritmo de agrupamento acessível e poderoso para explorar dados não rotulados e descobrir padrões intrínsecos. Embora sua simplicidade seja uma vantagem, a escolha do número de clusters (`k`) é um desafio crítico que pode ser mitigado com técnicas como o Método do Cotovelo. Sua utilidade em aplicações do mundo real, desde sistemas de recomendação até compressão de imagens, o torna uma ferramenta essencial no campo da Ciência de Dados.

### 📋 Tópicos não aprofundados
- **Simulação Manual:** A execução passo a passo do K-Means com os pontos do exercício não foi detalhada.
- **Análise de Dados de Exercícios:** Os valores de inércia da tabela e a análise do dataset de clientes para o sistema de recomendação foram omitidos.
- **Detalhes de Implementação:** As questões específicas sobre a implementação da função K-Means na biblioteca Scikit-Learn não foram abordadas.