---

materia: Cálculo Numérico 
fonte: Exercícios criados a partir das lousas, do PDF de ponto flutuante e do resumo de revisão 
tags:

- atividade
- treino
- calculo-numerico

---
# 📝 Treino — Cálculo Numérico

## 👁️ Como usar

Dois sets: o **Set 1** é simples, para aquecer e checar o básico; o **Set 2** é no nível dos exemplos da lousa e do resumo de revisão. O gabarito fica **no fim de cada set**, recolhido — clique no título para abrir. Os exercícios e o gabarito foram criados por mim, e todas as contas foram conferidas no computador.

Regras usadas em todos os exercícios, salvo quando o enunciado disser outra coisa:

- **Mantissa** no formato do resumo de revisão: $0{,}d_1 d_2 \dots d_k$, com $d_1 \neq 0$. Quando a resposta muda na convenção da lousa ($d_1{,}d_2\dots$), o gabarito mostra as duas.
- **Arredondamento**: dígito seguinte $\ge 5$ sobe. A regra da ABNT só entra no exercício que pede por ela.
- **Operações**: alinhe os expoentes pelo maior, opere com todos os dígitos e **arredonde o resultado** para $k$ dígitos.
- **Newton e Secante**: 4 casas decimais, arredondando a cada passo.

---

## 🟢 Set 1 — Básico

**1.** Converta $45$ para a base 2.

**2.** Converta para a base 10: (a) $(1011)_2$; (b) $(212)_3$.

**3.** Escreva na forma normalizada $0{,}d_1 d_2 \dots \times 10^e$: (a) $0{,}00372$; (b) $523{,}1$.

**4.** Represente $x = 2{,}71828$ com $k = 3$ dígitos na mantissa: (a) por truncamento; (b) por arredondamento.

**5.** Para $x = 5{,}0$ (exato) e $\bar{x} = 4{,}9$ (aproximado), calcule o erro absoluto e o erro relativo.

**6.** No sistema $F(10, 2, -1, 1)$, calcule: (a) a quantidade total de números; (b) o maior número positivo; (c) o menor número positivo.

**7.** Mostre que $f(x) = x^2 - 2$ tem pelo menos uma raiz em $[1, 2]$.

**8.** Faça a 1ª iteração da Bisseção para $f(x) = x^2 - 2$ em $[1, 2]$ e diga o novo intervalo.

**9.** Faça uma iteração do Método de Newton-Raphson para $f(x) = x^2 - 2$ com $x_0 = 1$.

**10.** Quantas iterações da Bisseção garantem erro menor que $\varepsilon = 0{,}1$ no intervalo $[0, 1]$?

**11.** Responda rápido: (a) Qual método precisa da derivada: Bisseção ou Newton? (b) Qual método é intervalar: Bisseção ou Newton? (c) Um resultado maior que $x_{max}$ causa overflow ou underflow? (d) Quantos bits tem um `double` e como eles se dividem?

