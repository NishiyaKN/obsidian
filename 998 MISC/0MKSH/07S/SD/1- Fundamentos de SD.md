## 👁️ Visão Geral
Este material introduz os conceitos fundamentais de Sistemas Distribuídos (SD), abordando suas principais definições acadêmicas e desafios operacionais. Utiliza a infraestrutura do Instagram como estudo de caso prático para ilustrar como bilhões de requisições são processadas de forma transparente, explorando a arquitetura multicamadas e os componentes essenciais de rede, armazenamento e processamento.

## 🔍 Definições Clássicas
* **Tanenbaum:** Conjunto de computadores independentes que se apresenta aos usuários como um sistema único e coerente (foco em transparência).
* **Coulouris:** Computadores interligados em rede que se comunicam e coordenam ações *apenas* por troca de mensagens (ausência de memória compartilhada).
* **Lamport:** Sistema onde a falha de um computador desconhecido pode inutilizar o seu próprio computador (foco na interdependência e propagação de falhas).

## 🏗️ Arquitetura do Instagram (Fluxo de Requisição)
Quando um usuário interage com o aplicativo, a requisição passa por uma esteira complexa de serviços:
```text
Smartphone -> DNS -> CDN -> Load Balancer (Nginx) -> Servidores de Aplicação -> Cache (Redis) -> Banco de Dados (PostgreSQL) -> Sistema de Arquivos Distribuído (Object Storage)
```
## 📊 Desafios e Conceitos de Sistemas Distribuídos
| Conceito                       | Descrição                                                      | Exemplo Prático (Instagram)                                                    |
| :----------------------------- | :------------------------------------------------------------- | :----------------------------------------------------------------------------- |
| **Concorrência**               | Múltiplos acessos e modificações simultâneas.                  | Dois usuários curtindo o mesmo post ao mesmo tempo (corridas de atualização).  |
| **Ausência de Relógio Global** | Dificuldade em estabelecer a ordem exata dos eventos no tempo. | Ordenar cronologicamente comentários feitos quase no mesmo milissegundo.       |
| **Falhas Independentes**       | Componentes do sistema podem cair sem derrubar o resto.        | Um data center falha e o tráfego precisa ser redirecionado automaticamente.    |
| **Escalabilidade**             | Capacidade de absorver aumentos drásticos de uso.              | Adição rápida de servidores quando um post viraliza.                           |
| **Replicação**                 | Manter cópias de dados em diferentes locais.                   | Garantir alta disponibilidade de fotos, lidando com o desafio da consistência. |

## 📚 Arquitetura Multicamadas
Padrão que divide a aplicação em camadas lógicas independentes, permitindo que cada uma rode em máquinas ou regiões diferentes, aumentando a modularidade e segurança.

1. **Camada de Apresentação (Cliente):** Interface com o usuário (ex: App Mobile, Navegador).
2. **Camada de Aplicação (Lógica de Negócio):** Orquestra operações, regras de negócio e integrações (ex: APIs REST, Microserviços).
3. **Camada de Dados (Persistência):** Armazena e recupera os dados do sistema (ex: SGBDs, Caches, Object Storage).

## 📊 Componentes da Infraestrutura
| Componente | Função Principal | Exemplos / Tecnologias |
| :--- | :--- | :--- |
| **DNS** | Traduzir nomes de domínio para endereços IP. | Sistema distribuído hierárquico. |
| **CDN** | Entregar conteúdo estático do servidor geograficamente mais próximo. | Distribuição de imagens e vídeos. |
| **Load Balancer** | Distribuir requisições entre vários servidores para evitar sobrecarga. | Nginx. |
| **Servidor de Aplicação** | Executar a lógica de negócio e autenticação. | Business Logic, APIs. |
| **Cache Distribuído** | Armazenar dados em memória para acesso ultrarrápido, reduzindo carga no BD. | Redis, Memcached. |
| **SGBD** | Armazenar dados relacionais consistentes (usuários, relacionamentos). | PostgreSQL. |
| **DFS / Object Storage** | Armazenar objetos massivos com metadados para acesso via rede. | Amazon S3, Hadoop HDFS. |

## 💡 Conclusão
Sistemas distribuídos modernos focam em fornecer a ilusão de um serviço único e ininterrupto para o usuário final, ocultando uma infraestrutura altamente complexa. A adoção de arquiteturas multicamadas e componentes especializados (como CDNs, Caches e Load Balancers) é fundamental para contornar gargalos de rede, garantir a escalabilidade horizontal e manter a resiliência contra falhas isoladas.

## ✂️ Tópicos não aprofundados
* **Comandos práticos de rede:** Trechos mostrando a execução de comandos no prompt (`nslookup`, `ping`, `tracert`, `ipconfig`).
* **Analogias didáticas:** Comparação da arquitetura em camadas com "cebolas/ogros" (referência ao filme Shrek).
* **Revisão básica de Sistemas Operacionais e Redes:** Definições muito fundamentais sobre o que é um "Nó", "Cliente", "Servidor" isolado e "Serviço", além da comparação visual direta entre arquitetura local de SO vs. Redes.