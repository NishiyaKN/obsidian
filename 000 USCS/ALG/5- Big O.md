# 📝 Análise de Algoritmos: Notação Big Oh

## 🔍 Visão Geral
A notação Big Oh ($O$) é uma notação assintótica utilizada na ciência da computação para exprimir a ordem de grandeza do tempo de execução (ou espaço) de um algoritmo em relação ao tamanho da sua entrada ($n$). Seu principal objetivo é fornecer um limite superior de crescimento, permitindo que constantes e termos de menor grau sejam desprezados para focar exclusivamente no fator que mais impacta a escalabilidade do algoritmo quando a entrada tende ao infinito.

## 📚 Tópicos Principais

### Definição Formal
Diz-se que uma função $f(n)$ é $O(g(n))$ se existirem constantes positivas $c > 0$ e $n_0 \ge 1$ tais que:
$f(n) \le c \cdot g(n)$ para todo inteiro $n \ge n_0$.
- Na prática, isso significa que a função $g(n)$ multiplicada por uma constante sempre será maior ou igual ao tempo real $f(n)$ a partir de um ponto $n_0$.

### Majorando Funções (Exemplo Matemático)
Para provar que uma função polinomial pertence a uma ordem de complexidade, substitui-se os termos de menor grau por termos do maior grau encontrado, somando os coeficientes para encontrar a constante $c$.

```python
# Exemplo conceitual da lógica de simplificação:
f(n) = 5n^2 + 10n + 8
# Passo 1: Majora-se todos os termos para a maior potência de n (n^2)
f(n) <= 5n^2 + 10n^2 + 8n^2
# Passo 2: Soma-se os coeficientes para encontrar 'c'
f(n) <= 23n^2  --> Portanto, é O(n^2) com c = 23 e n >= 1.
```

### Limite Superior e Otimização
A notação Big Oh define uma **cota superior**. Embora seja matematicamente correto dizer que um algoritmo linear ($O(n)$) também pertence aos conjuntos $O(n^2)$ ou $O(n^3)$, na prática busca-se sempre a cota mais justa (menor limitante superior).
A cota superior de um problema pode ser rebaixada ao longo do tempo caso pesquisadores descubram novos algoritmos mais eficientes.

### Outras Notações Assintóticas
* **Big-Omega ($\Omega$):** Define o limite inferior de um algoritmo (melhor caso estrutural).
* **Big-Theta ($\Theta$):** Define um limite exato (justo), onde a função é limitada tanto superiormente quanto inferiormente pela mesma ordem de grandeza.

## 📊 Comparações e Estruturas

### Classes de Complexidade Comuns
| Notação       | Ordem        | Crescimento (Desempenho)     |
| :------------ | :----------- | :--------------------------- |
| $O(1)$        | Constante    | Excelente (independe de $n$) |
| $O(\log n)$   | Logarítmica  | Muito Bom                    |
| $O(n)$        | Linear       | Bom                          |
| $O(n \log n)$ | Linearítmica | Razoável                     |
| $O(n^2)$      | Quadrática   | Ruim (cresce rapidamente)    |

### Evolução do Limite Superior: Multiplicação de Matrizes
Exemplo prático de como a cota superior de um problema clássico diminuiu através da invenção de novos algoritmos:

| Ano | Autor/Algoritmo | Complexidade (Cota Superior) |
| :--- | :--- | :--- |
| Clássico | Método Trivial | $O(n^3)$ |
| 1969 | V. Strassen | $O(n^{2.807})$ |
| 1990 | Coppersmith e Winograd| $O(n^{2.376})$ |
| 2011 | V. Williams | $O(n^{2.372})$ |

## 🎯 Conclusão
A notação Big Oh fornece um método padronizado e matemático para comparar a eficiência teórica de algoritmos sem depender de hardware ou especificidades de implementação. Focar no termo de maior grau e ignorar constantes garante uma visão de longo prazo sobre o comportamento do software, permitindo que desenvolvedores façam escolhas de design que suportem grandes volumes de dados.

## ✂️ Tópicos não aprofundados
- Analogias extensas comparando a cota superior com o recorde mundial esportivo (ex: atletismo / Usain Bolt).
- O processo algébrico completo e prova por redução ao absurdo demonstrando por que $2n^2 - 3n + 4$ não pode ser $O(n)$.
- Informações institucionais, e-mail do professor e dados específicos da universidade (USCS).