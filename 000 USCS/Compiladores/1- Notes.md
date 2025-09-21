## 🔍 Análise Léxica (Scanner)
A Análise Léxica é a primeira fase do compilador, responsável por ler o código-fonte como uma sequência de caracteres e convertê-lo em uma sequência de **tokens**. Os tokens são as unidades léxicas fundamentais da linguagem, como palavras-chave, identificadores e operadores.

* **Função Principal:** Agrupar caracteres em lexemas e classificá-los em tokens.
* **Formalismo:** Utiliza **Expressões Regulares** para definir os padrões dos tokens e **Autômatos Finitos** para reconhecê-los[cite: 4].
* **Símbolos:** Os símbolos terminais de uma gramática correspondem aos tokens[cite: 3].
* **Tratamento de Espaços:** O analisador léxico geralmente ignora espaços em branco, quebras de linha e comentários.
* **Tabela de Símbolos:** Os tokens identificados são organizados e entregues para a tabela de símbolos, que será utilizada pelo analisador sintático[cite: 3].

## 🌳 Análise Sintática (Parser)
Após a análise léxica, a Análise Sintática (ou *parsing*) verifica se a sequência de tokens forma uma estrutura gramaticalmente válida. Ela organiza os tokens de forma hierárquica, geralmente através de uma árvore de derivação, para dar sentido à estrutura do código (ex: definir o que é uma soma, uma declaração de variável, etc.).

* **Função Principal:** Validar a estrutura gramatical e hierarquizar os tokens.
* **Formalismo:** Utiliza um **Autômato de Pilha**, pois ele possui memória para lidar com a natureza aninhada das estruturas de programação[cite: 5].
* **Árvore de Derivação:** Embora a análise resulte em uma estrutura de árvore, uma árvore explícita não é necessariamente construída na memória durante o processo[cite: 6].
* **Interação:** A análise léxica e sintática podem ocorrer de maneira simultânea, embora o processo sempre precise iniciar com a análise léxica[cite: 7].

## 📊 Formalismos e Gramáticas
Existem diferentes formalismos para descrever e reconhecer linguagens, cada um com seu poder e complexidade.

| Formalismo       | Descrição                                                                        | Exemplo de Uso       |
| :--------------- | :------------------------------------------------------------------------------- | :------------------- |
| **Gerador**      | Define as regras para gerar todas as palavras válidas de uma linguagem[cite: 2]. | Gramáticas           |
| **Reconhecedor** | Verifica se uma determinada palavra pertence a uma linguagem[cite: 2].           | Autômatos            |
| **Denotacional** | Fornece uma notação simplificada para descrever uma linguagem[cite: 2].          | Expressões Regulares |

As gramáticas são classificadas em uma hierarquia com base em suas restrições de produção:

| Tipo de Gramática     | Regra de Produção (Esquerda `->` Direita)                                                                                        | Autômato Equivalente |
| :-------------------- | :------------------------------------------------------------------------------------------------------------------------------- | :------------------- |
| **Regular**           | `A -> a` ou `A -> aB`. Lado esquerdo com uma variável, lado direito com no máximo uma variável[cite: 13].                        | Autômato Finito      |
| **Livre de Contexto** | `A -> x`. Lado esquerdo é uma única variável, e o lado direito é livre (qualquer combinação de terminais e variáveis)[cite: 14]. | Autômato de Pilha    |
| **Irrestrita**        | `u -> v`. Sem restrições, exceto que o lado esquerdo não pode ser vazio.                                                         | Máquina de Turing    |

## 🏁 Conclusão
As fases de análise léxica e sintática são a base de um compilador, garantindo que o código-fonte seja válido e estruturado. A análise léxica transforma texto bruto em tokens usando a simplicidade das expressões regulares e autômatos finitos. Em seguida, a análise sintática utiliza o poder dos autômatos de pilha e gramáticas livres de contexto para impor uma ordem hierárquica a esses tokens, preparando o terreno para as fases de semântica e geração de código.

## 🚫 Tópicos não aprofundados
A lista abaixo contém tópicos presentes no material de origem que não foram incluídos ou foram abordados superficialmente neste resumo por serem considerados de menor relevância para o entendimento geral:
* Detalhes sobre a prova e questões específicas mencionadas[cite: 1, 5].
* Funcionamento de geradores de analisadores léxicos como o `lex`[cite: 11].
* Definições detalhadas de operações em linguagens (concatenação, fecho de Kleene, etc.)[cite: 8, 9].
* Uso e significado de metacaracteres específicos em expressões regulares[cite: 10].
* Gramáticas sensíveis ao contexto e a equivalência de autômatos com duas pilhas e Máquinas de Turing[cite: 15].
* Detalhes sobre a implementação de diagramas de transição.
