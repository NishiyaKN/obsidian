# 🐳 Virtualização com Containers: Docker

## 📝 Visão Geral
Este resumo aborda a tecnologia de virtualização baseada em containers, com foco no Docker. Ele explora os conceitos fundamentais, características, comparações com máquinas virtuais, a arquitetura do Docker, o Docker Desktop, o Docker Hub e exemplos práticos de uso, servindo como um guia de estudo para estudantes de Ciência da Computação.

## 🧊 O que são Containers?
Containers são ambientes de execução isolados que compartilham o mesmo sistema operacional do host, mas mantêm suas bibliotecas, dependências e arquivos de configuração encapsulados[cite: 2]. Essa tecnologia permite empacotar uma aplicação com tudo o que ela precisa para rodar, garantindo que funcione da mesma forma em qualquer ambiente[cite: 3]. Um contêiner é uma unidade padrão de software que empacota código e todas as suas dependências para que o aplicativo seja executado de forma rápida e confiável[cite: 4]. Uma imagem de contêiner Docker é um pacote leve, autônomo e executável de software que inclui tudo o que é necessário para executar um aplicativo: código, tempo de execução, ferramentas do sistema, bibliotecas de sistema e configurações[cite: 5]. As imagens de contêineres se tornam contêineres em tempo de execução quando são executadas no Docker Engine[cite: 6]. O software em contêiner, disponível para aplicações baseadas em Linux e Windows, sempre será executado da mesma forma, independentemente da infraestrutura[cite: 7].

## ✨ Características dos Containers
* **Leves**: Compartilham o kernel do sistema operacional do host, eliminando a necessidade de um sistema operacional completo por container[cite: 9].
* **Portáveis**: Como tudo que a aplicação precisa está incluído no container, ele pode ser facilmente executado em diferentes ambientes[cite: 10].
* **Isolamento**: Utilizam namespaces e cgroups do Linux para garantir que processos sejam isolados entre containers[cite: 11].
* **Inicialização rápida**: Como não precisam inicializar um sistema operacional completo, containers são extremamente rápidos para iniciar[cite: 12].
* **Imagens imutáveis**: Os containers são baseados em imagens que são normalmente construídas por meio de scripts (como o Dockerfile) e não são modificadas em tempo de execução[cite: 13].

## 📊 Comparação: Containers vs Máquinas Virtuais
| Aspecto             | Containers                                                                 | Máquinas Virtuais (VMs)                                                     |
| ------------------- | -------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| **Arquitetura** | Compartilham o kernel do host [cite: 21]                                       | Cada VM possui seu próprio sistema operacional [cite: 21]                       |
| **Inicialização** | Em segundos [cite: 21]                                                        | Em minutos [cite: 21]                                                         |
| **Uso de Recursos** | Mais leve, consome menos CPU, RAM e armazenamento [cite: 21]                 | Mais pesada, devido ao overhead do sistema operacional [cite: 21]           |
| **Isolamento** | Médio (nível de processo e rede via namespaces/cgroups) [cite: 21]             | Forte (nível de hardware via hypervisor) [cite: 21]                           |
| **Portabilidade** | Alta (imagens funcionam em qualquer sistema com suporte) [cite: 21]          | Menor, devido à dependência do sistema operacional [cite: 21]                 |
| **Segurança** | Boa, mas dependente do kernel compartilhado [cite: 21]                       | Muito alta, isolamento completo [cite: 21]                                    |
| **Gerenciamento** | Fácil com ferramentas como Docker e Kubernetes [cite: 21]                    | Mais complexo, precisa de gerenciadores de VMs [cite: 21]                     |
| **Caso de Uso Ideal**| Microserviços, CI/CD, aplicações portáteis [cite: 21]                       | Aplicações legadas, multi-OS, alto isolamento [cite: 21]                     |

Os contêineres são uma abstração na camada de aplicativo que empacota códigos e dependências juntos[cite: 14]. Múltiplos contêineres podem ser executados na mesma máquina e compartilhar o kernel do sistema operacional com outros contêineres, cada um executando como processos isolados no espaço do usuário[cite: 15]. Eles ocupam menos espaço que as VMs (dezenas de MBs) e podem lidar com mais aplicativos[cite: 16]. As máquinas virtuais (VMs) são uma abstração de hardware físico, transformando um servidor em muitos servidores[cite: 17]. O hypervisor permite que várias VMs sejam executadas em uma única máquina[cite: 18]. Cada VM inclui uma cópia completa de um sistema operacional, o aplicativo, binários e bibliotecas, ocupando dezenas de GBs e podendo ser lentas para inicializar[cite: 19, 20].

