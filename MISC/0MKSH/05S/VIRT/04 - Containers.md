# 🐳 Virtualização com Containers Utilizando Docker

## 📜 Visão Geral
Este documento aborda os conceitos fundamentais de virtualização utilizando containers, com foco na ferramenta Docker. O objetivo é entender o que são containers, suas vantagens, como se comparam com máquinas virtuais e como utilizar o Docker para gerenciar e executar aplicações em ambientes isolados e portáteis.

## 📝 O que são Containers?
Containers são ambientes de execução isolados que compartilham o mesmo sistema operacional do host, mas mantêm suas próprias bibliotecas, dependências e arquivos de configuração encapsulados. [cite: 2] Essa tecnologia permite empacotar uma aplicação com tudo o que ela precisa para rodar, garantindo que funcione da mesma forma em qualquer ambiente - seja no computador do desenvolvedor, em um servidor local ou na nuvem. [cite: 3] Um contêiner é uma unidade padrão de software que empacota código e todas as suas dependências para que o aplicativo seja executado de forma rápida e confiável de um ambiente de computação para outro. [cite: 4]

Uma **Imagem de Contêiner Docker** é um pacote leve, autônomo e executável de software que inclui tudo o que é necessário para executar um aplicativo: código, tempo de execução, ferramentas do sistema, bibliotecas de sistema e configurações. [cite: 5] As imagens de contêineres se tornam contêineres em tempo de execução quando são executadas no Docker Engine. [cite: 6] O software em contêiner sempre será executado da mesma forma, independentemente da infraestrutura, e está disponível para aplicações baseadas em Linux e Windows. [cite: 7]

## ✨ Características dos Containers
Os containers possuem características distintas que os tornam uma solução eficiente para desenvolvimento e deployment de aplicações:
* **Leves**: Compartilham o kernel do sistema operacional do host, eliminando a necessidade de um sistema operacional completo por container. [cite: 9]
* **Portáveis**: Como tudo que a aplicação precisa está incluído no container, ele pode ser facilmente executado em diferentes ambientes. [cite: 10]
* **Isolamento**: Utilizam namespaces e cgroups do Linux para garantir que processos sejam isolados entre containers. [cite: 11]
* **Inicialização rápida**: Como não precisam inicializar um sistema operacional completo, containers são extremamente rápidos para iniciar. [cite: 12]
* **Imagens imutáveis**: Os containers são baseados em imagens que são normalmente construídas por meio de scripts (como o Dockerfile) e não são modificadas em tempo de execução. [cite: 13]

## ⚖️ Containers vs. Máquinas Virtuais (VMs)
Containers e Máquinas Virtuais (VMs) são tecnologias de virtualização, mas operam em níveis diferentes e possuem características distintas. [cite: 14, 17]

| Aspecto               | Containers                                                           | Máquinas Virtuais (VMs)                                            |
| --------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------ |
| **Arquitetura**       | Compartilham o kernel do host. [cite: 21]                            | Cada VM possui seu próprio sistema operacional. [cite: 21]         |
| **Inicialização**     | Em segundos. [cite: 21]                                              | Em minutos. [cite: 21]                                             |
| **Uso de Recursos**   | Mais leve, consome menos CPU, RAM e armazenamento. [cite: 21]        | Mais pesada, devido ao overhead do sistema operacional. [cite: 21] |
| **Isolamento**        | Médio (nível de processo e rede via namespaces/cgroups). [cite: 21]  | Forte (nível de hardware via hypervisor). [cite: 21]               |
| **Portabilidade**     | Alta (imagens funcionam em qualquer sistema com suporte). [cite: 21] | Menor, devido à dependência do sistema operacional. [cite: 21]     |
| **Segurança**         | Boa, mas dependente do kernel compartilhado. [cite: 21]              | Muito alta, isolamento completo. [cite: 21]                        |
| **Caso de Uso Ideal** | Microserviços, CI/CD, aplicações portáteis. [cite: 21]               | Aplicações legadas, multi-OS, alto isolamento. [cite: 21]          |

