### 📝 Visão Geral
Este resumo apresenta o Prolog, uma linguagem de programação fundamentada no paradigma lógico. Em Prolog, um programa é construído como uma base de conhecimento composta por fatos e regras. A interação com o programa ocorre por meio de perguntas (queries), que consultam essa base para obter respostas lógicas.

### 🧱 Componentes de um Programa Prolog
Um programa em Prolog é estruturado em três elementos principais:

| Componente    | Descrição                                                                                                                               | Sintaxe Exemplo             |
| :------------ | :-------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------- |
| **Fatos**     | Informações declaradas como verdadeiras que compõem a base de conhecimento.                                                             | `pai(andre, conrado).`      |
| **Regras**    | Definições que são avaliadas como verdadeiras ou falsas com base nos fatos existentes. A sintaxe de uma regra é `regra(Args) :- corpo`. | `genitor(X,Y) :- pai(X,Y).` |
| **Perguntas** | Forma de interagir e consultar a base de conhecimento.                                                                                  | `?- pai(andre, X).`         |

### ✍️ Sintaxe e Conceitos
A sintaxe do Prolog possui regras específicas para a representação de seus elementos.

* **Nomenclatura:**
    * **Variáveis** sempre começam com letra maiúscula (ex: `X`, `Pessoa`).
    * **Constantes** (átomos) sempre começam com letra minúscula (ex: `andre`, `conrado`).
* **Operadores Lógicos:**
    * A vírgula (`,`) representa o operador lógico **E** (AND).
    * O ponto e vírgula (`;`) representa o operador lógico **OU** (OR).
* **Aridade:** Refere-se ao número de argumentos que um fato ou regra possui. Por exemplo, `casado(joao, maria)` tem aridade 2.
* **Consistência:** A ordem dos argumentos em fatos e regras é crucial e deve ser consistente em toda a base de conhecimento.

### 💡 Exemplo Prático
Abaixo está um exemplo de uma pequena base de conhecimento e como ela pode ser consultada.

^^^prolog
% --- Fatos ---
% pai(Pai, Filho).
pai(andre, conrado).
pai(andre, ana).

% mae(Mae, Filho).
mae(marta, conrado).
mae(marta, ana).

% --- Regras ---
% X é genitor de Y se X é pai de Y OU X é mãe de Y.
genitor(X, Y) :- pai(X, Y); mae(X, Y).

% --- Perguntas e Respostas Esperadas ---
% Pergunta: Quem é o pai de Conrado?
% ?- pai(X, conrado).
% Resposta: X = andre.

% Pergunta: Marta é mãe de quem?
% ?- mae(marta, Y).
% Resposta: Y = conrado; Y = ana.

% Pergunta: Andre é genitor de Ana?
% ?- genitor(andre, ana).
% Resposta: true.
^^^

### 🏁 Conclusão
Prolog implementa uma abordagem declarativa para a programação, onde o foco está em definir "o que" é verdade (fatos e regras) em vez de "como" computar uma solução. A execução de um programa é um processo de dedução lógica, no qual o motor do Prolog busca na base de conhecimento as respostas para as perguntas do usuário. Isso o torna uma ferramenta poderosa para representação de conhecimento, sistemas especialistas e outras aplicações em inteligência artificial.

### 🚫 Tópicos não aprofundados
A lista abaixo contém tópicos que não foram abordados no material de origem, que se concentrou apenas na sintaxe básica:
* O mecanismo de **unificação** (matching) e **backtracking**, que são centrais para a execução do Prolog.
* Uso de **recursão** para definir regras complexas.
* Estruturas de dados, como **listas** e suas manipulações.