## 🏗️ Arquitetura Docker
A arquitetura Docker é composta por:
* **Client**: Interface utilizada para interagir com o Docker Daemon (ex: comandos `docker run`, `docker build`, `docker pull`).
* **Docker Host**: Máquina que executa o Docker Daemon.
* **Docker Daemon**: Processo que gerencia os containers, imagens, volumes e redes.
* **Images**: Templates read-only com instruções para criar um container Docker.
* **Containers**: Instâncias executáveis de uma imagem.
* **Registry**: Repositório para armazenar e distribuir imagens Docker (ex: Docker Hub).
[cite: 22]

## 🖥️ Docker Desktop
Docker Desktop é um software para desenvolvedores e equipes que simplifica o desenvolvimento com ferramentas de contêiner[cite: 24]. Ele permite gerenciar containers, imagens e volumes de forma gráfica e integrada ao ambiente de desenvolvimento[cite: 25, 37].

### 📋 Planos de Assinatura Docker
| Plano           | Preço (usuário/mês) | Ideal para                                                                 | Recursos Chave (além do plano anterior)                                                                                                                              |
| --------------- | ------------------- | -------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Personal** | $0 [cite: 29]          | Desenvolvedores individuais (ferramentas essenciais) [cite: 29]               | Docker Desktop, Docker Engine + Kubernetes, Docker Hub, Docker Scout, Docker Debug, Testcontainers Cloud, Synchronized File Shares [cite: 33]                        |
| **Pro** | $11 [cite: 30]         | Profissionais individuais (recursos avançados) [cite: 30]                    | Tudo do Personal mais alocações de uso de ferramentas premium integradas com capacidade de adicionar mais[cite: 28, 33].                                              |
| **Team** | $16 [cite: 31]         | Pequenas equipes (ferramentas colaborativas) [cite: 31]                      | Tudo do Pro mais: Adicionar usuários em massa, Audit logs, Docker Hub role-based access control, Suporte com resposta em 2 dias[cite: 33].                          |
| **Business** | $24 [cite: 32]         | Empresas (segurança robusta, controle e conformidade) [cite: 32]             | Tudo do Team mais: Hardened Docker Desktop, Single Sign-On (SSO), SCIM user provisioning, Image and Registry Access Management[cite: 33].                           |

*Nota: O uso comercial do Docker Desktop em empresas com mais de 250 funcionários OU mais de $10 milhões em receita anual requer uma assinatura paga (Pro, Team ou Business)[cite: 70].*

### ⚙️ Requisitos de Sistema para Docker Desktop no Windows
Existem duas principais arquiteturas para rodar o Docker Desktop no Windows: WSL (Windows Subsystem for Linux) e Hyper-V. A funcionalidade é consistente em ambas, sem preferência por uma ou outra, cada uma com suas vantagens e desvantagens dependendo da configuração e caso de uso[cite: 40, 41, 51, 52].

**Para backend Hyper-V (x86_64):**
* Windows 11 64-bit: Enterprise, Pro, ou Education versão 22H2 ou superior[cite: 43].
* Windows 10 64-bit: Enterprise, Pro, ou Education versão 22H2 (build 19045) ou superior[cite: 44].
* Ativar recursos Hyper-V e Containers do Windows[cite: 44].
* Processador de 64 bits com Second Level Address Translation (SLAT)[cite: 45].
* 4GB de RAM do sistema[cite: 45].
* Suporte à virtualização de hardware em nível de BIOS/UEFI ativado[cite: 45].
* *Importante: Para rodar containers Windows, é necessário Windows 10 ou Windows 11 Professional ou Enterprise. Edições Home ou Education permitem apenas containers Linux[cite: 48].*

