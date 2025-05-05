## 8.1 - RDS
- Serviço gerenciado
- Banco de dados relacional
- Tarefas administrativas são automatizadas
- Cliente foca apenas na otimização do app
### Instância de banco de dados
- Ambiente que pode conter vários BDs
- Tipo uma instância EC2, mas específico para BD e com gerenciamento embutido
- Normalmente é isolada em uma sub-rede privada
- Suporte a MySQL, Aurora, SQL Server, PostgreSQL, MariaDB e Oracle
### Implantação Multi-AZ
- Se for configurada, gera automaticamente uma cópia em espera da instância de BD em outra AZ dentro da mesma VPC
- Transações são aplicadas de forma síncrona para a cópia em espera
- Em caso de falha no BD principal, a cópia em espera assume sua posição
### Réplica de letitura
- Cópia somente de leitura da instância de BD
- Atualizações no BD main são copiadas de forma assíncrona para a réplica
- Reduz a carga na instância main, direcionando as consultas de leitura para a réplica
- Pode estar em uma região diferente do BD main
### Cobrança de instância, armazenamento, etc
- Sob demanda
- Reservada (1 a 3 anos)

- Armazenamento gratuito para backup de instâncias ativas. 
	- para backups de instâncias não ativas, é cobrado por mês
	
- Implantação em 1 AZ mais barato que 2 ou 3 AZ

- Entrada de dados é gratis
- Saída de dados é cobrado
## DynamoDB
- Não relacional (NoSQL)
- Baixa latência (<10ms)
- Serviço gerenciado
- Armazenamento praticamente ilimitado