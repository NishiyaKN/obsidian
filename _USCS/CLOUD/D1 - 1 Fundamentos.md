## ☁️ Fundamentos de Computação em Nuvem  

### 📌 Definição  
- Modelo que oferece recursos computacionais sob demanda (redes, servidores, armazenamento) via internet, com pagamento por uso.  
- **Características-chave**:  
  - Escalabilidade elástica.  
  - Acesso ubíquo (qualquer dispositivo, qualquer lugar).  
  - Autoatendimento via portal/API.  

### 🔍 Origens Históricas  
- **1961**: John McCarthy (Stanford) prevê "computação como utilidade pública".  
- **1969**: Leonard Kleinrock antevê "redes de computadores como utilities".  
- **1999**: Salesforce pioneira em SaaS corporativo.  
- **2006**: AWS lança EC2 e populariza o termo "cloud computing".  

---

## 🏗️ Modelos de Implantação  

### 1. Nuvem Pública  
- **Exemplos**: AWS, Azure, Google Cloud.  
- **Vantagens**:  
  - Custo reduzido (sem infraestrutura própria).  
  - Escalabilidade instantânea.  
- **Desvantagens**:  
  - Dados compartilhados em hardware multitenant.  

### 2. Nuvem Privada  
- **Casos de uso**: Bradesco (financeiro), Petrobras (dados sensíveis).  
- **Vantagens**:  
  - Controle total sobre segurança e compliance.  
- **Desvantagens**:  
  - Custos elevados de manutenção.  

### 3. Nuvem Híbrida  
- Combina recursos locais com nuvem pública.  
- **Exemplo**: Hospedar dados críticos localmente e usar AWS para processamento.  

### 4. Multicloud  
- Uso simultâneo de múltiplos provedores (ex: AWS + Azure).  
- **Motivação**: Evitar vendor lock-in e aproveitar melhores serviços de cada plataforma.  

---

## 🛠️ Modelos de Serviço  

| Tipo  | Controle do Usuário               | Exemplos                          |  
|-------|-----------------------------------|-----------------------------------|  
| **IaaS** | SO, redes, armazenamento          | AWS EC2, Azure VMs, Google Compute Engine |  
| **PaaS** | Aplicações e dados                | Heroku, Google App Engine, Azure App Service |  
| **SaaS** | Apenas uso do software            | Salesforce, Google Workspace, Slack |  

---

## 💡 Benefícios vs. Desafios  

### ✅ Benefícios  
- **Redução de custos**: Elimina CAPEX em hardware.  
- **Agilidade**: Implantação rápida de aplicações.  
- **Disponibilidade**: Data centers redundantes.  

### ❗ Desafios  
- **Segurança**: Riscos de vazamento de dados.  
- **Vendor lock-in**: Dificuldade de migração entre provedores.  
- **Conformidade**: LGPD, GDPR e soberania de dados.  

---

## 🌐 Tecnologias Habilitadoras  
- **Virtualização**: Divisão de recursos físicos em máquinas virtuais (ex: VMware).  
- **Contêineres**: Isolamento leve de aplicações (Docker, Kubernetes).  
- **Grid Computing**: Recursos distribuídos geograficamente (ex: projetos científicos).  

---

## 📚 Tópicos Relacionados no Obsidian  
- [[Virtualização]]  
- [[AWS vs Azure vs Google Cloud]]  
- [[LGPD e Compliance em Nuvem]]  