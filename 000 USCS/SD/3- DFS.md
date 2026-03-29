# 📂 Sistemas de Arquivos Distribuídos (DFS)

### 📝 Visão Geral
O DFS (Distributed File System) é uma tecnologia que permite organizar e acessar arquivos espalhados por múltiplos servidores através de um namespace único e hierárquico. Para o usuário, o sistema oferece uma visão unificada, como se todos os dados estivessem armazenados em um único local, simplificando estruturas complexas de rede e abstraindo a localização física real dos arquivos.

### 🏛️ Estrutura e Funcionamento
O DFS opera criando uma camada de abstração entre o caminho lógico e o caminho físico.

* **Namespace:** É o caminho lógico único (ex: \\Empresa\Arquivos) que centraliza o acesso.
* **Tipos de Namespace:** * **Autônomo:** Configurado em um único servidor.
    * **Baseado em Domínio:** Integrado ao Active Directory, oferece alta disponibilidade e múltiplos servidores.
* **Raízes (Roots) e Links:** A estrutura é composta por destinos de raiz, links DFS e pastas compartilhadas. Cada link pode apontar para múltiplos destinos (balanceamento/tolerância a falhas).
* **Replicação (DFS-R):** Mantém os arquivos sincronizados entre servidores, garantindo redundância e continuidade de negócios em caso de falhas (exige volumes NTFS).

📊 **Comparativo de Configurações**

| Característica | Sem DFS | Com DFS |
| :--- | :--- | :--- |
| **Acesso** | Múltiplos caminhos (\\ServidorA\RH, \\ServidorB\Proj) | Caminho único centralizado (\\Empresa\Arquivos) |
| **Localização** | Usuário deve saber onde cada pasta está | Localização física é transparente ao usuário |
| **Disponibilidade** | Se o servidor cai, o acesso é perdido | Redirecionamento automático para outro destino |

### 🛠️ Implementação e Funções
O sistema é gerenciado por um conjunto de APIs que permitem a manipulação programática da estrutura distribuída.

* **Funções de Criação/Expansão:** `NetDfsAdd`, `NetDfsAddRootTarget`.
* **Funções de Monitoramento/Consulta:** `NetDfsEnum`, `NetDfsGetInfo`.
* **Funções de Exclusão:** `NetDfsRemove`, `NetDfsMove`.
* **Segurança:** Integra-se aos mecanismos de controle de acesso do Windows e Active Directory através de funções como `NetDfsSetSecurity` e proteção explícita da pasta raiz (desabilitando herança).

### 💻 Exemplo de Instalação via PowerShell
A instalação das funções de servidor pode ser feita rapidamente através de comandos administrativos.

^^^powershell
# Instala os recursos de Namespace e Replicação do DFS
Install-WindowsFeature FS-DFS-Namespace, FS-DFS-Replication -IncludeManagementTools
^^^

### 🔍 Conclusão
O DFS é uma ferramenta vital para infraestruturas de TI modernas, pois transforma a gestão de armazenamento em uma rede lógica eficiente. Ao separar a lógica de acesso da infraestrutura física, ele permite que administradores reorganizem servidores e realizem manutenções sem impactar o fluxo de trabalho do usuário final, garantindo redundância e escalabilidade com segurança configurável.

### 📑 Tópicos não aprofundados
* Detalhes do passo a passo da interface gráfica (Server Manager) para criação de Namespaces e pastas.
* Procedimento detalhado de desabilitação de herança e remoção de permissões explícitas no Windows Explorer para proteção do namespace.
* Configurações específicas de topologia de replicação, largura de banda e filtros.
* Sincronização forçada de metadados com o emulador PDC do domínio.