## 🚀 Criação de Imagem Docker para Aplicação Node.js  

### 📌 Visão Geral  
- **Objetivo**: Containerizar uma aplicação web Node.js usando Docker.  
- **Stack**: Node.js + Express + Docker.  
- **Resultado**: Aplicação respondendo `"Hello Docker"` na porta 3000.  

---

### 🔧 Passo a Passo  

#### 1️⃣ Configurar Ambiente  
- Instalar Node.js:  
  ```bash  
  node -v  # Verificar versão  
  npm -v   # Verificar gerenciador de pacotes  
  ```  

#### 2️⃣ Criar Projeto Node.js  
- Inicializar projeto:  
  ```bash  
  mkdir HelloDocker  
  cd HelloDocker  
  npm init -y  # Criar package.json automático  
  ```  

#### 3️⃣ Desenvolver Aplicação  
- Arquivo `server.js`:  
  ```javascript  
  const express = require('express');  
  const app = express();  
  const PORT = 3000;  

  app.get('/', (req, res) => res.send('Hello Docker'));  
  app.listen(PORT, () => console.log(`Server running on http://localhost:${PORT}`));  
  ```  

- Instalar Express:  
  ```bash  
  npm install express  
  ```  

#### 4️⃣ Criar Dockerfile  
- Conteúdo:  
  ```dockerfile  
  FROM node:18                 # Imagem base  
  WORKDIR /app                 # Diretório de trabalho  
  COPY package*.json ./        # Copiar dependências  
  COPY server.js ./            # Copiar aplicação  
  RUN npm install              # Instalar pacotes  
  EXPOSE 3000                  # Expor porta  
  CMD ["node", "server.js"]    # Comando de inicialização  
  ```  

#### 5️⃣ Construir e Executar Container  
- Build da imagem:  
  ```bash  
  docker build -t hello-docker .  
  ```  

- Rodar container:  
  ```bash  
  docker run -d -p 3000:3000 --name hello-docker-app hello-docker  
  ```  

- Acessar aplicação:  
  `http://localhost:3000` → Exibe "Hello Docker".  

---

### 🛑 Gerenciamento de Container  
| Comando                  | Ação                                |  
|--------------------------|-------------------------------------|  
| `docker stop <nome>`     | Parar container                    |  
| `docker rm <nome>`       | Remover container                  |  
| `docker rmi <imagem>`    | Remover imagem                     |  

---

### 💡 Explicações Chave  
- **`WORKDIR /app`**: Organiza arquivos dentro do container.  
- **`EXPOSE 3000`**: Mapeia porta do container para o host.  
- **`-d` (detached)**: Roda o container em segundo plano.  

---

### 📊 Fluxo Docker vs. Node.js  
| Etapa               | Docker                              | Node.js Puro               |  
|---------------------|------------------------------------|----------------------------|  
| **Ambiente**        | Isolado via container             | Depende do SO hospedeiro   |  
| **Portabilidade**   | Funciona em qualquer sistema*     | Requer instalação manual   |  

*Desde que Docker esteja instalado.  

---

### 🚨 Solução de Problemas  
- **Erro "Port already in use"**:  
  - Altere a porta no `server.js` e no `docker run` (ex: `-p 4000:3000`).  
- **Dependências não instaladas**:  
  - Verifique se `package.json` está no mesmo diretório do Dockerfile.  