> [!success]- Gabarito — Set 1 **1.** $45 \div 2 = 22$ r **1**; $22 \div 2 = 11$ r **0**; $11 \div 2 = 5$ r **1**; $5 \div 2 = 2$ r **1**; $2 \div 2 = 1$ r **0**. Lendo de baixo para cima (último quociente, depois os restos subindo): **$(101101)_2$**. Conferência: $32 + 8 + 4 + 1 = 45$ ✔
> 
> **2.** (a) $1 \cdot 8 + 0 \cdot 4 + 1 \cdot 2 + 1 \cdot 1 = 11$. (b) $2 \cdot 9 + 1 \cdot 3 + 2 \cdot 1 = 23$.
> 
> **3.** (a) **$0{,}372 \cdot 10^{-2}$**; (b) **$0{,}5231 \cdot 10^{3}$**. (Na lousa: $3{,}72 \cdot 10^{-3}$ e $5{,}231 \cdot 10^{2}$.)
> 
> **4.** Normalizado: $0{,}271828 \cdot 10^1$. (a) Truncamento: **$0{,}271 \cdot 10^1$**. (b) O 4º dígito é 8 ($\ge 5$), sobe: **$0{,}272 \cdot 10^1$**.
> 
> **5.** $E_a = |5{,}0 - 4{,}9| = 0{,}1$. $E_r = 0{,}1 / 5{,}0 = 0{,}02$ (2%) — dividindo pelo **exato**.
> 
> **6.** (a) Expoentes de $-1$ a $1$ → 3. $N = 2 \cdot 9 \cdot 10 \cdot 3 + 1 = 541$. (b) $0{,}99 \cdot 10^1 = 9{,}9$. (c) $0{,}10 \cdot 10^{-1} = 0{,}01$. (Na lousa: maior $9{,}9 \cdot 10^1 = 99$; menor $1{,}0 \cdot 10^{-1} = 0{,}1$. O $N$ é o mesmo.)
> 
> **7.** $f$ é polinômio, portanto contínua. $f(1) = -1 < 0$ e $f(2) = 2 > 0$ → $f(1) \cdot f(2) < 0$ → por **Bolzano**, há raiz em $(1, 2)$.
> 
> **8.** $m = 1{,}5$; $f(1{,}5) = 2{,}25 - 2 = 0{,}25 > 0$ → mesmo sinal de $f(2)$ → $m$ substitui o $b$ → **$[1;\ 1{,}5]$**. (A raiz é $\sqrt{2} \approx 1{,}414$ ✔.)
> 
> **9.** $f'(x) = 2x$. $f(1) = -1$, $f'(1) = 2$ → $x_1 = 1 - \frac{-1}{2} = 1{,}5$.
> 
> **10.** $(1 - 0)/0{,}1 = 10$. Primeiro $2^n$ maior que 10: $2^3 = 8$ (não), $2^4 = 16$ (sim) → **$n = 4$**.
> 
> **11.** (a) **Newton**. (b) **Bisseção**. (c) **Overflow**. (d) **64 bits**: 1 de sinal, 11 de expoente, 52 de mantissa.

---

## 🟡 Set 2 — Nível da matéria

**1.** (a) Converta $200$ para a base 3. (b) Converta $(1432)_5$ para a base 10.

**2.** No sistema $F(10, 3, -3, 4)$, calcule a quantidade total de números, o maior e o menor número positivo.

**3.** No sistema $F(2, 3, -1, 2)$, calcule a quantidade total de números e o maior e o menor número positivo, em decimal.

**4.** Represente $x = 0{,}0034567$ em $F(10, 4, -5, 5)$ por truncamento e por arredondamento e calcule o erro relativo de cada um.

**5.** Em $F(10, 3, -5, 5)$, efetue $x + y$ com $x = 0{,}937 \cdot 10^4$ e $y = 0{,}272 \cdot 10^2$. Calcule também o erro absoluto em relação à soma exata.

**6.** Em $F(10, 3, -5, 5)$, calcule, somando da esquerda para a direita: $$S_1 = 1000 + \sum_{i=1}^{5} 2 \qquad\qquad S_2 = \sum_{i=1}^{5} 2 + 1000$$ Qual está certo? Por quê?

**7.** Em $F(10, 3, -5, 5)$, com $a = 45{,}67$ e $b = 2{,}342$, calcule $(a - b)^2$ de dois jeitos: direto e pela forma $a^2 - 2ab + b^2$. Qual ficou mais perto do valor exato?

**8.** Avalie $f(x) = \sqrt{x+1} - \sqrt{x}$ para $x = 1000$ com 4 dígitos significativos: (a) direto; (b) racionalizando. Qual é o problema da forma direta?

**9.** Arredonde para 2 casas decimais **pela regra da ABNT**: (a) $3{,}145$; (b) $2{,}675$; (c) $7{,}4351$; (d) $1{,}2849$. Em qual deles a regra simples ("$\ge 5$ sobe") daria resultado diferente?

**10.** No sistema $F(10, 3, -4, 4)$, diga o que acontece em cada operação: (a) $(0{,}600 \cdot 10^3) \times (0{,}500 \cdot 10^3)$ (b) $(0{,}200 \cdot 10^{-2}) \times (0{,}300 \cdot 10^{-3})$

**11.** Isole **todas** as raízes reais de $f(x) = x^3 - 6x + 2$, tabelando $f$ nos inteiros de $-3$ a $3$.

**12.** Faça 4 iterações da Bisseção para $f(x) = x^3 - 6x + 2$ em $[2, 3]$. Dê $\bar{x}$ (o último ponto médio) e o intervalo final.

