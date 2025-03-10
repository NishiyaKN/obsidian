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
- Calculadora de preço da AWS
	- estima custos mensais
	- modela soluções antes de criá-las
	- 