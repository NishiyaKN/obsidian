## 🐳 Docker e Containers

### 🔍 Conceitos Fundamentais
- **Docker**: Plataforma para criar, executar e distribuir aplicações em containers.
- **Container**: Unidade isolada que empacota código + dependências (ex: `Node.js + bibliotecas`).
- **Imagem Docker**: "Molde" do container, definido por um `Dockerfile`.

---

### 🚀 Por que usar Docker?
#### Problemas tradicionais:
1. **"Funciona na minha máquina"**: Diferenças entre SO (Windows vs Linux), versões de software ou configurações de servidor.
2. **Dependências conflitantes**: Python 3.8 no dev vs 3.10 no prod.

#### Soluções com Docker:
- **Isolamento**: Containers rodam uniformemente em qualquer SO.
- **Portabilidade**: Imagens podem ser compartilhadas via Docker Hub.
- **Eficiência**: Consome menos recursos que VMs (compartilha kernel do host).

---

### ⚖️ Containers vs Máquinas Virtuais (VMs)
| **Característica** | **Containers**                 | **VMs**                        |
| ------------------ | ------------------------------ | ------------------------------ |
| **Peso**           | Leves (MBs)                    | Pesadas (GBs)                  |
| **Inicialização**  | Segundos                       | Minutos                        |
| **Isolamento**     | Nível de processo (namespaces) | Hardware completo (hypervisor) |
| **Exemplo**        | Docker, LXC                    | VMware, VirtualBox             |

---

### 🛠️ Fluxo de Trabalho com Docker
1. **Dockerfile**: Define etapas para construir a imagem (ex: `FROM python:3.8`).
2. **Build**: `docker build -t minha-app .` → Gera a imagem.
3. **Run**: `docker run -p 8080:80 minha-app` → Inicia o container.

---

### 🌐 Docker Hub
- **Repositório de imagens** (públicas/privadas).
- **Comandos úteis**:
  - `docker pull nginx`: Baixa imagem do Nginx.
  - `docker push meu-user/minha-imagem`: Envia imagem personalizada.

---

### 📥 Instalação do Docker
1. **Download**: [Docker Desktop](https://www.docker.com/products/docker-desktop) (Windows/Mac/Linux).
2. **Verificação**: `docker version` no terminal.
3. **Planos**:
   - **Free**: Para desenvolvedores individuais (1 repositório privado).
   - **Pro/Team**: Recursos avançados para equipes.

---

### ⚠️ Limitações
- **Hardware/Drivers**: Containers dependem do kernel do host.
- **Configurações externas**: DNS, firewall exigem ajustes manuais.
- **Segredos**: Credenciais precisam de gerenciadores como Vault.

---

### 💡 Exemplo Prático
```dockerfile
# Dockerfile para app Python
FROM python:3.8-slim
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
CMD ["python", "app.py"]
```
### Passos:
1. Salve como Dockerfile
2. Execute docker build -t python-app .
3. Rode com docker run -p 5000:5000 python-app