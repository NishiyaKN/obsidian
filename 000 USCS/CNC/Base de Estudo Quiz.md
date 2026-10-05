---

materia: Cálculo Numérico 
fonte: Quiz do Google Forms + resumo de revisão + notas da matéria 
tags:

- resumo
- calculo-numerico
- base-quiz

---
# 📝 Base de Estudo — Quiz de Cálculo Numérico

## 👁️ Visão geral

Esta nota reúne **tudo o que é preciso para responder as 21 questões** de [[Quiz — Cálculo Numérico (Forms)]]: representação em ponto flutuante, tipos de erro, cancelamento catastrófico, Teorema de Bolzano, os três métodos para achar raízes (Bisseção, Newton-Raphson e Secante), ordem de convergência e critérios de parada. Os exemplos daqui são **diferentes** dos do quiz, para o quiz continuar servindo de teste. A seção final explica os termos que aparecem como alternativas erradas, para você conseguir eliminá-las. Para aprofundar: [[1. Ponto Flutuante]] e [[Zeros de Funções — Bolzano, Bisseção e Newton-Raphson]].

## 🔢 Representação em ponto flutuante

### Forma normalizada

O computador guarda um número real como

$$x = \pm, m \cdot b^{e}$$

onde $b$ é a **base** (2, 10…), $m$ é a **mantissa** (os dígitos significativos) e $e$ é o **expoente** inteiro. A mantissa é **normalizada** quando

$$\frac{1}{b} \le m < 1 \quad\Longleftrightarrow\quad m = 0{,}d_1 d_2 \dots d_k \ \text{ com } d_1 \neq 0$$

ou seja: a vírgula fica **antes** do primeiro dígito, e esse primeiro dígito **não pode ser zero**. O $k$ é o número de dígitos que cabem na mantissa (a **precisão**).

**Como normalizar:** ande com a vírgula até ficar logo antes do primeiro dígito não nulo e compense no expoente.

- $523{,}1 = 0{,}5231 \cdot 10^{3}$ (a vírgula andou 3 casas para a esquerda → expoente $+3$)
- $0{,}006279 = 0{,}6279 \cdot 10^{-2}$ (andou 2 casas para a direita → expoente $-2$)

> [!tip] Confira o expoente multiplicando de volta $0{,}6279 \cdot 10^{-2} = 0{,}006279$ ✔. Já $0{,}6279 \cdot 10^{-3} = 0{,}0006279$ ✘ (um zero a mais). Errar o expoente por 1 é a armadilha mais comum nesse tipo de questão.

> [!info] Na lousa A professora escreveu a mantissa como $d_1{,}d_2\dots$ (ex.: $6{,}279 \cdot 10^{-3}$). O quiz e o resumo de revisão usam $0{,}d_1 d_2\dots$. Os dígitos são os mesmos; o expoente muda em 1.

### Truncamento e arredondamento

Quando o número tem mais dígitos do que os $k$ da mantissa:

|Técnica|Regra|$0{,}6279 \cdot 10^{-2}$ com $k = 3$|
|:--|:--|:--|
|**Truncamento**|**Descarta** todos os dígitos depois do $k$-ésimo, sem olhar para eles|$0{,}627 \cdot 10^{-2}$|
|**Arredondamento**|Olha o $(k+1)$-ésimo dígito: se for $\ge b/2$ (em base 10, $\ge 5$), **soma 1** ao $k$-ésimo|4º dígito $= 9 \ge 5$ → $0{,}628 \cdot 10^{-2}$|

Roteiro: **normalizar → contar $k$ dígitos → olhar o próximo → cortar ou arredondar**.

### Padrão IEEE 754

É o padrão de ponto flutuante dos computadores. Os formatos do dia a dia são em **base 2**:

|Tipo|Bits|Sinal|Expoente|Mantissa|Precisão|
|:--|:-:|:-:|:-:|:-:|:-:|
|`float` (precisão simples)|32|1|8|23|~7 dígitos decimais|
|`double` (precisão dupla)|64|1|11|52|~16 dígitos decimais|

Questões às vezes citam o IEEE 754 só como contexto e pedem a conta em base 10 — nesse caso, faça a normalização normalmente na base que o enunciado der.

### Overflow e underflow

- **Overflow**: o resultado é **maior** (em módulo) que o maior número representável. Vira `inf`.
- **Underflow**: o resultado é **diferente de zero**, mas **menor** (em módulo) que o menor número representável. Pode ser zerado.

