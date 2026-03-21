## 👁️ Visão Geral
Este material aprofunda o estudo da análise de algoritmos focando na Função de Complexidade, que modela matematicamente a eficiência de um código em relação ao tamanho da sua entrada de dados ($n$). O conteúdo demonstra como comparar o crescimento de diferentes algoritmos (como $O(n^2)$ vs $O(n^3)$), explora o impacto da melhoria de hardware frente à complexidade matemática e define formalmente as análises de Melhor Caso, Pior Caso e Caso Médio.

## 🔍 O que é a Função de Complexidade?
A função de complexidade $f(n)$ é uma abstração matemática para medir o custo de um algoritmo.
* **Complexidade de Tempo:** Não mede o tempo cronológico (segundos, milissegundos), mas sim o **número de vezes que uma operação relevante é executada** em função do tamanho da entrada ($n$).
* **Complexidade de Espaço:** Mede a quantidade de memória adicional exigida pelo algoritmo para processar uma entrada de tamanho $n$.
* **Dependência da Entrada:** O custo de execução cresce proporcionalmente ao tamanho e, às vezes, à disposição dos dados de entrada (ex: um vetor já ordenado vs. um vetor desordenado).

## 💻 Exemplo: Maior Elemento de um Array
Para encontrar o maior valor num vetor de $n$ elementos, o algoritmo precisa varrer o vetor comparando os valores.
```java
// O algoritmo assume o primeiro elemento como o maior
int Max = V[0];
// E compara com o restante do vetor
for (int i = 1; i < V.length; i++) {
    if (V[i] > Max) Max = V[i]; 
}
```
* **Análise:** Independentemente do conteúdo do vetor, o laço começará no índice 1 e irá até $n-1$. Logo, a função de complexidade é **$f(n) = n - 1$** (crescimento linear).

## 📊 Cenários de Análise de Algoritmos
A eficiência de um algoritmo pode variar drasticamente dependendo da configuração inicial dos dados fornecidos. Para isso, avaliam-se três cenários:

| Cenário | Definição | Exemplo: Pesquisa Sequencial em Arquivo de tamanho $n$ |
| :--- | :--- | :--- |
| **Melhor Caso** | Ocorre o menor número de operações possíveis para uma entrada $n$. | $f(n) = 1$ (O registro procurado é exatamente o 1º da lista). |
| **Pior Caso** | Ocorre o maior número de operações possíveis para uma entrada $n$. É a garantia máxima de custo. | $f(n) = n$ (O registro é o último da lista ou sequer existe). |
| **Caso Médio** | Média dos tempos de execução baseada em uma distribuição de probabilidade das entradas. | $f(n) = (n+1)/2$ (Assumindo que todas as chaves têm igual probabilidade $1/n$ de serem buscadas). |

*Nota sobre o Caso Médio:* É frequentemente o cenário mais difícil de ser calculado matematicamente, pois exige conhecer ou prever a probabilidade real de distribuição dos dados na natureza.

## 💡 Conclusão
O estudo das funções de complexidade revela uma dura realidade da Ciência da Computação: **hardware não resolve problemas de algoritmos ineficientes**. Como demonstrado no material, mesmo se executarmos um algoritmo exponencial ($2^n$) em um computador 100 vezes mais rápido, o tamanho do problema que conseguimos resolver no mesmo tempo aumenta de forma pífia (ex: de 25 para apenas 31 itens). Por isso, otimizar a lógica (passar de $n^3$ para $n^2$) é sempre superior a simplesmente comprar processadores melhores.

## ✂️ Tópicos não aprofundados
* **Cálculos Algébricos Detalhados:** O passo a passo matemático para encontrar o ponto de equilíbrio onde $8n^2 = n^3$ (que resulta em $n=8$).
* **Fórmulas de Impacto de Hardware:** O desenvolvimento das equações (ex: $tt_v = x^2 \cdot t_v$) usadas para calcular as porcentagens de melhoria de tempo e velocidade entre "máquinas velhas" e "máquinas novas".
* **Gráficos e Tabelas de Dispersão:** As imagens plotando as curvas e linhas de tendência (como a reta $y = x - 1$ e o cruzamento das curvas $A$ e $B$) para instâncias de entrada variando de 1 a 12.