### 📜 Visão Geral
A **Análise Léxica**, também conhecida como *scanning*, é a **primeira fase** de um compilador. Sua principal função é ler o código-fonte como uma sequência de caracteres e agrupá-los em unidades significativas chamadas **tokens**. Essa fase serve como a base para a análise sintática, simplificando o processo ao lidar com a formatação bruta do código e organizar a entrada para as etapas seguintes.

---

### 🔍 Conceitos Fundamentais: Token, Lexema e Padrão
A compreensão desses três termos é central para a análise léxica. Eles descrevem, respectivamente, a regra, o texto real e a categoria simbólica.

| Conceito 💡 | Definição | Exemplo |
| :--- | :--- | :--- |
| **Padrão** | Uma regra, geralmente descrita por uma **Expressão Regular**, que define como os lexemas de um token devem ser formados. | A regra para um identificador: "uma letra seguida por zero ou mais letras ou dígitos" (`letra(letra\|digito)*`). |
| **Lexema** | A sequência de caracteres no código-fonte que corresponde a um padrão. | O texto `varSoma` no código-fonte. |
| **Token** | Um símbolo que representa uma categoria de lexemas. É a unidade que o analisador léxico envia para o analisador sintático. | O token `<ID, "varSoma">`, onde `ID` é a classe (identificador) e `"varSoma"` é o atributo (o lexema em si). |

---

### ⚙️ O Processo de Análise Léxica
O analisador léxico (ou *scanner*) opera como um serviço para o analisador sintático (*parser*), que solicita o próximo token da entrada conforme necessário. Durante seu trabalho, o scanner também realiza tarefas importantes:

* **Remove "ruído"**: Ignora elementos que não têm significado sintático, como **espaços em branco, comentários e quebras de linha**.
* **Interage com a Tabela de Símbolos**: Quando um lexema para um identificador (como um nome de variável) é encontrado, ele é armazenado na **Tabela de Símbolos**. O token enviado ao parser pode conter um ponteiro para essa entrada, o que é mais eficiente do que enviar a string inteira repetidamente.

---

### 📐 Formalismos para Reconhecimento: Expressões Regulares e Autômatos
A implementação de um analisador léxico é baseada em dois formalismos da teoria da computação:

1.  **Expressões Regulares (ER)**: São usadas para **especificar os padrões** de cada tipo de token. Por exemplo, uma ER pode definir o que constitui um número, um identificador ou um operador em uma linguagem.
2.  **Autômatos Finitos (AF)**: São o mecanismo de **reconhecimento** construído a partir das expressões regulares. Um autômato é como uma máquina de estados que consome os caracteres do código-fonte. Se, ao final de uma sequência de caracteres, a máquina estiver em um estado de aceitação, o lexema é reconhecido com sucesso.

---

### 🛠️ Geradores de Analisadores Léxicos (Lex/Flex)
Em vez de construir um scanner manualmente, os programadores frequentemente usam ferramentas geradoras como **Lex** ou **Flex**. O processo funciona da seguinte forma:
1.  O desenvolvedor escreve um arquivo de especificação que define os padrões dos tokens usando **expressões regulares** e as **ações** a serem tomadas quando cada padrão é reconhecido.
2.  A ferramenta (ex: Flex) lê esse arquivo e **gera automaticamente o código-fonte** (em C, por exemplo) de um analisador léxico completo e otimizado.
3.  Esse código gerado é então compilado para criar o scanner executável.

### 🏁 Conclusão
A Análise Léxica é a fundação do processo de compilação, responsável por traduzir um fluxo de texto desestruturado em uma sequência organizada de tokens lógicos. Ao aplicar a teoria de Expressões Regulares e Autômatos Finitos, muitas vezes de forma automatizada com geradores como o Flex, é possível construir a primeira e crucial etapa para que um computador possa "entender" um programa.

### 🗑️ Tópicos não aprofundados
* A sintaxe completa e os metacaracteres das expressões regulares.
* Diagramas de transição detalhados para diferentes autômatos.
* Exemplos de código em linguagem `lex`.
* A diferença entre autômatos finitos determinísticos e não-determinísticos.
* Referências e links para vídeos externos.