### Épsilon da máquina

O **épsilon da máquina** $\varepsilon$ é o **menor número positivo tal que $1{,}0 + \varepsilon > 1{,}0$** no computador — a distância entre o 1 e o próximo número que a máquina consegue representar. Qualquer coisa menor que isso, somada a 1, "some". Em `double`, $\varepsilon \approx 2{,}2 \cdot 10^{-16}$. Ele mede a **precisão relativa** da máquina, e por isso uma tolerância de parada nunca deve ser menor que ele.

## 📏 Erros

### Erro absoluto e erro relativo

Seja $x$ o valor **exato** e $\bar{x}$ o valor **aproximado**:

$$E_a = |x - \bar{x}| \qquad\qquad E_r = \frac{|x - \bar{x}|}{|x|}$$

- O **erro absoluto** é a distância entre os dois valores. Tem a mesma unidade do número.
- O **erro relativo** divide o erro absoluto pelo **valor exato**. Serve para **escalar o erro pela ordem de grandeza** do número: errar por 1 ao medir 10 é grave (10%); errar por 1 ao medir 10 000 é desprezível (0,01%). Multiplicando por 100, vira porcentagem.
- Os dois têm **módulo**, então **nunca são negativos**.

> [!example] Exemplo $x = 4{,}000$ (exato) e $\bar{x} = 3{,}900$ (aproximado): $E_a = |4{,}000 - 3{,}900| = 0{,}100$ $E_r = 0{,}100 / 4{,}000 = 0{,}025$ (ou 2,5%)

### Tipos de erro

|Tipo|De onde vem|Exemplo típico|
|:--|:--|:--|
|**Erro de truncamento**|Do **método**: um processo **infinito** é cortado depois de alguns passos|Aproximar $\operatorname{sen} x \approx x - \frac{x^3}{3!}$ jogando fora os termos seguintes da **Série de Taylor**|
|**Erro de arredondamento**|Da **máquina**: o número é guardado com uma quantidade **finita de dígitos (bits)**|Guardar $1/3$ como $0{,}333$; ou $0{,}1$, que em binário é uma **dízima periódica** ($0{,}000110011\ldots_2$) e nunca é guardado exato|

> [!warning] Mesmo nome, duas coisas "Truncamento" também é o nome da técnica de cortar dígitos da mantissa (seção acima). Quando a questão fala de **Série de Taylor** ou de parar um processo infinito, é **erro de truncamento** no sentido de método. Quando fala de representar um número com bits finitos, é **erro de arredondamento**.

### Cancelamento catastrófico

É a **perda de dígitos significativos** ao **subtrair dois números muito próximos**: os dígitos iguais se cancelam e sobra pouca informação confiável.

Exemplo com 4 dígitos: $\sqrt{101} - \sqrt{100} \approx 10{,}05 - 10{,}00 = 0{,}05$ → sobrou **um** dígito significativo.

**Como evitar: reescrever a expressão para trocar a subtração por uma soma.** Com raízes, a técnica é **racionalizar** — multiplicar e dividir pelo **conjugado** (a mesma expressão com o sinal trocado):

$$\sqrt{A} - \sqrt{B} = \left(\sqrt{A} - \sqrt{B}\right) \cdot \frac{\sqrt{A} + \sqrt{B}}{\sqrt{A} + \sqrt{B}} = \frac{A - B}{\sqrt{A} + \sqrt{B}}$$

O numerador vira uma diferença **exata** (sem raízes), e o denominador é uma **soma**, que não cancela dígitos. No exemplo: $\dfrac{101 - 100}{\sqrt{101} + \sqrt{100}} = \dfrac{1}{20{,}05} \approx 0{,}04988$, com os 4 dígitos corretos.

## 📍 Teorema de Bolzano

### Enunciado e uso

> [!info] Teorema de Bolzano (Valor Intermediário) Se $f$ é **contínua** em $[a, b]$ e $$f(a) \cdot f(b) < 0$$ (sinais **opostos** nas pontas), então existe **pelo menos uma raiz** $\alpha \in (a, b)$, isto é, $f(\alpha) = 0$.

O **produto negativo** é o jeito compacto de dizer "um é positivo e o outro é negativo". Não é soma, não é derivada.

**Como usar:** calcule $f$ nas duas pontas. Se os sinais forem opostos (e $f$ for contínua — todo polinômio é), há raiz no meio.