**13.** Quantas iterações da Bisseção garantem o erro pedido? (a) $[1, 3]$ com $\varepsilon = 10^{-2}$ (b) $[0, 2]$ com $\varepsilon = 10^{-4}$

**14.** Encontre a raiz de $f(x) = x^3 - 2x - 2$ pelo Método de Newton-Raphson, com 4 casas decimais. Isole a raiz primeiro e use $x_0 = 2$.

**15.** Faça 2 iterações do Método da Secante para $f(x) = x^2 - 5$, com $x_0 = 2$ e $x_1 = 3$.

**16.** Responda: (a) Classifique o erro: usar $e^x \approx 1 + x + \frac{x^2}{2}$; guardar $\frac{1}{3}$ como $0{,}333$. (b) Por que a Bisseção sempre converge e o Newton não? (c) O que acontece se um programa em `double` usar tolerância $10^{-20}$ no critério de parada? (d) Qual a ordem de convergência de Bisseção, Newton e Secante?

> [!success]- Gabarito — Set 2 **1.** (a) $200 \div 3 = 66$ r **2**; $66 \div 3 = 22$ r **0**; $22 \div 3 = 7$ r **1**; $7 \div 3 = 2$ r **1**. De baixo para cima: **$(21102)_3$**. Conferência: $162 + 27 + 9 + 0 + 2 = 200$ ✔ (b) $1 \cdot 125 + 4 \cdot 25 + 3 \cdot 5 + 2 \cdot 1 = 125 + 100 + 15 + 2 = 242$.
> 
> **2.** Expoentes de $-3$ a $4$ → 8. $N = 2 \cdot 9 \cdot 10^2 \cdot 8 + 1 = 14,401$. Maior: $0{,}999 \cdot 10^4 = 9990$. Menor: $0{,}100 \cdot 10^{-3} = 0{,}0001$. (Na lousa: maior $9{,}99 \cdot 10^4 = 99,900$; menor $1{,}00 \cdot 10^{-3} = 0{,}001$.)
> 
> **3.** Em base 2, $d_1 = 1$ (única opção). Expoentes de $-1$ a $2$ → 4. $N = 2 \cdot 1 \cdot 2^2 \cdot 4 + 1 = 33$. Maior: $(0{,}111)_2 = \frac12 + \frac14 + \frac18 = 0{,}875$; $\times 2^2$ → **3,5**. Menor: $(0{,}100)_2 = 0{,}5$; $\times 2^{-1}$ → **0,25**. (Na lousa: maior $(1{,}11)_2 \times 2^2 = 1{,}75 \times 4 = 7$; menor $(1{,}00)_2 \times 2^{-1} = 0{,}5$.)
> 
> **4.** Normalizado: $0{,}34567 \cdot 10^{-2}$ (expoente $-2$, dentro do sistema).
> 
> - Truncamento: **$0{,}3456 \cdot 10^{-2}$**. $E_a = 0{,}0034567 - 0{,}003456 = 7 \cdot 10^{-7}$; $E_r = 7 \cdot 10^{-7} / 0{,}0034567 \approx$ **$2{,}03 \cdot 10^{-4}$** (0,0203%).
> - Arredondamento: 5º dígito é 7 → sobe: **$0{,}3457 \cdot 10^{-2}$**. $E_a = 3 \cdot 10^{-7}$; $E_r \approx$ **$8{,}68 \cdot 10^{-5}$** (0,0087%).
> 
> **5.** Alinhar pelo maior expoente: $y = 0{,}00272 \cdot 10^4$. Somar: $0{,}937 + 0{,}00272 = 0{,}93972 \cdot 10^4$. Arredondar (4º dígito 7): **$0{,}940 \cdot 10^4 = 9400$**. Exato: $9397{,}2$ → $E_a = 2{,}8$.
> 
> **6.** $1000 = 0{,}100 \cdot 10^4$ e $2 = 0{,}0002 \cdot 10^4$.
> 
> - $S_1$: $0{,}100 + 0{,}0002 = 0{,}1002$ → 3 dígitos → $0{,}100 \cdot 10^4$. O 2 some, e isso se repete 5 vezes → **$S_1 = 1000$**.
> - $S_2$: $2 + 2 + 2 + 2 + 2 = 10$ (exato) $= 0{,}001 \cdot 10^4$; $0{,}100 + 0{,}001 = 0{,}101 \cdot 10^4$ → **$S_2 = 1010$**.
> 
> O exato é $1010$: **$S_2$ está certo**. Somando os pequenos primeiro, eles se acumulam antes de encontrar o número grande.
> 
> **7.** Representar: $a = 0{,}4567 \cdot 10^2 \to 0{,}457 \cdot 10^2$; $b = 0{,}2342 \cdot 10^1 \to 0{,}234 \cdot 10^1$. **Direto:** $a - b = 0{,}457 \cdot 10^2 - 0{,}0234 \cdot 10^2 = 0{,}4336 \cdot 10^2 \to 0{,}434 \cdot 10^2$. $(0{,}434 \cdot 10^2)^2 = 0{,}188356 \cdot 10^4 \to$ **$0{,}188 \cdot 10^4 = 1880$**. **Expandido:**
> 
> - $a^2 = 0{,}208849 \cdot 10^4 \to 0{,}209 \cdot 10^4$
> - $2ab = 2 \cdot 0{,}457 \cdot 0{,}234 \cdot 10^3 = 0{,}213876 \cdot 10^3 \to 0{,}214 \cdot 10^3$
> - $b^2 = 0{,}054756 \cdot 10^2 = 0{,}54756 \cdot 10^1 \to 0{,}548 \cdot 10^1$
> - $a^2 - 2ab = 0{,}209 \cdot 10^4 - 0{,}0214 \cdot 10^4 = 0{,}1876 \cdot 10^4 \to 0{,}188 \cdot 10^4$
> - $+, b^2$: $0{,}188 \cdot 10^4 + 0{,}000548 \cdot 10^4 = 0{,}188548 \cdot 10^4 \to$ **$0{,}189 \cdot 10^4 = 1890$**
> 
> Exato: $(45{,}67 - 2{,}342)^2 = 43{,}328^2 \approx 1877{,}3$. O **direto** (1880) ficou mais perto: faz menos operações, logo menos arredondamentos.
> 
> **8.** (a) $\sqrt{1001} \approx 31{,}6386 \to 31{,}64$; $\sqrt{1000} \approx 31{,}6228 \to 31{,}62$; $31{,}64 - 31{,}62 = 0{,}02$. (b) $f(x) = \dfrac{1}{\sqrt{x+1} + \sqrt{x}}$ → $\dfrac{1}{31{,}64 + 31{,}62} = \dfrac{1}{63{,}26} \approx$ **0,01581**. O valor verdadeiro é $\approx 0{,}015807$. A forma direta sofre **cancelamento catastrófico**: os dígitos iguais ($31{,}6$) se cancelam, sobra um só dígito significativo, e o erro passa de 25%.
> 
> **9.** (a) $3{,}14,|,5$ → 5 exato, anterior 4 é **par** → mantém → **3,14**. (b) $2{,}67,|,5$ → anterior 7 é **ímpar** → sobe → **2,68**. (c) $7{,}43,|,51$ → depois do 5 vem 1, está acima da metade → sobe → **7,44**. (d) $1{,}28,|,49$ → 4 < 5 → mantém → **1,28**. Só o **(a)** muda: pela regra simples, $3{,}145 \to 3{,}15$.
> 
> **10.** (a) $600 \times 500 = 300,000 = 0{,}300 \cdot 10^6$. Expoente $6 > 4$ → **overflow**. (b) $0{,}002 \times 0{,}0003 = 0{,}0000006 = 0{,}600 \cdot 10^{-6}$. Não nulo, com expoente $-6 < -4$ → **underflow**. (Na convenção da lousa, $3{,}00 \cdot 10^5$ e $6{,}00 \cdot 10^{-7}$: as conclusões são as mesmas.)
> 
> **11.**
> 
> |$x$|$-3$|$-2$|$-1$|$0$|$1$|$2$|$3$|
> |:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
> |$f(x)$|$-7$|$6$|$7$|$2$|$-3$|$-2$|$11$|
> |Sinal|$-$|$+$|$+$|$+$|$-$|$-$|$+$|
> 
> Três trocas de sinal → raízes em **$[-3, -2]$**, **$[0, 1]$** e **$[2, 3]$**. Uma cúbica tem no máximo 3 raízes reais, então achamos todas.
> 
> **12.** Pontas: $f(2) = -2$ (**negativo**) e $f(3) = 11$ (positivo). Atenção: aqui $f(a) < 0$.
> 
> |Iteração|$a$|$b$|$m$|$f(m)$|Novo intervalo|
> |:-:|:-:|:-:|:-:|:-:|:-:|
> |1|2|3|2,5|$+2{,}625$|$[2;\ 2{,}5]$|
> |2|2|2,5|2,25|$-0{,}109$|$[2{,}25;\ 2{,}5]$|
> |3|2,25|2,5|2,375|$+1{,}146$|$[2{,}25;\ 2{,}375]$|
> |4|2,25|2,375|2,3125|$+0{,}491$|$[2{,}25;\ 2{,}3125]$|
> 
> **$\bar{x} = 2{,}3125$**, intervalo final **$[2{,}25;\ 2{,}3125]$**. A raiz verdadeira é $\approx 2{,}2618$ ✔. Regra usada: $m$ substitui a ponta com o **mesmo sinal** de $f(m)$.
> 
> **13.** (a) $(3 - 1)/0{,}01 = 200$. $2^7 = 128$ (não), $2^8 = 256$ (sim) → **$n = 8$**. Pela fórmula: $n > \log 200 / \log 2 \approx 7{,}64$ → 8. (b) $(2 - 0)/0{,}0001 = 20,000$. $2^{14} = 16,384$ (não), $2^{15} = 32,768$ (sim) → **$n = 15$**. Pela fórmula: $\approx 14{,}29$ → 15.
> 
> **14.** Isolar: $f(1) = -3$ e $f(2) = 2$ → raiz em $[1, 2]$. Derivada: $f'(x) = 3x^2 - 2$.
> 
> |Iteração|$x$|$f(x)$|$f'(x)$|$x_{n+1}$|
> |:-:|:-:|:-:|:-:|:-:|
> |0|2|2|10|1,8|
> |1|1,8|0,232|7,72|1,7699|
> |2|1,7699|0,0045|7,3976|1,7693|
> |3|1,7693|$\approx 0$|7,3913|1,7693|
> 
> **Raiz $\approx 1{,}7693$** ($x_{n+1}$ repetiu nas 4 casas). Primeira linha: $x_1 = 2 - \frac{2}{10} = 1{,}8$. Segunda: $f(1{,}8) = 5{,}832 - 3{,}6 - 2 = 0{,}232$; $f'(1{,}8) = 3 \cdot 3{,}24 - 2 = 7{,}72$; $x_2 = 1{,}8 - 0{,}0301 = 1{,}7699$.
> 
> **15.** $f(2) = -1$ e $f(3) = 4$. $x_2 = 3 - 4 \cdot \dfrac{3 - 2}{4 - (-1)} = 3 - \dfrac{4}{5} = 2{,}2$. $f(2{,}2) = 4{,}84 - 5 = -0{,}16$. $x_3 = 2{,}2 - (-0{,}16) \cdot \dfrac{2{,}2 - 3}{-0{,}16 - 4} = 2{,}2 - \dfrac{0{,}128}{-4{,}16} = 2{,}2 + 0{,}0308 = 2{,}2308$. (A raiz é $\sqrt{5} \approx 2{,}2361$.)
> 
> **16.** (a) Série cortada no $x^2$ → **truncamento** (erro do método). $1/3 \to 0{,}333$ → **arredondamento** (dígitos finitos da máquina). (b) A Bisseção mantém a raiz sempre presa num intervalo com troca de sinal, que cai pela metade a cada passo. O Newton só segue a tangente a partir de um ponto: pode falhar com $f'(x) \approx 0$, oscilar ou divergir se o chute for ruim. (c) O critério **nunca é atingido**, porque o épsilon da máquina do `double` é $\approx 2{,}2 \cdot 10^{-16}$, e perto de 1 duas aproximações não ficam mais próximas que isso. O laço só para pelo número máximo de iterações. (d) Bisseção: $p = 1$ (linear); Newton: $p = 2$ (quadrática); Secante: $p \approx 1{,}618$.