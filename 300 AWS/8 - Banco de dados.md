## 8.1 - Amazon RDS
- Serviço gerenciado
- Banco de dados relacional
- Tarefas administrativas são automatizadas
- Cliente foca apenas na otimização do app
- Backup automático
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
## 8.2 -  DynamoDB
- Não relacional (chave-valor)
- Baixa latência (<10ms)
- Serviço gerenciado
- Armazenamento praticamente ilimitado
- Executado exclusivamente em SSDs
- Alta escalabilidade de throughtput de armazenamento
- Pode configurar replicação automática entre diferentes regiões (global tables)
### Componentes principais e particionamento
- Tabela: coleção de dados
- itens: grupo de atributos identificável e exclusível
- Atributo: elemento de dados
- Chaves primárias: 
	- chave de partição: 
		- atributo único que identifica cada item
		- todos os itens com o mesmo valor de chave de partição são armazenados juntos
	- chave primária composta (chave de partição e chave de classificação)
		- funciona da mesma forma anterior (partição)
		- pode ordernar itens que possuem o mesmo valor de chave de partição dentro da partição
		- basicamente uma forma de especificar uma ordem a partir da chave de partição
		- chave de classificação é basicamente uma chave secundária
- Usa `scan` para 
	- encontrar um item por meio de um atirbuto diferente da primary key
- Usa `query` para:
	- consultar tabela usando chave de partição
	- consultar todos os índices secundários de uma tabela
	- recuperar itens de uma tabela ou índice secundário com eficiência
## 8.3 - Amazon Redshift
- Data warehouse
- Serviço gerenciado
- Usa SQL e ferramentas BI
- Usado para análise de Big Data (petabytes de dados estruturados)
- Processamento massivo de dados paralelos
- Possui um nó líder que gerencia a comunicação com programas e nós de computação
- Paga pelo que usar
- Fácil de automatizar e dimensionar, compatibilidade com SQL, JDBC, ODBC, ferramentas BI, etc
## 8.4 - Amazon Aurora
- BD relacional
- Compatível com MySQL e PostgreSQL
- Serviço gerenciado (pelo RDS)
- Paga pelo que usar
- Destaque para sua alta disponibilidade
	- armazena cópias dos dados em várias AZ com backups contínuos
	- até 15 réplicas de leitura
	- reinicialização de um BD com falha em menos de 60s
