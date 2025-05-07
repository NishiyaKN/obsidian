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
### Funcionamento de um load balancer
- Configura para aceitar tráfego de entrada especificando um ou mais listeners
	- processo que verifica se há solicitações de conexão
	- configurada com um protocolo e porta
- Pode configurar para fazer verificação de integridade
	- se ver que um destino não está íntegro, interrompe o roteamento para o mesmo
	- se ver que ele está ok, retorna a rotear