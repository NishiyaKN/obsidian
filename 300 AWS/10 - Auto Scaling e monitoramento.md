## 10.1 - ELB
- Serviço que distribui o tráfego de entrada de apps ou rede entre vários destinos
- Consegue escalar automaticamente o load balancer
### Tipos de load balancers
#### Application Load Balancer
- Opera na camada 7 do modelo OSI
- Roteia tráfego de acordo com o conteúdo da solicitação
- Ideal para HTTP e HTTPS
- Suporte a containers e microsserviços
- Utiliza SSL/TLS o tempo todo
#### Network Load Balancer
- Opera na camada 4 OSI
- Roteia tráfego de acordo com os ddos do protocolo IP
- Ideal para tráfego TCP e UDP
- Suporte a milhões de solicitações por segundo, com baixa latência
- Otimizado para lidar com padrões de tráfego súbitos e voláteis
#### Classic Load Balancer
- Implementação antiga
- Opera na camada 4 e 7
- Balanceamento de instância do EC2 apenas
- HTTP, HTTPS, TCP e SSL
### Configuração de um load balancer
- Configura para aceitar tráfego de entrada especificando um ou mais listeners
	- processo que verifica se há solicitações de conexão
	- configurada com um protocolo e porta
- Pode configurar para fazer verificação de integridade
	- se ver que um destino não está íntegro, interrompe o roteamento para o mesmo
	- se ver que ele está ok, retorna a rotear
### Monitoramento do load balancer
- Métricas do Amazon CloudWatch: ELB publica dados no CloudWatch de seus load balancer e destinos.
- Logs de acesso: possibilita verificar detalhes das solicitações feitas ao load balancer (armazenado no S3)
- Logs do AWS CloudTrail: logs de chamadas feitas pela API do ELB (fica no S3)
## 10.2 - Amazon CloudWatch
- Monitora recursos da AWS e apps na AWS
- Coleta métricas
- Envia notificações pelo Amazon SNS
- Executa ações do EC2 Auto Scaling ou EC2
- Define regras que correspondam a eventos de entrada ou alterações no ambiente AWS e os rotear para destinos para processamento
- Paga pelo que usar
## 10.3 - Amazon EC2 Auto Scaling
- Adiona ou remove instâncias EC2 automaticamente
- Detecta instâncias não íntegras e as substitui automaticamente
- Fornece escalabilidade manual, programada, sob demanda (dinâmica) e preditiva
### Grupo de Auto Scaling
- Conjunto de instâncias que são agrupadas logicamente para escalabilidade e gerenciamento automático
- Pode especificar número mínimo, máximo e desejado de instâncias
### Funcionamento do EC2 Auto Scaling
- Especifica uma configuração de execução (o que vai escalar)
	- define as configurações da instância (AMI, tipo, IAM, etc)
- Especificad uma sub-rede dentro de uma VPC (onde vai escalar)
	- integração com o ELB para poder associar um ou mais load balancers a um grupo de Auto Scaling
- Especifica quando o evento de escalabilidade deve ocorrer (quando vai escalar)
	- **Manter os níveis de instãncia atuais em todos os momentos**: verifica apenas a integridade das instâncias
	- **Escalabilidade manual**: define capacidade max, min e desired
	- **Escalabilidade programada**: baseado em data e hora (carga de trabalho previsível)
	- **Escalabilidade sob demanda (dinâmica)**: define parâmetros de condições
	- **Escalabilidade preditiva**: de acordo com a demanda prevista (usa dados do uso real do EC2, machine learning)
### AWS Auto Scaling
- Serviço que monitora os apps
- Ajusta automaticamente a capacidade para manter uma performance estável pelo menor custo
- Cria planos de escalabilidades para
	- EC2
	- ECS
	- DynamoDB
	- Aurora