> [!example] Exemplo $f(x) = x^3 - 2x - 5$ em $[2, 3]$: $f(2) = 8 - 4 - 5 = -1$ e $f(3) = 27 - 6 - 5 = 16$. $f(2) \cdot f(3) = -16 < 0$ → existe ao menos uma raiz em $(2, 3)$.

Rigorosamente, $f(a) \cdot f(b) < 0$ é condição **suficiente**, não necessária: com sinais iguais nas pontas ainda pode haver um número **par** de raízes.

## 🔁 Métodos para encontrar raízes

### Método da Bisseção

Parte de um intervalo $[a, b]$ com troca de sinal e **corta ao meio** a cada iteração:

$$x_k = \frac{a_k + b_k}{2}$$

Depois fica com a metade onde a troca de sinal continua: **o ponto médio substitui a ponta que tem o mesmo sinal que ele**.

> [!example] Exemplo $f(x) = x^2 - 3$ em $[1, 2]$: $f(1) = -2$ e $f(2) = 1$. $x_1 = 1{,}5$; $f(1{,}5) = -0{,}75$ (negativo, igual a $f(1)$) → substitui o $1$ → novo intervalo **$[1{,}5;\ 2]$**. Conferência: $\sqrt{3} \approx 1{,}732$ está em $[1{,}5;\ 2]$ ✔.

**Vantagem principal:** **convergência garantida** (global) — se $f$ é contínua e há troca de sinal, a raiz nunca sai do intervalo. **Desvantagem:** é lenta. Ela **precisa** de um intervalo inicial com troca de sinal (não é verdade que "não precisa de nada para começar").

### Número de iterações da Bisseção

Depois de $n$ iterações, o intervalo tem largura $\dfrac{b - a}{2^n}$. O critério de parada pela largura é:

$$\frac{b - a}{2^n} < \varepsilon$$

(é **$b - a$**, a largura, e não $a + b$).

Para saber quantas iterações bastam: calcule $\dfrac{b-a}{\varepsilon}$ e ache o **menor $n$** com $2^n$ maior que isso. Ou, pela fórmula, $n > \dfrac{\ln\left(\frac{b-a}{\varepsilon}\right)}{\ln 2}$, **arredondando para cima**.

> [!example] Exemplo $[1, 2]$ com $\varepsilon = 10^{-2}$: $\dfrac{2-1}{0{,}01} = 100$. $2^6 = 64$ (não passa), $2^7 = 128$ (passa) → **$n = 7$**. Pela fórmula: $\ln 100 / \ln 2 \approx 6{,}64$ → arredonda para cima → 7.

Potências de 2 para ter de cabeça: 2, 4, 8, 16, 32, 64, 128, 256, 512, **1024**, 2048.

### Método de Newton-Raphson

Parte de um chute inicial $x_0$ e segue a **reta tangente** até ela cortar o eixo $x$:

