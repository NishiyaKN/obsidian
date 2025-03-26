1. Conjuntos
    - Definição: Coleção bem definida de elementos (ex.: A={1,2,3}A={1,2,3}).
    - Operações Fundamentais:
        - União (A∪BA∪B): Combina elementos de AA e BB.
        - Interseção (A∩BA∩B): Elementos comuns a AA e BB.
        - Diferença (A−BA−B): Elementos de AA não em BB.
        - Complemento (AcAc): Elementos não em AA (relativo a um universo UU).
        - Produto Cartesiano (A×BA×B): Pares ordenados (a,b)(a,b).

2. Relações
    - Definição: Subconjunto do produto cartesiano A×BA×B (ex.: R={(1,a),(2,b)}R={(1,a),(2,b)}).
    - Tipos Especiais:
        - Reflexiva: (a,a)∈R(a,a)∈R para todo a∈Aa∈A.
        - Simétrica: Se (a,b)∈R(a,b)∈R, então (b,a)∈R(b,a)∈R.
        - Transitiva: Se (a,b),(b,c)∈R(a,b),(b,c)∈R, então (a,c)∈R(a,c)∈R.

    - Fechamentos:
        - Reflexivo: Adiciona (a,a)(a,a) para todo a∈Aa∈A.
        - Simétrico: Adiciona (b,a)(b,a) para cada (a,b)∈R(a,b)∈R.
        - Transitivo: Adiciona (a,c)(a,c) se (a,b),(b,c)∈R(a,b),(b,c)∈R.

3. Funções
    - Definição: Relação onde cada elemento de AA mapeia a exatamente um elemento de BB.
    - Tipos:
        - Injetora: Elementos distintos em AA mapeiam para elementos distintos em BB.
        - Sobrejetora: Todo elemento em BB é mapeado por algum elemento em AA.
        - Bijetora: Injetora e sobrejetora (correspondência biunívoca).

4. Indução Matemática
    - Objetivo: Provar propriedades para todos os números naturais.
    - Passos:
        - Base: Verificar para n=0n=0 ou n=1n=1.
        - Indutivo: Assumir válido para n=kn=k e provar para n=k+1n=k+1.
    - Aplicações: Correção de algoritmos recursivos, propriedades de autômatos.

5. Linguagens Formais
    - Alfabeto (ΣΣ): Conjunto finito de símbolos (ex.: Σ={0,1}Σ={0,1}).
    - Cadeia (Σ∗Σ∗): Sequência finita de símbolos (ex.: "0101").
    - Linguagem (LL): Subconjunto de Σ∗Σ∗ (ex.: L={"01","0011"}L={"01","0011"}).
    - Tipos de Linguagens:
        - Regular: Reconhecida por autômatos finitos (ex.: cadeias com número par de '0's).
        - Livre de Contexto: Reconhecida por autômatos com pilha (ex.: 0n1n0n1n).

6. Representação de Linguagens
    - Gramáticas Formais: Regras de produção para gerar cadeias (ex.: S→aS∣bS∣εS→aS∣bS∣ε).
    - Expressões Regulares: Padrões para descrever linguagens regulares (ex.: (0∣1)∗1(0∣1)∗1).
    - Autômatos Finitos: Modelos para reconhecer linguagens:
        - AFD: Transições determinísticas.
        - AFND: Transições não determinísticas.

7. Aplicações na Computação
    - Bancos de Dados: Relações matemáticas entre tabelas.
    - Compiladores: Gramáticas para análise sintática, autômatos para análise léxica.
    - Criptografia: Funções injetoras e bijetoras para mapeamentos seguros.
    - Teoria da Complexidade: Classificação de problemas usando linguagens formais.

8. Conclusão

Conjuntos, relações e linguagens formam a base matemática da computação teórica, sendo essenciais para modelar sistemas, projetar algoritmos e formalizar linguagens de programação. O estudo desses conceitos permite a construção de autômatos, gramáticas e expressões regulares, fundamentais para aplicações práticas como compiladores e reconhecimento de padrões.