## 🏗️ Arquitetura Docker
A arquitetura Docker é baseada em um modelo cliente-servidor: [cite: 22]
* **Client (Cliente Docker)**: Interface de linha de comando (CLI) ou outras ferramentas que permitem ao usuário interagir com o Docker Daemon. [cite: 22] Comandos como `docker run`, `docker build`, `docker pull` são enviados ao Daemon. [cite: 22]
* **Docker Host (Host Docker)**: [cite: 22]
    * **Docker Daemon (dockerd)**: O "cérebro" do Docker. Escuta as requisições da API Docker e gerencia objetos Docker como imagens, containers, redes e volumes. [cite: 22]
    * **Images (Imagens)**: Templates read-only com instruções para criar um container Docker. [cite: 22] Podem ser baseadas em outras imagens e personalizadas.
    * **Containers (Contêineres)**: Instâncias executáveis de imagens. [cite: 22] São os ambientes isolados onde as aplicações rodam.
* **Registry (Registro)**: Um local para armazenar e distribuir imagens Docker. [cite: 22] O Docker Hub é um registro público, mas é possível ter registros privados. [cite: 88]

## 🐳 Docker Desktop
Docker Desktop é uma aplicação para Mac, Windows e Linux que permite construir e compartilhar aplicações e microserviços containerizados. [cite: 24, 35] Ele inclui o Docker Engine, Docker CLI client, Docker Compose, Kubernetes, e outras ferramentas. [cite: 29]

## 🚀 Exemplos Práticos com Docker

### "Hello World" 🌎
Este é geralmente o primeiro container executado para verificar se a instalação do Docker está funcionando corretamente. [cite: 94]
```bash
docker run hello-world
```
Ao executar este comando:
1.  O cliente Docker contata o Docker daemon. [cite: 95]
2.  O Docker daemon procura a imagem "hello-world" localmente. Se não encontrar, faz o download (pull) da imagem do Docker Hub. [cite: 96]
3.  O Docker daemon cria um novo container a partir dessa imagem, que executa o programa que gera a mensagem de "Hello from Docker!". [cite: 97]
4.  O Docker daemon transmite a saída do container para o cliente Docker, que a envia para o seu terminal. [cite: 98]

### MySQL com Docker 💾
É possível executar um banco de dados MySQL dentro de um container Docker. [cite: 109]

1.  **Rodando o container MySQL**:
    O comando abaixo baixa a imagem do MySQL (se não existir localmente) [cite: 113, 114] e inicia um container. [cite: 112]
    ```bash
    docker run --name meu-mysql-container -e MYSQL_ROOT_PASSWORD=minhasenha -d mysql:latest
    ```
    * `--name meu-mysql-container`: Nomeia o container. [cite: 112]
    * `-e MYSQL_ROOT_PASSWORD=minhasenha`: Define a senha do usuário root do MySQL através de uma variável de ambiente. [cite: 112]
    * `-d`: Executa o container em modo detached (em segundo plano). [cite: 112]
    * `mysql:latest`: Especifica a imagem a ser usada (a versão mais recente do MySQL). [cite: 112]

2.  **Conectando ao container MySQL via CLI**: [cite: 131]
    ```bash
    docker exec -it meu-mysql-container mysql -uroot -p
    ```
    * `docker exec`: Executa um comando em um container em execução. [cite: 118]
    * `-it`: Aloca um pseudo-TTY interativo.
    * `meu-mysql-container`: Nome do container. [cite: 131]
    * `mysql -uroot -p`: Comando para iniciar o cliente MySQL como usuário root, solicitando a senha. [cite: 131]

