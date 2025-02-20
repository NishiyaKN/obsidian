# Módulo 1
### Componentes de rede
- Host: **todo** computador **conectado** a uma rede que participa diretamente da comunicação em rede
- Peer-to-Peer: mesmo PC é usado tanto como um server quanto um client
- End devices: origem ou destino de uma mensagem transmitida pela rede
- Intermediary devices: conectam dispositivos finais à rede
___
### Representações e topologias de rede
- NIC - Network Interface Card: **fisicamente** conecta os end devices na rede
- Porta: conector para conectar dispositivo de rede a outros dispositivos
- Interface: portas **especializadas** que conecta o dispositivo a redes individuais

###### Diagrama de topologia física 
Mostra a localização **real**, ilustra a localização física dos dispositivos intermediários e a instalção dos cabos
![[Pasted image 20240816112854.png]]
###### Diagrama de topologia lógica 
Mostra os **end devices, intermediary devices e mídia usada**, ilustra dispositivos, portas e esequema de endereçamento da rede
![[Pasted image 20240816113014.png]]
___
### Tipos de redes
**LAN** - Local Area Network: rede pequena que conecta alguns dispositivos, usado em **casas** ou pequenas empresas
**WAN** - Wide Area Network: rede de ampla área geográfica, grande coporação ou ISP, conecta cidades, estados, países, **continentes**
Internet: coleção mundial de redes interconectadas

Intranet: conexão privada de LANs e WANs que pertence a uma **organização**, somente pessoal autorizado
Extranet: mesmo que a intranet, mas para fornecer acesso seguro dos dados a empresa a indivíduos terceirizados 
___
### Internet
##### Conexões com a  Intenet para residências e pequenos escritórios
- Cabo: oferecido por provedores de serviços de **televisão a cabo**, fornece alta largura de banda e alta disponibilidade
- DSL (Digital Subscriber Line): utiliza a **linha telefônica**, normalmente é DSL **Assimétrico**, onde **download é mais rápido que upload**
- Celular: rede de telefonia por meio do sinal de celular, desempenho limimtado pelo telefone e torre celular
- Satélite: antenas parabólicas precisam de uma visão clara para o satélite
- Dial-up: baixo custo usa qualquer linha telefônica e um modem, baixa largura de banda

##### Conexões corporativas com a Internet
- Linha alugada Dedicada: circuitos reservados na rede do ISP que conectam escritórios separados para redes privadas de voz ou dados
- Metro Ethernet: Ethernet WAN, ethernet metropolitana, estende a tecnologia de acesso à LAN na WAN
- DSL de negócios (comercial): DSL **Simétrico**, oferece **upload a download nas mesmas velocidades**
- Satélite: quando opção com fios não estiver disponível

**Redes convergentes:** fornece dados, voz e vídeos entre diversos tipos de dispositivos na **mesma infraestrutura de rede**, diferente das antigas redes separadas tradicionais, onde cada tipo de dispositivo tinha seus meios, mensagens e padrões diferentes para cada tipo de mídia
___
### Redes confiáveis

**Arquitetura de redes**: tecnologias que apoiam a infraestrutura e os servições programados e os protocolos que movimentam os dados na rede, deve possuir:
- **Tolerância a falhas**: recuperação rápida em caso de falhas, **redundância** de caminhos (se um falhar, envia por outro caminho). 
	- **Comutação de pacotes**: **divide os dados** do tráfego (mensagem, e-mail, vídeo) em pacotes que são roteados por uma rede compartilhada, cada pacote tem informações de endereço da origem e destino da mensagem, e **cada pacote de uma mensagem pode seguir caminhos diferentes**
- **Escalabilidade**: adição de redes inteiras à redes existentes sem perda de desempenho, segue **protocolos e padrões**
- **Qualidade de Serviço**: o **roteador gerencia**, por exemplo, o **congestionamento** de dados (demanda de largura de banda -bps- maior que a quantidade disponível), para que streaming não fique travando. Com o congestionamento os dispositivos retêm os pacotes na memória até conseguir transmití-los. Webpages podem usar menos banda, equanto chamada de vídeos o **roteador fornece prioridade e maior banda.**
- **Segurança**: os pacotes devem ter **confidencialidade, integridade e disponibilidade**
___
### Tendências das redes
##### Cloud computing
Possibilitado por meio dos data centers, existem 4 tipos de nuvens:
- Public Cloud: disponível para todos, usa internet para oferecer seviços (Google Drive)
- Private Cloud: acesso dentro de uma organização específica, como um governo
- Hybrid Cloud: possui 2+ clouds diferetes onde cada parte tem um objetivo distinto mas usa a mesma arquitetura, acesso de nível variável de acordo com as permissões dos usuários
- Community Cloud: uso exclusivo para entidades ou organizações específicas, como organizações de saúde

##### Rede powerline
- Usa a fiação elétrica existente para conectar dispositivos usando um adaptador padrão powerline. 
- Não precisa instalar cabos de dados, e pouca eletricidade adicional usada
- Não substitui o cabeamento dedicado em redes de dados, é uma alternativa apenas
___
### Segurança de redes
##### Ameaças a segurança
- Viruses, worms, and Trojan horses - código malicioso 
- Spyware and adware - coleta informações do user
- Zero-day attacks - zero-hour attacks, ocorre no mesmo dia que uma vulnerabilidade se torna conhecida
- Threat actor attacks - A malicious person attacks user devices or network resources.
- Denial of service attacks - travam aplicativos e processos em um network device
- Data interception and theft - captura informações privadas de uma organização
- Identity theft - rouba credenciais de login

##### Soluções para segurança (em empresas)

-  Dedicated firewall systems - These provide more advanced firewall capabilities that can filter large amounts of traffic with more granularity.
-  Access control lists (ACL) - These further filter access and traffic forwarding based on IP addresses and applications.
-  Intrusion prevention systems (IPS) - These identify fast-spreading threats, such as zero-day or zero-hour attacks.
-  Virtual private networks (VPN) - These provide secure access into an organization for remote workers.
___
# Módulo 2
### IOS
- OS nos roteadores domésticos são normalmente chamados de firmware
- A porta AUX em dispositivos de rede fornece conexões fora de banda por uma linha telefônica
___
### Navegação IOS
Como recurso de segurança, há separação do acesso de gerenciamento em dois modos de comando:
 - Modo EXEC de usuário - recursos limitados, operações básicas, não consegue alterar a configuração do dispositivo **(view only)**, no prompt representado por `>`
 - Modo EXEC privilegiado - comandos de configuração, no prompt representado por `#` 

###### Configuração global
- Para configurar o dispositivo é necessário entrar no modo de **configuração global**, identificado por `(config)#` 
- Nesse modo ele pode entrar em diversos modos de subconfiguração, os mais comuns são
	- `(config-line)#` Modo de configuração de linha - Usado para configurar o acesso ao console, SSH, Telnet ou AUX
	- `(config-if)#` Modo de configuração da interface - Usado para configurar uma porta de switch ou interface de rede do roteador. 

##### Navegar entre os modos
- enable -> # 
- disable -> >
- configure terminal -> (config)#
- exit -> # 
- line console 0 -> (config-line)# (`line [tipo] [número da linha de gerenciamento]`)
	- exit -> (config)# 
	- end -> # (`Ctrl + z`)
- interface FastEthernet 0/1 -> (config-if)# ()