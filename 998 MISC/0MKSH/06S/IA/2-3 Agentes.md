### 📜 Visão Geral
A abordagem moderna da Inteligência Artificial é centrada no conceito de **Agentes Inteligentes**. Em vez de tentar replicar o pensamento humano de forma abstrata, essa visão foca em projetar entidades autônomas que agem racionalmente para atingir objetivos. Um agente percebe seu ambiente através de sensores e atua sobre ele com atuadores. Este resumo apresenta o framework **PEAS**, usado para projetar agentes, e as principais propriedades que definem a complexidade de seus ambientes de tarefa.

---

### 🤖 O que é um Agente Inteligente?
Um **agente** é qualquer entidade que interage com um **ambiente**. [cite_start]Ele utiliza **sensores** para perceber o estado do ambiente e **atuadores** para executar ações que o modificam. [cite: 4367] [cite_start]A "inteligência" de um agente reside em sua **racionalidade**: a capacidade de escolher a ação que se espera que maximize seu desempenho. [cite: 4401]

* [cite_start]**Racionalidade é medida pelo resultado**: Um agente é avaliado não por seus processos internos, mas pelos resultados de suas ações no ambiente, medidos por uma **métrica de performance**. [cite: 4410, 4421]
* **Exemplos**:
    * [cite_start]**Agente Humano**: Sensores (olhos, ouvidos), Atuadores (mãos, pernas). [cite: 4375, 4376, 4377]
    * [cite_start]**Agente de Software**: Sensores (entradas de teclado, pacotes de rede), Atuadores (exibição na tela, envio de pacotes). [cite: 4378, 4379, 4380]

---

### 📊 O Framework PEAS
Para projetar um agente racional, é essencial definir claramente sua tarefa. O framework **PEAS** organiza essa definição em quatro componentes:

| Componente | Descrição | Exemplo: Táxi Autônomo |
| :--- | :--- | :--- |
| **P**erformance (Desempenho) | Como o sucesso do agente é medido? | Chegar ao destino de forma segura, rápida, barata e confortável. [cite_start]Maximizar o lucro. [cite: 4434, 4435, 4436, 4437] |
| **E**nvironment (Ambiente) | Onde o agente opera? | [cite_start]Ruas, tráfego, pedestres, clima, clientes. [cite: 4427, 4428] |
| **A**ctuators (Atuadores) | Como o agente age no ambiente? | [cite_start]Volante, acelerador, freio, buzina, painel de comunicação. [cite: 4441, 4442, 4443, 4444] |
| **S**ensors (Sensores) | Como o agente percebe o ambiente? | [cite_start]Câmeras, GPS, velocímetro, sensores de proximidade. [cite: 4447, 4448, 4449, 4450, 4451, 4452] |

---

### 🌍 Propriedades do Ambiente de Tarefas
A complexidade e o tipo de algoritmo necessário para um agente dependem crucialmente das propriedades de seu ambiente de trabalho.

| Propriedade 💡 | Tipo A | vs. | Tipo B |
| :--- | :--- | :-: | :--- |
| **Visibilidade** | **Totalmente Observável** <br> (O agente conhece o estado completo do ambiente) | | [cite_start]**Parcialmente Observável** <br> (O agente tem uma visão incompleta) [cite: 4482] |
| **Agentes** | **Agente Único** <br> (Nenhum outro agente interfere) | | [cite_start]**Multiagente** <br> (Múltiplos agentes interagem, de forma cooperativa ou competitiva) [cite: 4483] |
| **Determinismo** | **Determinístico** <br> (O próximo estado é totalmente previsível pela ação atual) | | [cite_start]**Estocástico** <br> (O próximo estado é incerto e envolve aleatoriedade) [cite: 4484] |
| **Episódios** | **Episódico** <br> (A experiência é dividida em episódios independentes) | | [cite_start]**Sequencial** <br> (A ação atual afeta todas as decisões futuras) [cite: 4485] |
| **Dinamismo** | **Estático** <br> (O ambiente não muda enquanto o agente "pensa") | | [cite_start]**Dinâmico** <br> (O ambiente muda com o passar do tempo, independentemente das ações do agente) [cite: 4485] |
| **Continuidade** | **Discreto** <br> (Número finito de estados, percepções e ações distintas) | | [cite_start]**Contínuo** <br> (Estados e ações existem em um espectro contínuo de valores) [cite: 4485] |

Quanto mais o ambiente se inclina para as características da coluna "Tipo B", mais complexo é o design do agente.

### 🏁 Conclusão
O paradigma do agente inteligente fornece uma estrutura concreta para o desenvolvimento de IA. O sucesso de um agente depende de uma definição clara de sua tarefa através do framework **PEAS** e, mais importante, de uma profunda compreensão das propriedades de seu **ambiente**. Ambientes dinâmicos, parcialmente observáveis e estocásticos, como o mundo real, exigem agentes muito mais sofisticados do que aqueles projetados para ambientes simples e estáticos.

### 🗑️ Tópicos não aprofundados
* O quiz inicial com suas respostas.
* Detalhes sobre as tabelas PEAS para outros exemplos (diagnóstico médico, robô de seleção de peças).
* Os exercícios propostos para os alunos.
* Referências e links para vídeos externos.