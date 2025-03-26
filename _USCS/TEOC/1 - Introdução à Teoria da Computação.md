1. Conceitos Fundamentais
	- Computação: Processo de transformar entradas em saídas seguindo regras definidas (algoritmos).
	- Algoritmo: Sequência finita de instruções para resolver um problema.
	- Computabilidade: Estuda o que pode ou não ser resolvido computacionalmente.
	- Decidibilidade: Determina se um problema pode ser resolvido por um algoritmo que sempre retorna uma resposta correta em tempo finito.

2. Formalismo Matemático
    - Objetivo: Descrever conceitos computacionais com precisão, evitando ambiguidades e permitindo provas matemáticas.
    - Estruturas Utilizadas:
        - Conjuntos: Definir alfabetos e linguagens (ex.: Σ={a,b,c}Σ={a,b,c}).
        - Funções e Relações: Modelar transformações (ex.: f(x)=2xf(x)=2x).
        - Lógica Matemática: Base para circuitos e linguagens formais (ex.: P∨QP∨Q).
        - Autômatos e Modelos Computacionais: Máquinas abstratas para processar informações.

3. Modelos de Computação
    - Modelos Clássicos:
        - Autômatos Finitos (AFD):
            - Reconhecem linguagens regulares.
            - Definição: M=(Q,Σ,δ,q0,F)M=(Q,Σ,δ,q0​,F).
            - Aplicações: Análise léxica, reconhecimento de padrões.
        - Autômatos com Pilha (PDA):
            - Reconhecem linguagens livres de contexto.
            - Definição: M=(Q,Σ,Γ,δ,q0,F)M=(Q,Σ,Γ,δ,q0​,F).
            - Aplicações: Análise sintática em compiladores.
        - Máquina de Turing:
            - Modelo mais poderoso, define computabilidade.
            - Definição: M=(Q,Σ,Γ,δ,q0,qaceita,qrejeita)M=(Q,Σ,Γ,δ,q0​,qaceita​,qrejeita​).
            - Aplicações: Problemas indecidíveis (ex.: problema da parada).
        - Máquina RAM:
            - Abstração de computadores reais, usada para análise de complexidade.
			
    - Modelos Alternativos:
        - Lambda Cálculo: Baseado em funções matemáticas (ex.: linguagens funcionais como Haskell).
        - Computação Quântica: Utiliza qubits para resolver problemas complexos (ex.: Algoritmo de Shor).

4. Relação entre Computação e Matemática
    - A matemática fornece a base para a computação teórica:
        - Teoria dos Números: Criptografia.
        - Álgebra Booleana: Circuitos digitais.
        - Teoria dos Conjuntos: Linguagens formais.
        - Teoria da Complexidade: Classificação de problemas (P, NP, NP-completo).

5. Aplicações do Formalismo Matemático
    - Compiladores: Gramáticas formais e autômatos para análise sintática.
    - Algoritmos: Funções para descrever tempo de execução.
    - Criptografia: Problemas matemáticos difíceis (ex.: fatoração de primos).

6. Histórico
    - Década de 1930: Máquina de Turing (Alan Turing), Lambda Cálculo (Alonzo Church), Teorema da Incompletude (Gödel).
    - Década de 1950-1960: Autômatos finitos, arquitetura de von Neumann.
    - Década de 1970: Teoria da Complexidade (P, NP), criptografia moderna.

