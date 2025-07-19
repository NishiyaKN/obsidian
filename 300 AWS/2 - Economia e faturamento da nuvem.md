### 2.1 - Fundamentos da definição de preço
- Três fatores fundamentais de custo com a AWS:
	- **Computação**: cobrado por hora ou segundo (varia por tipo de instância)
	- **Armazenamento**: cobrado normalmente por GB
	- **Transferência** **de** **dados**: **entrada** e transferência de dados **entre serviços dentro da mesma região AWS** normalmente **não** é cobrada, saída é agregada e **cobrada** por GB
- Modelos de preço por tipo de consumo:
	- Pagamento conforme o uso
	- Pague menos ao fazer reserva
		- Instância Reservada (IR): economiza até 75% 
			- **AURI**: All up front RI
			- **PURI**: Partial up front RI
			- **NURI** No up front RI
	- Pague menos quando usar mais
		- Exemplos: S3, EBS, EFS. Quanto mais GBs usar, menos você paga por GB
	- Pague menos com o crescimento da AWS
- Preços personalizados
###### Serviços sem custo
- **VPC** (Virtual Private Cloud) - provisiona uma seção da nuvem isolada logicamente na qual é possível executar recursos da AWS em uma rede virtual que você mesmo define
- **IAM** (Identity and Access Management) - controla o acesso dos usuário aos serviços e recursos da AWS
- **Elastic** **Beanstalk** - implantar e gerenciar aplicativos na nuvem
- **Cloud** **Formation** - oferece aos desenvolvedores e administradores de sistemas uma maneira fácil de criar um grupo de recursos da AWS relacionados e fornecê-los de uma forma organizada e previsível
- **OpsWorks** - serviço de gerenciamento de aplicativos que facilita a implantação e operação de aplicativos de todos os tipos e tamanhos
### 2.2 Custo total de propriedade
- **TCO** - estimativa financeira para ajudar a identificar custos diretos e indiretos de um sistema
	- comparar os custos da execução de um ambiente de infraestrutura inteiro para uma carga de trabalho específica on-premises em comparação com a AWS
	- criar orçamento e um caso de negócios para migrar para a nuvem
- **Calculadora de preço da AWS**
	- estima custos mensais
	- modela soluções antes de criá-las
		- consegue criar uma estimativa para o custo do caso de uso

### 2.3 AWS Organizations
- Serviço de gerenciamento de contas, onde várias contas podem fazer parte de u ma organização.
	- Políticas de acesso
	- Automatização de criação e gerenciamento de contas AWS
	- Cobrança consolidada
	![[Pasted image 20250311211608.png]]
	- OU (organizational unit) - contêiner para várias contas em uma raiz, podendo conter outras OUs
	- As ramificações consistem em UOs filhas e elas se movem para baixo até terminarem em contas,  que são como as folhas da árvore.
	- Quando você anexa uma política a um dos nós na hierarquia, ela flui para baixo e afeta todas as  ramificações e folhas. 
	- Cada conta pode fazer parte de apenas uma OU
	
- Pode criar políticas de controle de serviço (SCPs) para permitir ou negar acesso a serviços AWS para contas / grupos AWS (até mesmo o usuário raiz)
- Criar  grupos de contas e anexar políticas a um grupo para garantir que as políticas 
- Simplifica o gerenciamento de contas usando APIs para automatizar a criação e o gerenciamento de novas contas da AWS.
##### Políticas do AWS Identity and Access Management (IAM)
- Permite ou nega acesso a serviços, recursos individuais ou ações de API.
- Pode ser aplicada apenas a usuários, grupos ou funções
- Nunca restringe o usuário raiz

### 2.4 AWS Billing and Cost Management
- Serviço usado para pagar a fatura AWS, monitorar seu uso e controlar seus custos.
- Prevê usos e custos futuros
##### Painel de faturamento
Visualizar status das despesas acumuladas no mês
- Spend Summary - gráfico que mostra quanto gastou mês passados, esse mês até agora, e o previsto até final desse mês
- Bills - lista custos do mês passado para cada serviço AWS (por região)
- Cost Explorer - gráfico que mostra o gasto mensal por serviço
- Budgets - criar notificações para quando exceder o orçamento do mês
- Reports - lista o uso de cada categoria de serviço usado por uma conta por hora ou por dia (junto de impostos)

### 2.5 Suporte Técnico
- Technical Accounts Manger (TAM) - oferece orientação, revisão de arquitetura e comunicação contínua
- AWS Trusted Advisor - oferece práticas recomendadas, verifica oportunidades para reduzir despesar e aumentar produtividade.
- Support Concierge - fornece análises sobre problemas de faturamentos e contas (dúvidas não técnicas)
##### Planos de suporte
- Basic - acesso à central de recursos,  painel de status do serviço, perguntas frequentes  sobre produtos, fóruns de discussão e suporte  a verificações de integridade
- Developer - suporte para beta testers AWS ou pra implementar AWS
- Business - clientes que executam cargas de trabalho de produção
- Enterprise - clientes que executam cargas de trabalho comerciais 