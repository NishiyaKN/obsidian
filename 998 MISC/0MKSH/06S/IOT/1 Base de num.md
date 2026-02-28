### 📜 Visão Geral
Toda a computação moderna é construída sobre o sistema binário (base 2), que utiliza apenas os dígitos 0 e 1 para representar dados e instruções. Este resumo aborda os sistemas de numeração essenciais para a ciência da computação (Binário, Octal, Decimal e Hexadecimal), as técnicas para conversão entre essas bases, o uso de prefixos de medida para quantificar dados e a representação de texto através do padrão ASCII.

---

### 🔢 Sistemas de Numeração em Computação
Um sistema de numeração é definido por sua **base** (a quantidade de algarismos que utiliza) e por ser **posicional** (o valor de um algarismo depende de sua posição no número).

| Sistema         | Base | Algarismos Utilizados                            |
| :-------------- | :--: | :----------------------------------------------- |
| **Binário**     |  2   | `0`, `1`                                         |
| **Octal**       |  8   | `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`           |
| **Decimal**     |  10  | `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9` |
| **Hexadecimal** |  16  | `0`-`9`, `A`, `B`, `C`, `D`, `E`, `F`            |

O sistema binário é fundamental para os computadores, pois seus dois algarismos podem ser facilmente representados por dois níveis de tensão elétrica (ligado/desligado). Octal and Hexadecimal são usados como uma forma mais compacta e legível de representar longas sequências de bits.

---

### ⚙️ Conversão Rápida entre Bases (via Binário)
A conversão entre as bases 2, 8 e 16 é direta e não requer passar pela base 10, pois elas são potências de 2. A técnica consiste em agrupar os bits:

* **Binário ↔ Octal**: Agrupam-se os bits de **3 em 3**. Cada trio de bits corresponde a um único dígito octal.
    * Exemplo: `101110`₂ → `101` `110` → `56`₈

* **Binário ↔ Hexadecimal**: Agrupam-se os bits de **4 em 4**. Cada quarteto de bits corresponde a um único dígito hexadecimal.
    * Exemplo: `11010111`₂ → `1101` `0111` → `D7`₁₆

* **Octal ↔ Hexadecimal**: Usa-se o **binário como intermediário**. Primeiro converte-se o número para binário e depois reagrupam-se os bits para a base de destino.
    * Exemplo: `1F`₁₆ → `0001` `1111` → `00011111`₂ → `011` `111` → `37`₈

---

### 📈 Prefixos de Medida (SI vs. Computação)
Prefixos como kilo, mega e giga têm significados diferentes no Sistema Internacional (SI) e na computação.

| Prefixo (Símbolo) | Significado Padrão (Base 10) | Significado em Computação (Base 2) |
| :--- | :--- | :--- |
| **kilo (k)** | $10^3$ (mil) | $2^{10}$ (1.024) |
| **mega (M)** | $10^6$ (milhão) | $2^{20}$ (aprox. 1 milhão) |
| **giga (G)** | $10^9$ (bilhão) | $2^{30}$ (aprox. 1 bilhão) |
| **tera (T)** | $10^{12}$ (trilhão) | $2^{40}$ (aprox. 1 trilhão) |

Essa diferença é a razão pela qual um disco rígido de "1 TB" (1 trilhão de bytes) é reportado pelo sistema operacional como tendo aproximadamente "931 GB" (gibibytes).

---

### 🔡 Representação de Texto: ASCII
Para que os computadores possam manipular texto, é preciso um padrão para converter caracteres em números binários.

* **ASCII (American Standard Code for Information Interchange)** é um código que usa **7 bits** para representar 128 caracteres, incluindo:
    * 95 caracteres gráficos (letras, números, pontuação).
    * 33 caracteres de controle (não-imprimíveis, como `NUL`, `ENTER`, `TAB`).
* Como os dados são armazenados em **bytes (8 bits)**, o oitavo bit é frequentemente usado para estender o padrão, permitindo a representação de caracteres adicionais, como letras acentuadas (padrões UTF-8, Windows Code Page, etc.).

### 🏁 Conclusão
O domínio dos sistemas de numeração e das conversões de base é uma habilidade fundamental em ciência da computação, pois revela como os computadores manipulam toda e qualquer informação em seu nível mais básico. Da mesma forma, entender a diferença entre os prefixos de medida em base 10 e base 2 é essencial para interpretar corretamente as capacidades de armazenamento e as taxas de transferência de dados.

### 🗑️ Tópicos não aprofundados
* História e exemplos de sistemas de numeração antigos (egípcio, maia).
* Métodos de conversão detalhados de e para a base decimal.
* Dezenas de exercícios de conversão de base e suas respostas.
* Tabelas completas de caracteres ASCII (controle, gráficos e estendidos).