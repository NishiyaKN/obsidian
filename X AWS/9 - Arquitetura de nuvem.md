## 9.1 - AWS Well-Architected Framework
- É um guia para ajudar a criar uma infraestrutura da nuvem melhor
- Constituído por 6 pilares
### Excelência operacional
- Foco em executar e monitorar sistemas e melhorar processos e procedimentos de suporte
	- Automatização de alterações
	- Resposta a eventos
	- Definir padrões para gerenciar as operações diárias
- **Executar operações como código** (limita o erro humano)
- **Alterações frequentes, pequenas e reversíveis**
- **Refinar (melhorar) procedimentos operacionais com frequência**
- **Prever falhas** (fazer testes e simulações)
- **Aprender com falhas operacionais**
### Segurança
- Foco em proteger informações, sistemas e ativos, fazer avaliações de risco e estratégias de mitigação
	- Proteger a confidencialidade e integridade dos dados
	- Identificar e gerenciar quem pode fazer o quê
	- Proteger sistemas
- **Implementar uma base de identidade forte** (privilégio mínimo e separação de responsabilidades com autorização apropriada) 
- **Habilitar a rastreabilidade** (monitorar e alertar, executar ações a partir de logs e métricas automaticamente)
- **Aplicar segurança em todas as camadas** (VPC, sub-rede, instância, SO, app)
- **Automatizar práticas recomendadas de segurança**
- **Proteger dados em trânsito e ocioso**
- **Manter pessoas longe dos dados** (diminuir erro humano)
- **Preparar-se para eventos de segurança** (simular resposta a incidentes)
### Confiabilidade
- Foco em garantir que uma carga de trabalho execute sua função consistentemente
	- Projeto de sistemas distribuídos
	- Planajamento de recuperação
	- Tratamento de alterações
- **Recuperar-se automaticamente de falhas** 
- **Testar procedimentos de recuperação**
- **Escale horizontalmente para aumentar a disponibilidade**
- **Gerencie alterações na automação**
### Eficiência de desempenho
- Foco em usar os recursos de forma eficiente, acompanhando a evolução
	- Seleção dos tipos e tamanhos certos de recursos com base na carga de trabalho
	- Monitoramento e desempenho
	- Tomar decisões embasadas para manter a eficiência a medida que as necessidades evoluem
- **Democratize as tecnologias avançadas**: consumir tecnologia como um serviço (não precisa gerenciar e provisionar recursos)
- **Alcance global**: sistemas em várias regions par menor latência
- **Usar arquiteturas serverless**
### Otimização de custos
- Foco em evitar custos desnecessários
	- Compreender e controlar onde o dinheiro está sendo gasto
	- Selecionar o tipo mais apropriado de recurso
	- Analisar gastos ao longo do tempo
	- Scaling para atender às necessidades
- **Implementar o gerenciamento financeiro na nuvem** 
- **Adote um modelo de consumo:** escolher bem os recursos de acordo com os requisitos
- **Analise e atribua despesas:**  atribuir custos de TI a proprietários de cargas de trabalho individuais
### AWS Well-Architected Tool
- Ajuda a analisar o estado das cargas de trabalho
	- compara com as práticas recomendadas
- Para usar:
	- Defina a carga de trabalho
	- Responda diversas perguntas do que foi visto acima
	- Ele oferece um plano de ação para melhorar a carga de trabalho para a nuvem