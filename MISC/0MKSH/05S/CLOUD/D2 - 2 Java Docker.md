## 🐳 Criação de Imagem Docker para Aplicação Java Desktop  

### 📌 Visão Geral  
- Objetivo: Empacotar uma aplicação Java Desktop em um container Docker.  
- Fluxo:  
  1. Desenvolver aplicação Java simples.  
  2. Compilar e gerar arquivo JAR.  
  3. Criar imagem Docker com OpenJDK.  
  4. Executar o container em diferentes sistemas (Windows/Linux).  

---

### 🔧 Passo a Passo  

#### 1️⃣ Criar Estrutura do Projeto  
```sh  
mkdir hello-java-docker  
cd hello-java-docker  
mkdir src  
```  

#### 2️⃣ Desenvolver Aplicação Java  
- Arquivo: `src/HelloDockerJava.java`  
```java  
public class HelloDockerJava {  
    public static void main(String[] args) {  
        System.out.println("Hello, Docker.");  
    }  
}  
```  

#### 3️⃣ Compilar e Gerar JAR  
```sh  
javac -d out src/HelloDockerJava.java  
jar cfe hello-java-docker.jar HelloDockerJava -C out .  
```  

#### 4️⃣ Criar Dockerfile  
- Conteúdo:  
```dockerfile  
FROM openjdk:17  
WORKDIR /app  
COPY hello-java-docker.jar /app/hello-java-docker.jar  
CMD ["java", "-jar", "/app/hello-java-docker.jar"]  
```  

#### 5️⃣ Construir Imagem Docker  
```sh  
docker build -t hello-java-docker .  
```  

#### 6️⃣ Executar Container  
```sh  
docker run --rm hello-java-docker  
# Saída esperada: "Hello, Docker."  
```  

---

### 🌐 Transferência para Outras Máquinas  
1. **Exportar imagem** (Windows):  
   ```sh  
   docker save -o hello-java-docker.tar hello-java-docker  
   ```  
2. **Importar imagem** (Fedora):  
   ```sh  
   docker load -i hello-java-docker.tar  
   docker run --rm hello-java-docker  
   ```  

---

### 📊 Comparação: Imagem vs. Container  
| Conceito       | Descrição                                  |  
|----------------|-------------------------------------------|  
| **Imagem**     | Modelo estático com aplicação e dependências. |  
| **Container**  | Instância em execução da imagem.          |  

---

### 💡 Dicas Importantes  
- Use `WORKDIR` no Dockerfile para organização.  
- Flag `--rm` remove containers após execução.  
- Imagens OpenJDK otimizam o processo (evitam instalação manual).  