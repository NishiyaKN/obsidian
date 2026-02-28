### 📝 Visão Geral
O tratamento de erros é uma função essencial de um compilador robusto. Além de traduzir o código-fonte, o compilador deve ser capaz de detectar quando o código viola as regras da linguagem, reportar os problemas de forma clara ao programador e, idealmente, se recuperar para continuar a análise, encontrando múltiplos erros em uma única compilação. Este resumo aborda os principais tipos de erros e as quatro estratégias de recuperação mais comuns.

### ⚙️ Tipos de Erros em Compilação
Os erros são classificados de acordo com a fase da compilação em que são detectados.

| Tipo de Erro | Descrição | Exemplo |
| :--- | :--- | :--- |
| **Léxico** | Ocorre quando a entrada contém uma sequência de caracteres que não forma um token válido para a linguagem. | `int 2variavel;` (Identificadores não podem começar com números). |
| **Sintático** | Acontece quando a sequência de tokens viola as regras gramaticais da linguagem (a "sintaxe"). | `if (x > 0 { y = 1; }` (Falta do parêntese de fechamento `)`). |
| **Semântico** | O código é sintaticamente válido, mas não faz sentido "semanticamente", geralmente por problemas de tipo ou escopo. | `x = "texto" + 10;` (Operação de soma entre tipos incompatíveis: string e inteiro). |
| **Lógico** | O código é válido em todas as fases da compilação, mas produz um resultado incorreto ou inesperado em tempo de execução. | `media = soma / 0;` (Divisão por zero, um erro que o compilador não detecta). |

### 🛠️ Estratégias de Recuperação de Erros
O objetivo da recuperação é permitir que o compilador continue a análise após encontrar um erro, em vez de parar completamente.

| Estratégia | Descrição | Vantagens | Desvantagens |
| :--- | :--- | :--- | :--- |
| **Modo Pânico (Panic Mode)** | Ao detectar um erro, o parser descarta tokens da entrada até encontrar um "delimitador seguro" (como `;` ou `}`). É a técnica mais comum. | Simples e rápido de implementar. Evita uma cascata de mensagens de erro confusas. | Pode descartar muito código válido, levando a erros falsos subsequentes (ex: uma variável declarada em uma linha descartada é reportada como "não declarada"). |
| **Inserção/Deleção** | O parser faz pequenas correções locais no fluxo de tokens, como inserir um `;` ausente ou remover um `;;` extra. | Consegue lidar com erros simples sem descartar código, mantendo o contexto da análise. | Pode interpretar a intenção do programador de forma errada, gerando uma correção que não resolve o problema real. |
| **Produções de Erro** | O projetista da linguagem adiciona regras gramaticais extras que reconhecem explicitamente erros comuns (ex: um `if` sem a condição entre parênteses). | Permite gerar mensagens de erro extremamente claras e específicas para erros previstos. | Aumenta a complexidade da gramática e exige um esforço prévio para antecipar os erros mais comuns dos programadores. |
| **Correção Global** | Abordagem mais complexa que tenta encontrar o número mínimo de edições (inserções, deleções, substituições) para transformar o código incorreto em um programa válido. | Oferece a melhor experiência ao usuário, preservando o máximo de código e sugerindo múltiplas correções. | Muito complexa de implementar e possui um alto custo computacional, sendo inviável para compiladores em tempo real. |

### 📢 Boas Práticas para Mensagens de Erro
A qualidade das mensagens de erro impacta diretamente a produtividade do desenvolvedor. Boas mensagens devem:
- Ser claras, específicas e consistentes.
- Indicar a linha e a coluna exatas do erro.
- Evitar uma "tempestade de erros" (muitas mensagens causadas por um único erro inicial).
- Se possível, sugerir uma ou mais formas de corrigir o problema.

### 🏁 Conclusão
Um tratamento de erros eficaz é o que diferencia um compilador mediano de um excelente. A escolha da estratégia de recuperação envolve um balanço entre simplicidade de implementação, desempenho e a qualidade do feedback fornecido ao programador. Compiladores modernos frequentemente combinam múltiplas técnicas, como usar o Modo Pânico como estratégia geral e Produções de Erro para tratar os equívocos mais frequentes.

### 📋 Tópicos não aprofundados
- **Detalhes de Implementação do Parser:** O processo interno de como um parser (como YACC/Bison) utiliza a pilha para desempilhar estados e lidar com produções de erro.
- **Exemplos de Código Detalhados:** Os trechos de código específicos usados na apresentação para cada tipo de erro ou recuperação foram resumidos nas tabelas, não reproduzidos integralmente.
- **Discussões e Perguntas:** A seção de perguntas e respostas da aula foi omitida.
