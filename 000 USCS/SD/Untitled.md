**Sistema distribuído:** conjunto de computadores que se apresentam ao usuário como um sistema único, dividindo recursos e processamento, interligados por uma rede, comunicam via troca de mensagens
**Formas de troca de informações entre softwares em diferentes computadores:** TCP/IP, HTTP, gRPC, MQTT
**CDN:** rede de servers distribuídos geograficamente que armazenam cópias de conteúdos estáticdos (imagens, vídeos, CSS) para reduzir latência e consumo de banda no server origem
**Load Balancer:** guarda de trânsito, distribui tráfego de rede ou de requisições entre servidores
**Cache:** armazenamento temporário de acesso rápido para dados frequentemente acessados, evitando idas desnecessárias ao banco de dados
**Servidor de aplicação:** server executar a lógica de negócio, pode servir como intermediário entre o server web (interação com usuário) e o server de bancod de dados
**Aumento de capacidade de demanda:** escalabilidade, pode ser vertical (mais CPU, ram) ou horizontal (mais instâncias)
**Compartilhamento de recursos - acesso simultâneo:** concorrência, vários usuários tentam acessar e modificar o mesmo recurso ao mesmo tempo, precisa de mecanismos de lock ou transações para garantir consistência de dados
**Arquitetura Multicamada:** n-tier, aplicação é dividida em camadas lógicas independentes com funções específicas, para melhor modularidade, escalabilidade e manutenção, além da distribuição física dos componentes
**1- Persistência de dados:** banco de dados
**2- Apresentação:** interface com usuário, front end, app mobile, interface API
**3- Infraestrutura:** servidores fisicos ou virtuais, sistemas operacionais, conteineres, etc
**4- Rede:** responsável pelo roteamento, segurança e comunicação entre os nós
**5- Replicação:** cópias sincronizadas dos dados em diferentes servidores para garantir alta disponibilidade
**Paradigmas:** modelos de abstração que define a natureza da interação entre os componentes de software espalhados por diferentes nós (regras do jogo) para comunicação, sincronização e acoplamento, envolve trade-off. 
**de Arquitetura:** Cliente-servidor, peer-to-peer, sistema em camadas (estrutura vertical n+1 para desacoplamentos, comum o 3 camadas: user, processamento, dados)
**de Comunicação:** RPC (chamada a um serviço parece chamada de função local, transparência de acesso), RMI (JVM, orientado a objetos), MOM (sistemas assíncronos, msg enviada para filas)
**de Organização**: basedos em objetos (coleção de objetos distribuídos com estado e comportamento, interação via msg), arquivos distribuidos (transparência de localização, interage remoto como se fosse local), baseado em documento (transparência de representaçãoes de recursos, REST)
**de Coordenação:** acoplamento, nivel de dependência ou interli
**Trade-Off:**
**Remoção de dependencia entre os sistemas:**
**Projetar para falhar vs projetar para eliminar pontos de falha:**
**Health Check:**