$$x_{k+1} = x_k - \frac{f(x_k)}{f'(x_k)}$$

Além de $f(x_k)$, é obrigatório calcular a **derivada primeira** $f'(x_k)$. Regra de derivada de potência: $(x^n)' = n,x^{n-1}$; constante tem derivada 0.

> [!example] Exemplo $f(x) = x^2 - 3$, $x_0 = 2$: $f'(x) = 2x$; $f(2) = 1$; $f'(2) = 4$. $x_1 = 2 - \dfrac{1}{4} = 1{,}75$ (a raiz é $\sqrt{3} \approx 1{,}732$).

### Limitações do Newton-Raphson

1. **Derivada nula** ($f'(x_k) = 0$): a fórmula divide por zero e o método falha.
2. **Raiz múltipla** (multiplicidade $m > 1$, como em $(x-1)^2$): a convergência deixa de ser quadrática e passa a ser **linear**.
3. **Chute inicial longe da raiz**: o método pode **divergir** ou ficar **oscilando** sem convergir.
4. Precisa da **derivada**, que pode ser difícil de calcular.

### Método da Secante

É o Newton **sem derivada**: troca $f'(x_k)$ pela inclinação da reta que passa pelos **dois últimos pontos**. Por isso começa com **dois** pontos, $x_0$ e $x_1$:

$$x_{k+1} = x_k - f(x_k) \cdot \frac{x_k - x_{k-1}}{f(x_k) - f(x_{k-1})}$$

Para não confundir as fórmulas:

|Fórmula|Método|
|:--|:--|
|$x_{k+1} = x_k - \dfrac{f(x_k)}{f'(x_k)}$ (tem derivada)|**Newton-Raphson**|
|$x_{k+1} = x_k - f(x_k) \cdot \dfrac{x_k - x_{k-1}}{f(x_k) - f(x_{k-1})}$ (dois pontos, sem derivada)|**Secante**|
|$x_k = \dfrac{a_k + b_k}{2}$ (média)|**Bisseção**|

> [!example] Exemplo $f(x) = x^2 - 3$, $x_0 = 1$, $x_1 = 2$: $f(1) = -2$, $f(2) = 1$. $x_2 = 2 - 1 \cdot \dfrac{2 - 1}{1 - (-2)} = 2 - \dfrac{1}{3} \approx 1{,}6667$.

### Ordem de convergência

A **ordem $p$** diz a rapidez com que o método se aproxima da raiz: quanto **maior**, mais rápido.

|Método|Tipo|Ordem $p$|Como decorar|
|:--|:--|:-:|:--|
|**Bisseção**|Intervalar|$1$ (linear)|O mais lento|
|**Secante**|Aberto|$\approx 1{,}618$ (número de ouro)|No meio|
|**Newton-Raphson**|Aberto|$2$ (quadrática, em raiz simples)|O mais rápido|

Ordem crescente: **Bisseção (1) < Secante (1,618) < Newton (2)**.

### Critérios de parada

Um método iterativo precisa saber a hora de parar. Os critérios usuais, dada uma tolerância:

|Critério|Condição|
|:--|:--|
|Tolerância no **valor da função** (resíduo)|$\lvert f(x_k) \rvert < \varepsilon_1$|
|Tolerância no **passo** (diferença entre iterações)|$\lvert x_k - x_{k-1} \rvert < \varepsilon_2$|
|Tolerância relativa no passo|$\lvert x_k - x_{k-1} \rvert / \lvert x_k \rvert < \varepsilon$|
|**Número máximo de iterações**|$k \ge N_{max}$|
|Largura do intervalo (Bisseção)|$(b - a)/2^n < \varepsilon$|

Um conjunto **completo** combina critério sobre $f$, critério sobre $x$ **e** um limite de iterações (proteção contra laço infinito). Esperar erro **exatamente zero** não funciona: por causa do arredondamento, isso quase nunca acontece.

## ⚠️ Pegadinhas e distratores

Termos que aparecem como alternativas erradas e o que eles são de verdade:

|Termo|O que é|Por que não serve como resposta|
|:--|:--|:--|
|**Erro de mal condicionamento**|Propriedade do **problema**: pequenas mudanças nos dados causam grandes mudanças no resultado (contexto externo)|Não é o erro de cortar uma Série de Taylor|
|**Erro de discretização**|Trocar algo contínuo por pontos discretos, como uma derivada por uma diferença (contexto externo)|Não é a causa do erro de representar $0{,}1$ em binário|
|**Erro de modelagem / formulação**|O modelo matemático não descreve bem o fenômeno real (contexto externo)|Não vem da máquina nem do método|
|**Arredondamento por excesso**|Arredondar sempre para cima (contexto externo)|Descartar os dígitos é **truncamento**|
|**Underflow gradual**|No IEEE 754, números abaixo do menor normalizado que perdem precisão aos poucos (contexto externo)|Não é o nome do $\varepsilon$ com $1 + \varepsilon > 1$|
|**Cancelamento catastrófico**|Perda de dígitos ao subtrair números próximos|Não é o nome de exceder o maior valor (isso é **overflow**)|

Outras armadilhas:

- ==**Erro relativo nunca é negativo**== (tem módulo). Alternativas com $E_a$ ou $E_r$ negativos estão erradas.
- Não inverta: $E_a$ é a **diferença**; $E_r$ é a diferença **dividida pelo exato**.
- Bolzano é **produto** $f(a) \cdot f(b) < 0$, não soma e não derivada.
- Bisseção: largura é **$(b - a)$**; nº de iterações arredonda **para cima**.
- Na normalização, **multiplique de volta** para conferir o expoente.

## 💡 Fechamento

Quase todo o quiz se resolve com seis ideias: **normalizar e arredondar** a mantissa; **erro relativo = absoluto ÷ exato**; **truncamento = método, arredondamento = máquina**; **Bolzano = sinais opostos**; as **três fórmulas** (média, tangente com derivada, secante com dois pontos) e suas **ordens** 1, 2 e 1,618; e **parar** combinando tolerâncias com um máximo de iterações.