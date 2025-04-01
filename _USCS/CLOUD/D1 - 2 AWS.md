## 🚀 Visão Geral da AWS (Amazon Web Services)  

### 📌 História e Contexto  
- **2006**: Lançamento da AWS, originada da infraestrutura interna da Amazon.  
- **2024**: Receita de **US$ 27.5 bilhões** (crescimento de 19% no trimestre).  
- **Infraestrutura global**: 34 regiões geográficas, múltiplas Zonas de Disponibilidade (AZs) por região.  

---

## 🌍 Arquitetura Global AWS  

### 🔹 Regiões e Zonas de Disponibilidade  
- **Regiões**: Áreas geográficas isoladas (ex: `us-east-1` - N. Virginia).  
- **AZs**: Data centers independentes dentro de uma região (redundância de energia/rede).  
  - Distância entre AZs: Até 100 km (evita falhas correlacionadas).  

### 📊 Exemplo de Regiões  
| Região          | Código       | AZs |  
|-----------------|-------------|-----|  
| Norte da Virgínia | `us-east-1` | 6   |  
| São Paulo        | `sa-east-1` | 3   |  
| Frankfurt        | `eu-central-1` | 3 |  

---

## 💡 Modelos de Serviços AWS  

### 1. **IaaS (EC2, S3, VPC)**  
- **Controle**: SO, redes, armazenamento.  
- **Exemplos**:  
  - **EC2**: Máquinas virtuais sob demanda.  
  - **S3**: Armazenamento de objetos escalável.  

### 2. **PaaS (Elastic Beanstalk, Lambda)**  
- **Foco**: Implantação de aplicações sem gerenciar infraestrutura.  
- **Serverless**: AWS Lambda (execução por evento).  

### 3. **SaaS (Chime, WorkSpaces)**  
- **Pronto para uso**: Ferramentas de produtividade (ex: Amazon Chime para videoconferência).  

---

## 💰 Modelos de Precificação AWS  

| Modelo          | Descrição                                  | Exemplo                          |  
|----------------|-------------------------------------------|----------------------------------|  
| **Pay-as-you-go** | Cobrança por uso (segundos/horas).        | EC2: US$0.0116/hora (t2.micro)  |  
| **Savings Plans** | Descontos por compromisso de uso (1/3 anos). | Economia de até 72% vs. sob demanda. |  
| **Free Tier**   | 12 meses gratuitos para serviços selecionados. | 750h/mês de EC2 t2.micro.       |  

### ⚠️ Cuidados com o Free Tier  
- Limites mensais (ex: 5GB no S3).  
- Cobrança automática ao exceder limites.  

---

## 🛠️ Criando uma Instância EC2 (Passo a Passo)  

### 1. **Selecionar AMI**  
- **Ubuntu Server 24.04 LTS** (AMI: `ami-0e2c8caadb5378d8c`).  

### 2. **Escolher Tipo de Instância**  
- **t2.micro** (1 vCPU, 1GB RAM - Free Tier elegível).  

### 3. **Configurar Security Group**  
- **Regras recomendadas**:  
  - SSH (porta 22) → Restrito ao seu IP (`189.54.16.248/32`).  
  - HTTP (80) e HTTPS (443) → Liberados para `0.0.0.0/0` (apenas se necessário).  

### 4. **Armazenamento**  
- **Volume root**: 8GB gp3 (incluído no Free Tier).  

### 5. **Key Pair**  
- Criar novo par de chaves (.pem) para acesso SSH.  

---

## 🔍 Dicas de Otimização  
- **Monitorar custos**: Usar **AWS Cost Explorer** para evitar surpresas.  
- **Escalabilidade**: Utilizar **Auto Scaling Groups** para ajustar capacidade automaticamente.  
- **Segurança**: Habilitar **MFA** no login e revisar permissões IAM.  

---

## 📚 Tópicos Relacionados no Obsidian  
- [[AWS EC2 vs Lambda]]  
- [[Comparativo AWS x Azure x GCP]]  
- [[Gestão de Custos na AWS]]  