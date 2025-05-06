## 9.1 - AWS Well-Architected Framework
- É um guia para ajudar a criar uma infraestrutura da nuvem melhor
- Constituído por 6 pilares
### Excelência operacional
- Foco em executar e monitrar sistemas para agregar valor comercial e melhorar processos e procedimentos de suporte
	- Automatização de alterações
	- Resposta a eventos
	- Definir padrões para gerenciar as operações diárias
- Executar operações como código (limita o erro humano)
- Alterações frequentes, pequenas e reversíveis
- Refinar (melhorar) procedimentos operacionais com frequência
- Prever falhas (fazer testes e simulações)
- Aprender com falhas operacionais
### Segurança
- Foco em proteger informações, sistemas e ativos, agregar valor comercial por meio de avaliações de risco e estratégias de mitigação
	- Proteger a confidencialidade e integridade dos dados
	- Identificar e gerenciar quem pode fazer o quê
	- Proteger sistemas
- Implementar uma base de identidade forte (privilégio mínimo e separação de responsabilidades com autorização apropriada) 
- Habilitar a rastreabilidade (monitorar e alertar, executar ações a partir de logs e métricas automaticamente)
- Aplicar segurança em todas as camadas (VPC, sub-rede, instância, SO, app)
- Automatizar práticas recomendadas de segurança
- Proteger dados em trânsito e ocioso
- Manter pessoas longe dos dados (diminuir erro humano)
- Preparar-se para eventos de segurança (simular resposta a incidentes)
### Confiabilidade
- Foco em garantir que uma carga de trabalho execute sua função consistentemente
	- Projeto de sistemas distribuídos
	- Planajamento de recuperação
	- Tratamento de alterações