3.  **Operações básicas de SQL (dentro do CLI do MySQL)**:
    ```sql
    -- Criar um novo banco de dados
    CREATE DATABASE lojavirtual; [cite: 137]

    -- Selecionar o banco de dados para uso
    USE lojavirtual; [cite: 140]

    -- Criar uma tabela de produtos
    CREATE TABLE produtos (
        id INT PRIMARY KEY AUTO_INCREMENT,
        nome VARCHAR(100),
        preco DECIMAL(10, 2)
    ); [cite: 140]

    -- Inserir alguns dados
    INSERT INTO produtos (nome, preco) VALUES ('Laptop', 3500.00); [cite: 143]
    INSERT INTO produtos (nome, preco) VALUES ('Mouse Gamer', 150.00); [cite: 143]

    -- Consultar os dados
    SELECT * FROM produtos; [cite: 146]
    ```

4.  **Isolamento de Dados**:
    Se você criar múltiplos containers MySQL (ex: `mysqlContainer2`, `mysqlContainer3`), cada um terá seu próprio sistema de arquivos e dados isolados. [cite: 157, 177] Um banco de dados criado em `mysqlContainer` não estará acessível em `mysqlContainer2` a menos que mecanismos de persistência de dados externos e compartilhamento sejam configurados. [cite: 177]

### Python com Docker 🐍
É possível executar aplicações Python ou um interpretador Python interativo em um container. [cite: 178]

1.  **Rodando um container Python interativo**: [cite: 183]
    ```bash
    docker run -it --rm python:latest
    ```
    * `-it`: Modo interativo. [cite: 183]
    * `--rm`: Remove o container automaticamente quando ele é encerrado.
    * `python:latest`: Usa a imagem oficial mais recente do Python. [cite: 182]

2.  **Executando código Python dentro do container**: [cite: 184]
    Após o comando anterior, você estará no interpretador Python dentro do container. [cite: 183]
    ```python
    print("Olá do meu container Python no Docker!") [cite: 184]
    exit()
    ```

## 💡 Conclusão
Docker e a tecnologia de containers revolucionaram a forma como as aplicações são desenvolvidas, testadas e implantadas. Eles oferecem portabilidade, consistência entre ambientes, uso eficiente de recursos e inicialização rápida. Compreender os conceitos de imagens, containers, Dockerfiles e a arquitetura Docker é fundamental para o desenvolvimento de software moderno e práticas de DevOps.

## 🚫 Tópicos Não Aprofundados
Os seguintes tópicos estão presentes no documento original mas não foram detalhados neste resumo por questões de concisão ou por serem considerados menos centrais para o entendimento conceitual inicial:
* Processo detalhado de instalação do Docker Desktop em diferentes sistemas operacionais (Windows[cite: 38, 42], Linux[cite: 38], macOS [cite: 38]).
* Requisitos específicos de sistema e configurações detalhadas para Hyper-V [cite: 45, 62] e WSL 2 no Windows[cite: 56, 57, 62].
* Detalhes sobre os diferentes planos de subscrição (Personal[cite: 29], Pro[cite: 30], Team[cite: 31], Business [cite: 32]) e precificação do Docker.
* Exploração detalhada da interface gráfica do Docker Desktop [cite: 24, 25, 26, 78, 86, 125, 165, 169, 185] e do Docker Hub[cite: 88, 90, 107], incluindo capturas de tela de menus e listas de containers/imagens.
* Saídas detalhadas e explicações de todos os parâmetros dos comandos básicos do Docker como `docker ps`[cite: 120, 130, 161, 164, 166], `docker images`[cite: 121, 128, 129, 159], `docker --help`[cite: 117, 118].
* Instruções e exemplos específicos da atividade de avaliação formativa proposta no documento original[cite: 188, 189, 190].
* Diversas capturas de tela ilustrando cada passo da instalação [cite: 17, 63, 64, 66, 67, 68, 69, 72, 74, 75, 76, 77, 80, 83] e uso de comandos.
* Listagem e informações sobre as múltiplas tags disponíveis para imagens Docker como MySQL [cite: 109] e Python [cite: 181] no Docker Hub.
* Visualização do consumo de recursos (CPU, memória) de múltiplos containers MySQL em execução através do Docker Desktop[cite: 169, 170, 171, 172].