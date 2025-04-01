## 🌐 Transferência e Execução de Containers em Windows e Linux  

### 📌 Visão Geral  
- **Objetivo**: Compartilhar e executar imagens Docker entre sistemas Windows e Linux.  
- **Métodos**:  
  1. **Arquivo .tar** (para transferência direta).  
  2. **Docker Hub** (para distribuição via nuvem).  

---

### 🖥️ Processo para Windows  
#### 1️⃣ Exportar Imagem como .tar  
(codeblock)bash  
docker save -o hello-docker.tar hello-docker  
(codeblock)  

#### 2️⃣ Transferir Arquivo  
- **Métodos**:  
  - Google Drive/OneDrive.  
  - Pendrive.  
  - Rede local.  

#### 3️⃣ Importar no Windows 11  
(codeblock)bash  
docker load -i C:\caminho\hello-docker.tar  
docker images  # Verificar importação  
(codeblock)  

#### 4️⃣ Executar Container  
(codeblock)bash  
docker run -d -p 3000:3000 --name hello-docker-app hello-docker  
(codeblock)  
- Acesse: `http://localhost:3000` → "Hello Docker".  

---

### 🐧 Processo para Linux (Fedora)  
#### 1️⃣ Configurar Docker  
(codeblock)bash  
sudo dnf install docker  
sudo systemctl start docker  
sudo usermod -aG docker $USER  # Evitar sudo  
newgrp docker  # Atualizar grupos sem logout  
(codeblock)  

#### 2️⃣ Usar Docker Hub  
- **Passos**:  
  1. `docker login` (com token de acesso).  
  2. Baixar imagem:  
     (codeblock)bash  
     docker pull avfreitas/hello-docker  
     (codeblock)  

#### 3️⃣ Rodar Container  
(codeblock)bash  
docker run -d -p 3000:3000 --name hello-docker-app avfreitas/hello-docker  
(codeblock)  

---

### 🔄 Comparação: Métodos de Transferência  
| Método          | Vantagens                          | Limitações                     |  
|-----------------|-----------------------------------|-------------------------------|  
| **Arquivo .tar**   | - Rápido para redes locais.        | - Tamanho grande (~400MB).     |  
| **Docker Hub**     | - Acesso universal via internet.   | - Requer conta e token.        |  

---

### 🛠️ Comandos Úteis para Gerenciamento  
| Comando               | Ação                      |
| --------------------- | ------------------------- |
| `docker ps`           | Listar containers ativos. |
| `docker stop <nome>`  | Parar container.          |
| `docker rm <nome>`    | Remover container.        |
| `docker rmi <imagem>` | Remover imagem.           |
| `docker images`       | Lista imagens             |

---

### 💡 Explicações Chave  
- **Token de Acesso Docker Hub**: Substitui a senha para autenticação segura.  
- `usermod -aG docker`: Adiciona permissões permanentes ao usuário.  
- `-p 3000:3000`: Mapeia porta do container para a máquina host.  

---

### 🚨 Solução de Problemas  
- **Erro de Permissão no Linux**:  
  - Execute `newgrp docker` ou reinicie a sessão.  
- **Falha no Login no Docker Hub**:  
  - Verifique se o token está correto (copie sem espaços).  