**Para backend WSL 2 (x86_64 e Arm Beta):**
* WSL versão 1.1.3.0 ou posterior[cite: 54].
* Windows 11 64-bit: Home ou Pro versão 22H2 ou superior, ou Enterprise ou Education versão 22H2 ou superior[cite: 54].
* Windows 10 64-bit: Mínimo Home ou Pro 22H2 (build 19045) ou superior, ou Enterprise ou Education 22H2 (build 19045) ou superior[cite: 55].
* Ativar o recurso WSL 2 no Windows[cite: 56].
* Processador de 64 bits com Second Level Address Translation (SLAT)[cite: 57].
* 4GB de RAM do sistema[cite: 57].
* Ativar virtualização de hardware no BIOS/UEFI[cite: 57].
* *Importante: Para rodar containers Windows, é necessário Windows 10 ou Windows 11 Professional ou Enterprise. Edições Home ou Education permitem apenas containers Linux[cite: 61].*

*Docker Desktop não é suportado em versões de servidor do Windows como Windows Server 2019 ou 2022[cite: 47, 60].*

### 🚀 Processo de Instalação (Exemplo Windows)
1.  **Download**: Baixar o instalador do Docker Desktop.
2.  **Inicialização**: O instalador verifica o pacote[cite: 63].
3.  **Configuração**:
    * Opção de usar WSL 2 em vez de Hyper-V (recomendado)[cite: 64].
    * Opção de permitir o uso de Windows Containers[cite: 64].
    * Opção de adicionar atalho na área de trabalho[cite: 64].
4.  **Desempacotamento e Instalação**: Arquivos são desempacotados e componentes instalados[cite: 66, 67].
5.  **Reinicialização**: É necessário reiniciar o Windows para completar a instalação[cite: 68].
6.  **Acordo de Serviço**: Aceitar o "Docker Subscription Service Agreement"[cite: 69].
7.  **Configuração Final**: Escolher entre configurações recomendadas (requer senha de administrador) ou avançadas[cite: 72, 73].
8.  **Login/Registro (Opcional)**: Opção de fazer login com conta Docker ou criar uma[cite: 74, 75].
9.  **Pesquisa (Opcional)**: Responder a uma pesquisa sobre o perfil do usuário[cite: 76, 77].
10. **Integração com WSL**: Docker Desktop se integra bem com WSL, permitindo rodar comandos Docker no WSL ou Windows usando o mesmo daemon e imagens, compartilhar arquivos entre Windows e Linux, e usar ferramentas Windows em código Linux e vice-versa[cite: 84, 85].

## ☁️ Docker Hub
Docker Hub é um serviço de registro baseado em nuvem que permite encontrar e compartilhar imagens de contêineres[cite: 88]. É possível pesquisar por imagens como "hello-world" [cite: 90] ou "mysql"[cite: 107]. Ele também destaca imagens populares e tendências, como `ollama/ollama` para modelos de linguagem grandes e `pytorch/pytorch` para deep learning[cite: 89].

## 🛠️ Exemplos Práticos

### 🌍 Executando "hello-world"
O comando `docker run hello-world` demonstra que a instalação está funcionando corretamente[cite: 94].
Na primeira execução:
1.  O cliente Docker contata o daemon Docker[cite: 95].
2.  O daemon Docker baixa a imagem "hello-world" do Docker Hub (se não existir localmente)[cite: 96, 93].
3.  O daemon Docker cria um novo container a partir dessa imagem[cite: 97].
4.  O daemon Docker transmite a saída para o cliente Docker, que a envia para o terminal[cite: 98].
^^^bash
C:\Users\DEVSECOPS>docker run hello-world
^^^
Na segunda execução, como a imagem já está localmente, ela não é baixada novamente[cite: 101, 103].

### 🗃️ Usando MySQL
**Passo 1: Instalação do container MySQL**
O comando abaixo baixa (se necessário) e inicia um container MySQL chamado `mysqlContainer`, define a senha do root e executa em background (`-d`) usando a imagem `mysql:9.3.0`[cite: 112].
^^^bash
docker run --name mysqlContainer -e MYSQL_ROOT_PASSWORD=senha -d mysql:9.3.0
^^^
Durante a primeira execução, a imagem `mysql:9.3.0` é baixada do Docker Hub[cite: 114, 116].

**Passo 2: Conectando ao banco de dados**
Conecta-se ao container MySQL em execução de forma interativa (`-it`)[cite: 131].
^^^bash
docker exec -it mysqlContainer mysql -uroot -p
^^^
Será solicitada a senha definida no Passo 1.

