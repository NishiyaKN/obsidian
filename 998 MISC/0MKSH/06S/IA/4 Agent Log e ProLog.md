### 📜 Visão Geral
Os **Agentes Lógicos** são uma abordagem fundamental da **IA Simbólica**, onde a inteligência emerge da manipulação de símbolos e regras lógicas, em contraste com a abordagem conexionista que aprende padrões a partir de dados (como as redes neurais). Um agente lógico utiliza uma base de conhecimento para representar o mundo e um mecanismo de inferência para raciocinar sobre ele. Este resumo explora a definição desses agentes e utiliza a linguagem de programação **Prolog** como um exemplo prático de seu funcionamento.

---

### 🧠 O que é um Agente Lógico?
Um agente lógico é um sistema que toma decisões com base no raciocínio lógico formal. Seu comportamento é guiado por dois componentes principais:

1.  **Base de Conhecimento (Knowledge Base - KB)**: Um conjunto de sentenças e regras, escritas em uma linguagem formal, que representam o conhecimento do agente sobre o ambiente. É o que o agente "sabe".
2.  **Mecanismo de Inferência**: O "motor de raciocínio" do agente. Ele utiliza as informações da base de conhecimento para deduzir novas informações e conclusões que não estavam explicitamente declaradas.

O ciclo de operação de um agente lógico é: perceber o ambiente, atualizar sua base de conhecimento com novas informações, inferir a melhor ação a ser tomada e, por fim, atuar.

---

### 🤖 Programação em Lógica com Prolog
**Prolog (Programming in Logic)** é uma linguagem de programação declarativa que serve como uma excelente ferramenta para construir agentes lógicos. Em vez de escrever uma sequência de comandos (como em linguagens imperativas), em Prolog o programador define um mundo através de fatos e regras.

| Componente 💡 | Função | Sintaxe de Exemplo |
| :--- | :--- | :--- |
| **Fato** | Uma declaração que é considerada incondicionalmente verdadeira na base de conhecimento. | `homem(michel).` |
| **Regra** | Uma declaração cuja veracidade depende de outras condições. A cabeça da regra é verdadeira **se** o corpo da regra for verdadeiro. | `genitor(X, Y) :- pai(X, Y).` |
| **Pergunta** | Uma consulta feita à base de conhecimento. O Prolog tenta provar que a consulta é verdadeira, encontrando valores para as variáveis que satisfaçam as condições. | `?- homem(X).` |

---

### ⚙️ Raciocínio com Prolog: Um Exemplo Prático
Vamos construir uma pequena base de conhecimento familiar para entender como os componentes interagem.

**1. Definindo os Fatos:**
Primeiro, declaramos o que sabemos ser verdade.
^^^prolog
% Fatos sobre quem são os pais e mães.
mulher(jane).
homem(michel).
homem(andre).
pai(michel, andre). % Michel é pai de Andre.
mae(jane, michel).  % Jane é mãe de Michel.
^^^

**2. Definindo as Regras:**
Agora, criamos regras para inferir relações mais complexas. Usamos `,` para "E" e `;` para "OU".
^^^prolog
% Regra 1: X é genitor de Y se X for a mãe OU o pai de Y.
genitor(X, Y) :- mae(X, Y); pai(X, Y).

% Regra 2 (Recursiva): X é ancestral de Y se X for genitor de Y,
% OU se X for genitor de alguém (Z) que é ancestral de Y.
ancestral(X, Y) :- genitor(X, Y).
ancestral(X, Y) :- genitor(X, Z), ancestral(Z, Y).
^^^

**3. Fazendo Perguntas (Inferência):**
Com a base de conhecimento pronta, podemos fazer perguntas e o Prolog usará a inferência para respondê-las.
^^^prolog
% Pergunta 1: Quem são os genitores de Andre?
?- genitor(X, andre).
X = michel.

% Pergunta 2: Jane é ancestral de Andre?
?- ancestral(jane, andre).
true.
^^^

### 🏁 Conclusão
Agentes Lógicos representam a abordagem "top-down" da IA, onde o conhecimento humano é explicitamente codificado em fatos e regras. Linguagens como Prolog demonstram o poder desse paradigma, permitindo que sistemas raciocinem de forma lógica e expliquem suas conclusões. Embora diferente da abordagem conexionista (redes neurais), a IA simbólica continua sendo fundamental para sistemas especialistas, verificação formal e outras áreas onde a transparência do raciocínio é crucial.

### 🗑️ Tópicos não aprofundados
* O quiz inicial e as respostas.
* Os múltiplos exercícios práticos em Prolog (pizzaria, livraria, doação de sangue, etc.).
* Detalhes sobre o Problema da Mochila (Knapsack Problem).
* Instruções de instalação do SWI-Prolog.
* Referências e links para vídeos externos.