### RISC e CISC
Foco maior do RISC V é permitir que vários produtores de CPU usem o RISC V de modo livre, pra smartphone, tables, serers, notebook, desktop, etc. (alta escalabilidade)

CISC tem instruções complexas, desempenho vem pelo multiprocessamento possível por microcódigo. Flexibidade que otimiza o código e redução do tempo de execução. Uma instrução de cada vez.

Dependendo da necessidade da empresa, deve escolher o RISC ou CISC.
- Operações financeiras, débito e crédito, geração de nota fiscal, dá pra usar RISC.
- Aplicações complexas, empresas de engenharia, melhor optar por CISC.

CISC começou em 1960 com IBM, x86 surgiu no final da década de 70 para computadores pessoais.
x86-64 em 2003 (AMD64) é uma extensão da arquitetura x86, trouxe suporte para 64bits.

Chipset é o planejamento de toda a arquitetura de um computador. É lá onde se define o tipo de processador que irá utilizar. 

Exemplos de CISC
- Motorola 68000
- VAX - usado por mainframes e minicomputador (servidor de médio porte)
- SPARC - para servers e workstation Unix

### Microprogramação
- Otimizado para arquitetura CISC
- Pipeline é possível pela microprogramação
- Multiprocessamento: possibilidade de usar um hardware mais simples para executar diversas instruções reduzidas (micro instruções) de forma concorrente.

Exemplo: Para executar uma determinada instrução multiprocessada
- soma y vezes o valor de x
- microprograma é previamente desenvolvido pelo fabricante e armazenado em uma ROM do processador

- Com o surgimento da microprogramação foi inserido um nível intermediário entre a linguagem de máquina (baixo) e o nível de hardware (alto), este nível é denominado firmware, constituído pelo microprgrama. *No chipset faz o planejamento do firmware, e nele é possível fazer a implementação de ambas as arquiteturas de RICS e CISC.*
- É como se tivesse uma micro-CPU dentro do CPU: precisa de uma UC para controlar as microinstruções, um microcontador de instruções, um microrrregistrador de instrução.

![[Pasted image 20241020193617.png]]
[Memória de Controle (Unidade de controle) - executa ou controla a execução da instrução de máquina, associada ao CP (ajuda no endereçamento da próxima instrução). ]

Microprogramação tem dois tipos de microinstruções:
- Horizontais: (mais caro e mais rápido)
    - tem estrutura do RISC, pois o conceito é de instruções reduzidas: divisão da instrução em microinstruções lineares
    - cada bit da microinstrução tem uma função específica
    - controla uma linha do barramento de controle
    - permite condição de desvio se for necessário
    - pra ser executada precisa de duas funcionalidades:
        - ativar a linha de controle (vai ter um bit que é 1 indica que a microoperação é realizada)
        - avaliar os bits de condição, executar a partir da necessidade de desvio. Se todos os bits for 0, executa a próxima microinstrução, se um dos bits de condição for igual a 1 é executada em seguida a microinstrução

- Verticais: (mais barato e menos rápido)
    - reduz o custo/complexidade da micro UC, memória passa a ser menor, reduz os bits das microinstruções, mas há maior quantidade de microinstruções.
    - pequena perda de tempo por causa de decodificação desse grande número de microinstruções
    - tem estrutura do CISC - instruções complexas com multiprocessamento, decodificação das diferentes microinstruções
    - simplifica a microinstrução, não há necessidade de quebrar em linhas verticais cada instrução

_
- Misto:

- não será totalmente horizontal com a maior quantidade possível de bits
- nem totalmente vertical com a codificação de todos os campos

- reduz a quantidade de bits em relação ao formato horizontal
- reduz o custo da memória de controle
- não introduz acentuada perda de tempo em decodificação

2) **Analisar as características e as vantagens da arquitetura RISC V, para melhoria do desempenho de um computador/servidor.**  
A arquitetura RISC-V segue o princípio RISC, utilizando um conjunto de instruções reduzidas e simplificadas, o que possibilita que elas sejam executadas em menos ciclos de clock, tornando a execução de cada instrução mais rápida e eficiente. Essa arquitetura permite a otimização de pipelines para executar várias instruções simultaneamente. Além disso, ela é modular e flexível, fato que permite que sua implementação seja customizada de acordo com as necessidades específicas de cada aplicação.

3) **Analisar as características e as vantagens da integração da arquitetura CISC, com a microprogramação.**
A arquitetura CISC possui um conjunto de instruções maior e mais complexo, com várias instruções que podem executar tarefas complexas em uma única linha de código. Essas instruções normalmente exigem mais ciclos de clock para serem executadas, e para isso podemos utilizar a microprogramação, que consiste em decompor cada instrução em um sequência de microinstruções armazenadas em uma ROM do processador. Com isso, a microprogramação permite que insturções complexas sejam implementadas de forma mais simples no hardware, e permite também o uso de pipeline e multiprocessamento.

4) **Analisar uma aplicação prática da microprogramação, conforme apresentado em sala de aula.**
A microprogramação serve como um nível intermediário entre a linguagem de alto nível e a linguagem de baixo nível, sendo denomidado de firmware. Ele funciona como se tivesse uma micro CPU dentro da CPU, com uma memória não volátil para armazenar as microinstruções, um microcontador de instruções para armazenar o endereço da próxima microinstrução e microrregistrador de instrução para armazenar a microinstrução atual. Podemos observar essas características em processadores x86 da Intel e AMD por exemplo.

5) **Analisar as características e diferenças entre a microinstrução horizontal e a microinstrução vertical.**
Microinstrução horizontal: cada bit da microinstrução controla diretamente uma parte específica do hardware (registradores, barramentos, ALU), permitindo que várias partes do processador sejam controladas simultaneamente, fornecendo maior controle do hardware e mais operações em paralelo. O tamanho das microinstruções tendem a ocupar mais espaço na memória de controle, mas possui maior eficiência e personalização das operações.

Microinstrução vertical: usa códigos compactos para controlar grupos de sinais ao invés de cada sinal separadamente, tendo um número menor de bits para controlar o hardware por meio de um decodificador, que converte o código em sinais de controle específicos. O tamanho das microinstruções é menor, mas o processo de conficação e decodificação reduz o paralelismo de execução e permite menor controle sobre o hardware.
![[Pasted image 20240928092118.png]]

6) **Analisar as vantagens da microinstrução em projeto misto, integrando a microinstrução horizontal e a microinstrução vertical. Considerar a utilização conjunta das arquiteturas RISC e CISC.**
Ao utilizar uma mistura de microinstrução horizontal e vertical, teremos a redução da quantidade de bits em relação ao formato horizontal, redução do custo da memória de controle, menor perda de tempo em decodificação em relação ao formato vertical e controle granular para certos hardwares. Pode-se utilizar o formato horizontal para operações de alta performance que necessitam de paralelismo e o formato vertical para instruções menos exigentes que necessitam de menos memória.

Pode-se utilizar as arquiteturas RISC e CISC em um mesmo projeto a partir do planejamento do firmware no chipset, pois é a partir dele que se define a implementação de ambas as arquiteturas. Com isso, será possível flexibilizar o uso das arquiteturas para que cada tipo de instrução seja executada pela arquitetura que melhor otimiza seu processamento, como utilizar o RISC para operação que necessitam de alto desempenho e CISC para tarefas mais complexas.