**Passo 3: Criando o banco de dados**
^^^sql
CREATE DATABASE mercado; [cite: 137, 139]
^^^

**Passo 4: Criando uma tabela**
^^^sql
USE mercado; [cite: 140, 142]
CREATE TABLE produtos (
    id INT PRIMARY KEY,
    nome VARCHAR(100),
    preco DECIMAL(10, 2)
); [cite: 140]
^^^

**Passo 5: Inserindo dados na tabela**
^^^sql
INSERT INTO produtos (id, nome, preco) VALUES
(1, 'Abacaxi', 15.50),
(2, 'Banana', 22.30),
(3, 'Uva', 18.00),
(4, 'Pera', 25.00),
(5, 'Laranja', 30.00),
(6, 'Limao', 12.00),
(7, 'Melancia', 19.50),
(8, 'Mamao', 28.70),
(9, 'Goiaba', 17.80),
(10, 'Ameixa', 20.00); [cite: 143, 145]
^^^

**Passo 6: Consultando o conteúdo da tabela**
^^^sql
SELECT * FROM produtos; [cite: 146, 148]
^^^

**Passo 7: Identificando valores mínimo, máximo e média**
^^^sql
SELECT
    MAX(preco) AS preco_maximo,
    MIN(preco) AS preco_minimo,
    AVG(preco) AS preco_medio
FROM produtos; [cite: 150, 152]
^^^
Resultado: preco_maximo 30.00, preco_minimo 12.00, preco_medio 20.880000[cite: 153].

**Passo 8: Obtendo o valor total dos produtos**
^^^sql
SELECT SUM(preco) AS soma_total
FROM produtos; [cite: 154]
^^^
Resultado: soma_total 208.80[cite: 156].

**Criando containers (instâncias) adicionais**
É possível criar múltiplas instâncias do MySQL, cada uma com seu próprio nome e dados isolados.
^^^bash
docker run --name mysqlContainer2 -e MYSQL_ROOT_PASSWORD=senha -d mysql:9.3.0 [cite: 157]
docker run --name mysqlContainer3 -e MYSQL_ROOT_PASSWORD=senha -d mysql:9.3.0 [cite: 157]
^^^
Ao conectar no `mysqlContainer2` e tentar acessar o banco `mercado` ou a tabela `produtos`, eles não existirão, demonstrando o isolamento de dados entre as instâncias[cite: 173, 177].

### 🐍 Usando Python
**Instalação (Download da Imagem)**
Se a imagem `python:latest` não estiver localmente, o comando a baixa[cite: 182].
^^^bash
docker run python:latest
^^^

**Execução Interativa**
O comando `-it` permite interagir com o interpretador Python dentro do container[cite: 183].
^^^bash
docker run -it python:latest
^^^
Dentro do container, pode-se executar código Python:
^^^python
print ("Programando em um container docker"); [cite: 184]
exit()
^^^

### 📋 Comandos Docker Úteis
* `docker ps`: Lista os containers em execução[cite: 120, 130, 161, 164, 166].
* `docker images`: Lista as imagens Docker locais[cite: 121, 129, 159].
* `docker --help`: Exibe informações de ajuda sobre os comandos Docker[cite: 117].

| Comando  | Descrição                                                           |
| -------- | ------------------------------------------------------------------- |
| `run`    | Cria e executa um novo container a partir de uma imagem [cite: 118] |
| `exec`   | Executa um comando em um container em execução [cite: 118]          |
| `ps`     | Lista containers [cite: 118]                                        |
| `build`  | Constrói uma imagem a partir de um Dockerfile [cite: 118]           |
| `pull`   | Baixa uma imagem de um registro [cite: 118]                         |
| `push`   | Envia uma imagem para um registro [cite: 118]                       |
| `images` | Lista imagens [cite: 118]                                           |

## 💡 Conclusão
Docker e a tecnologia de containers revolucionaram o desenvolvimento e a implantação de software, oferecendo portabilidade, eficiência e isolamento. Através de ferramentas como Docker Desktop e Docker Hub, desenvolvedores podem facilmente criar, gerenciar e compartilhar aplicações em ambientes consistentes. A capacidade de rodar múltiplas instâncias isoladas, como demonstrado com o MySQL, e de utilizar ambientes de desenvolvimento prontos, como o Python, destaca a flexibilidade e o poder dos containers.