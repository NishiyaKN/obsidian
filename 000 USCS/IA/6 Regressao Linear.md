### 📝 Visão Geral
Este resumo aborda a avaliação de modelos de aprendizagem supervisionada e foca no conceito de Regressão Linear. O objetivo é entender como separar dados para treinamento e teste, como funciona o algoritmo de regressão linear para prever valores numéricos, e quais métricas são usadas para avaliar a performance desses modelos.

### 🧪 Avaliando Modelos Supervisionados
Para avaliar a qualidade de um modelo supervisionado (classificação ou regressão), é crucial separar os dados em conjuntos de treinamento, validação e teste. Isso evita o viés e previne problemas como **Overfitting** (o modelo decora os dados de treino e não generaliza bem) e **Underfitting** (o modelo é simples demais e não captura a tendência dos dados).

A escolha da estratégia de separação de dados depende de fatores como a quantidade de dados disponíveis e a distribuição das classes.

| Estratégia de Separação                  | Descrição                                                                                                                                                                                             | Quando Usar                                                                                  |
| :--------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------- |
| **Treino/Validação/Teste**               | Uma única divisão dos dados (ex: 70% treino, 20% validação, 10% teste). A validação ajuda a escolher o melhor modelo, e o teste avalia a performance final.                                           | Abordagem comum e simples, boa para grandes datasets.                                        |
| **Validação Cruzada (Cross-Validation)** | Os dados são divididos em *k* partes (folds). O modelo é treinado *k* vezes, usando uma parte diferente para teste a cada vez e o restante para treino. A performance final é a média dos resultados. | Robusto e ideal para datasets menores, pois aproveita melhor os dados.                       |
| **Leave-One-Out**                        | Um caso extremo de validação cruzada onde *k* é igual ao número de amostras. A cada iteração, um único ponto é usado para teste.                                                                      | Apenas quando há pouquíssimos dados disponíveis, pois tem um custo computacional muito alto. |

### 🔍 Modelos de Regressão
Modelos de regressão são algoritmos supervisionados usados para prever um valor numérico contínuo.

#### Regressão Linear
A forma mais simples de regressão, que ajusta uma linha reta aos dados. A equação da reta é:
$$y = ax + b$$
Onde:
- **y**: Valor a ser previsto.
- **x**: Variável independente.
- **a**: Coeficiente angular (inclinação da reta).
- **b**: Coeficiente linear (ponto onde a reta cruza o eixo y).

O objetivo é encontrar os valores de `a` e `b` que minimizem a distância média entre a reta e os pontos de dados reais. As fórmulas para encontrá-los são:
- **Coeficiente Angular (a):** $a=\frac{\sum(x_{i}-\overline{x})(y_{i}-\overline{y})}{\sum(x_{i}-\overline{x})^{2}}$
- **Coeficiente Linear (b):** $b=\overline{y}-a\overline{x}$

### 📊 Métricas de Avaliação para Regressão
Para medir a performance de um modelo de regressão, usamos métricas específicas:

1.  **Erro Quadrático Médio (RMSE - Root Mean Square Error)**
    - Mede a diferença média entre os valores previstos pelo modelo e os valores reais. Quanto menor o RMSE, melhor o modelo.
    - Fórmula: $RMSE=\sqrt{\frac{1}{n}\sum_{i=1}^{n}(y_{i}-\hat{y}_{i})^{2}}$

2.  **Coeficiente de Determinação ($R^{2}$)**
    - Indica a proporção da variância da variável dependente que é explicada pelo modelo. Varia de $-\infty$ a 1.
    - **$R^{2} = 1$**: Ajuste perfeito. O modelo explica 100% da variabilidade dos dados.
    - **$R^{2} = 0$**: O modelo não explica nada. É tão útil quanto usar a média dos dados como previsão.
    - **$R^{2} < 0$**: O modelo é pior do que simplesmente prever a média.
    - Fórmula: $R^{2}=1-\frac{\sum(y_{i}-\hat{y}_{i})^{2}}{\sum(y_{i}-\overline{y})^{2}}$

### ➰ Regressão Polinomial
Quando os dados não seguem uma tendência linear, a Regressão Linear simples não é eficaz. Nesses casos, a **Regressão Polinomial** pode ser usada para ajustar uma curva aos dados. A equação geral é:
$$y=a_{0}+a_{1}x+a_{2}x^{2}+a_{3}x^{3}+\cdot\cdot\cdot$$
Bibliotecas como o Scikit-Learn no Python facilitam a implementação de modelos polinomiais.

```python
# ​Exemplo conceitual de uso com Scikit-Learn
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression

# Transforma os dados para incluir termos polinomiais
poly = PolynomialFeatures(degree=7)
# ... código para aplicar a transformação e treinar o modelo ...

```
### 💡 Conclusão
A avaliação correta de um modelo de machine learning, através de técnicas como validação cruzada, é fundamental para garantir sua capacidade de generalização. A Regressão Linear é uma ferramenta poderosa para prever valores numéricos a partir de dados com tendência linear, enquanto a Regressão Polinomial oferece flexibilidade para modelar relações mais complexas. A performance desses modelos é quantificada por métricas como RMSE e $R^{2}$, que guiam o processo de ajuste e seleção do melhor modelo.

### 📋 Tópicos não aprofundados
- **Cálculo Manual Detalhado:** O passo a passo numérico para calcular os coeficientes `a` e `b` em um exemplo específico foi omitido para manter a concisão.
- **Resolução de Exercícios:** As respostas para os exercícios propostos no material não foram incluídas.
- **Implementação em Python:** Os trechos de código para plotar gráficos e realizar a regressão com `scikit-learn` foram mencionados conceitualmente, mas não detalhados.
- **Derivação Matemática das Fórmulas:** A derivação completa das fórmulas dos coeficientes a partir da função de perda não foi abordada.