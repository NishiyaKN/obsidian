### 1.1 - Introdução à computação em nuvem
- Computação em nuvem: entrega **sob demanda** de poder computacional, banco de dados, aplicativos, etc. via **Internet**
- Infraestrutura como **software** e não hardware
- Modelos de serviços em nuvem:
	- **IaaS** - Acesso virtual ou físico aos recursos de rede e computadores, alto nível de **flexibilidade** e **controle**
	- **PaaS** - Não precisa gerenciar o hardware, apenas os **aplicativos**
	- **Saas** - Produto completo para end user, **aplicativo**. Nenhum gerenciamento necessário.
- Modelos de implantação em nuvem:
	- **Nuvem** - **Completamente** implantado e executado em nuvem
	- **Híbrida** - **Conecta** infra e recursos da nuvem com o que não está na nuvem (infra local)
	- No **local** - Nuvem privada, oferece recursos dedicados, usa infra tradicional mas com tecnologias de **gerenciamento e virtualização** para melhorar a utilização de recursos.

### 1.2 - Vantagens da computação em nuvem
- Troca de **despesas de capital** (capex, usado para ativos físicos de uma empresa), por **despesa variável** (pagar pelo que usar)
- **Economia de escala** (quanto mais gente usar, mais barato fica para todos)
- Capacidade computacional **flexível** (não precisa ter equipamentos underused ou overused)

### 1.3 - Introdução à Amazon Web Services
- Serviço web é um software disponibilizado pela **Internet** que usa um **formato padronizado** (JSON, XML, etc.) para solicitação e resposta de uma **API**
- AWS - plataforma de nuvem cheio de serviços web
- Serviços da AWS:
	- EC2 - controle total sobre os recursos de computação
	- Lambda - executa código sem precisar de servidores
	- Elastic Beanstalk - gerenciamento de aplicativos web
	- Lightsail - plataforma em nuvem leve para um web app simples
	- Batch - executa centenas de milhares de cargas de trabalho em batch
	- Outposts - executa infra AWS no datacenter local
	- ECS, EKS, Fargate - arquitetura de microsserviços ou contêineres.
	- VMware Cloud - virtualização de servidor local que deseja migrar para a AWS
- Formas de interagir com a AWS por meio de **APIs** (semelhantes a **REST**):
	- Console de Gerenciamento (GUI)
	- CLI
	- SDK (acessa serviços com código Java, Python, etc.)

### 1.4 - AWS Cloud Adoption Framework (AWS CAF)
- Orientação e melhores práticas para organizações adotarem a nuvem
- Organizado em seis perspectivas:
	- Focadas em recursos empresarias:
		- Negócios - garantir que a TI esteja alinhada com as necessidades empresariais
		- Pessoas - priorização do treinamento, a equipe e mudanças organizacionais
		- Governança - alinhar estratégia e metas de TI com estratégia e metas empresariais
	- Focadas em recursos técnicos:
		- Plataforma - descrever a arquitetura do ambiente de estado de destino
		- Segurança - estruturar a implantação de controles de segurança
		- Operações - definem atividades e identificam alterações e treinamentos necessário para implementar a nuvem
