## 👁️ Visão Geral
Este material explora os paradigmas fundamentais que ditam as regras de interação em Sistemas Distribuídos (SD) e aprofunda-se nos conceitos de confiabilidade e alta disponibilidade. O foco central é demonstrar que não existem soluções perfeitas (sempre há *trade-offs*) e que a engenharia moderna de SD prioriza a recuperação rápida de falhas (resiliência) em vez da tentativa de criar sistemas infalíveis.

## 🧩 Paradigmas em Sistemas Distribuídos
Um paradigma em SD é um modelo de abstração que define como os componentes de software interagem. Ele estabelece as regras para comunicação, sincronização e acoplamento.

* **Trade-offs:** Toda vantagem obtida (ex.: maior velocidade ou escalabilidade) geralmente cobra um preço (ex.: menor consistência ou maior complexidade).
* **Acoplamento (Coupling):** É o grau de dependência entre componentes. 
  * **Espacial:** Forte (conhece IP/Porta) vs Desacoplado (usa tópicos/filas sem saber quem recebe).
  * **Temporal:** Forte/Síncrono (remetente bloqueia aguardando resposta) vs Desacoplado/Assíncrono (envia e continua, destinatário processa depois).
  * *Vantagem do Desacoplamento:* Alta escalabilidade e resiliência.
  * *Desvantagem:* Maior complexidade de infraestrutura e dificuldade de rastreamento de erros.

## 📊 Classificação dos Paradigmas
| Categoria | Tipos / Exemplos | Foco Principal |
| :--- | :--- | :--- |
| **Arquitetura** | Cliente-Servidor, P2P (Peer-to-Peer), Camadas (Layered) | Disposição estrutural dos nós e divisão de responsabilidades. |
| **Comunicação** | RPC (Procedimento Remoto), RMI, MOM (Mensagens) | Como os dados fluem (chamadas síncronas simulando local vs assíncronas). |
| **Organização** | Baseado em Objetos, DFS (Arquivos), Baseado em Documentos (Web/REST) | Como os recursos são abstraídos para o desenvolvedor e usuário. |
| **Coordenação** | Acoplamento Espacial e Temporal | Como os componentes se encontram e sincronizam operações. |

## 🛡️ Confiabilidade e Seus Atributos
Como falhas em rede e hardware são inevitáveis, um SD deve ser projetado para continuar entregando valor mesmo quando partes dele caem.

* **Disponibilidade (Availability):** Prontidão do sistema para uso em um dado momento (os famosos "noves").
* **Confiabilidade (Reliability):** Capacidade de funcionar continuamente sem interrupções por um período.
* **Segurança (Safety):** Garantia de que uma falha não causará danos catastróficos.
* **Manutenibilidade:** Facilidade e velocidade com que um nó falho pode ser reparado ou substituído.

## 🧮 Métricas de Disponibilidade (MTBF e MTTR)
A disponibilidade de um sistema é definida matematicamente pela relação entre o tempo que ele funciona e o tempo que leva para ser consertado.

**Tempo Médio Entre Falhas (MTBF):** Mede a estabilidade. Quanto maior, melhor.
$$MTBF=\frac{\text{Tempo total de operação}}{\text{Número de falhas}}$$

**Tempo Médio para Reparo (MTTR):** Mede a eficiência de recuperação. Quanto menor, melhor.
$$MTTR=\frac{\text{Tempo total de reparo}}{\text{Número de falhas}}$$

**Disponibilidade (A):**
$$A=\frac{MTBF}{MTBF+MTTR}$$

*Dica prática:* É muito mais barato e eficiente focar em reduzir o MTTR através de automação (subir instâncias novas em segundos) do que tentar aumentar o MTBF criando hardwares que nunca quebram.

![[Pasted image 20260329111442.png]]
![[Pasted image 20260329111436.png]]
## Impactos decorrentes da arquitetura

**Degradação em Cascata**: Uma falha pequena em um componente satura os outros, derrubando o sistema inteiro (Thundering Herd Problem).

**Dano à Reputação**: Usuários migram para concorrentes se o serviço se mostra instável.

**Custos de "Incêndio"**: Recuperar um sistema não planejado para HA após uma queda é muito mais caro e demorado do que manter um sistema resiliente.
## 📊 A Tabela dos "Noves" (Disponibilidade)
| Disponibilidade | Downtime Anual Tolerado | Contexto Comum |
| :--- | :--- | :--- |
| **99%** (2 noves) | ~3.65 dias | Sites pequenos, serviços não críticos |
| **99.9%** (3 noves) | ~8.77 horas | E-commerce, provedores SaaS |
| **99.99%** (4 noves) | ~52.56 minutos | Bancos, infraestrutura de nuvem |
| **99.999%** (5 noves) | ~5.26 minutos | Telecom, controle de tráfego aéreo |

## ⚙️ Estratégias para Alta Disponibilidade (HA)
* **Eliminação de SPOF (Single Point of Failure):** Criar redundância para que nenhum servidor ou banco de dados seja o único responsável por uma tarefa.
* **Balanceamento de Carga:** Distribuir o tráfego entre várias instâncias saudáveis.
* **Replicação de Dados:** Manter cópias geográficas para casos de desastres em data centers.
* **Detecção Automática (Self-healing):** Uso de *Health Checks* para identificar falhas e provisionar novos nós automaticamente (ex.: Kubernetes).

## 💡 Conclusão
Projetar um Sistema Distribuído eficiente exige a escolha consciente de paradigmas, aceitando que o desacoplamento traz escalabilidade ao custo de complexidade. No quesito confiabilidade, a arquitetura moderna assume que falhas vão ocorrer e foca em mascará-las do usuário final através de alta redundância, rotinas de *self-healing* e um MTTR drasticamente reduzido.

## ✂️ Tópicos não aprofundados
* **Cálculos Matemáticos Detalhados:** O passo a passo da resolução do problema matemático do servidor que falha 3 vezes em 17 dias (operações aritméticas de conversão de horas e minutos).
* **Cenário de Discussão do Datacenter:** O exercício teórico sobre as 3 camadas de energia (Enel, No-break de 5 min e Gerador Diesel de 1h) e suas desvantagens físicas (poluição, barulho).
* **Impactos de Negócio Específicos:** Detalhamento sobre degradação em cascata (*Thundering Herd Problem*) e custos corporativos de indisponibilidade ("efeito dominó").