___
Projeto de Integração de Software
- Vantagens de trabalhar com cloud computing
  - Iaas: hardware -> escolher novos serviços 
  - Paas: integração hardware e software
  - Saas: disponibilização de aplicações

### Projeto de hardware nível 3
- Abordagens padrão e padrões de design selecionados para projetar componentes de hardware simples.
- Busca orientação ao desviar de padrões de design estabelecidos.
- Considera os requisitos finais ambientais, de desempenho, segurança, confiança e sustentabilidade.
- Converte designs lógicos em designs físicos.
- Testa o desempenho de protótipos e dos resultados da produção em relação às especificações (scrum, agile).
- Envia projetos de hardware para aprovação.
- Documenta todo o trabalho usando as normas, métodos e ferramentas necessárias.

### Projeto de hardware nível 4
- Projeta componentes de hardware, levando em consideração os requisitos de ambiente, desempenho, segurança, confiabilidade e sustentabilidade.
- Traduz projetos lógicos em projetos físicos e entrega protótipos técnicos de componentes propostos para aprovação e produção
- Projeta os testes para medir o desempenho de protótipos e saída de produção em relação à especificação e reporta o desenvolvimento iterativo.
- Usuário tem que validar a implementação, verificar se está atendendo as necessidades.

### Projeto de hardware nível 5
- Especifica e projeta componentes/sistemas de hardware complexos
- Seleciona padrões, métodos e ferramentas de design apropriados, consistentes com as políticas corporativas pré-estabelecidas e garante que sejam aplicados de forma eficaz
- Analisa impacto nas principais opções de projeto e avalia e gerencia os riscos associados
- Garante que os projetos de hardware equilibrem requisitos funcionais, de qualidade, de segurança, de proteção, de gerenciamento de sistemas, de confiabilidade e de sustentabilidade.
- Revisa os projetos de outras equipes/profissionais para garantir a seleção de tecnologia apropriada, uso eficiente de recursos e interação eficaz de vários sistemas e tecnologias.
- Contribui para a política de seleção de componentes.

### Projeto de hardware nível 6
- Fornece direção geral e liderança na prática de design de hardware dentro de uma empresa. Influencia modelos baseados na indústria para o desenvolvimento de novas tecnologias de componentes.
- Desenvolve estratégias de compras eficazes, consistentes com as necessidades do negócio, impulsiona a adoção e garante a adesão às políticas, estratégias e padrões organizacionais para design de hardware.

### Projeto de hardware nível 7
- Essa habilidade normalmente não é observada ou praticada nesse nível de responsabilidade e prestação de contas.

1. Barramentos de alto desempenho
- pois em um servidor com vários discos pode haver sobrecarregamento do barramento
    - pode aumentar a largura de dados (inserir mais linhas)
    - ou pode usar uma tecnologia de barramento de alto desempenho
    - ou pode aumentar a frequência de clock
    - ou pode fazer o pipeline e segmentação de instruções em microinstruções
- barramento SAS, permite a gestão integrada dos discos em um servidor de rede.
- integração com tecnologia RAID.

### SSD Solid-State Drive
- Armazenamento é feito em um ou mais chips de memória
- Diespensando totalmente o uso de sistemas mecâncios para o seu funcionamento 
- usado de forma ampla, inclusive em dispositivos extremamente portáteis, como notebooks ultrafinos (ultrabooks) e tablets

### Vantagens do SSD
- mais econômicas no consumo de eneria, pois não precisam alimentar motores ou componentes semelhantes
- não utilização de peças móveis gera um silência do funcionamento de uma unidade SSD, como acontece com um HDD
- o risco de danos é menor quando o dispositivo sofre quedas ou é balançado
- dispositivos SSD pesam menos
- normalmente podem trabalhar com temperaturas mais elevadas que aquelas suportadas pelsos HDDs
- o tempo de transferência de dados entre a memória RAM e unidades SSD costuma ser muito menor, agilizando o processamento de dados

### Uso de memória flash:
- tecnologia SSD é baseada em chips especialmente preparados para armazenar dados, mesmo quando não há recebimento de energia

##### Memória Flash NOR 
- permite acesso ás células de memória de maneira aleatória, tal como acontece com a RAM, mas com alta velocidade
- permite acessar dados em posições diferentes da memória de maneira rápida, sem necessidade de esta atividade ser sequencial
- usado em chips de BIOS ou firmwares de smartphones, por exemplo
- alta velocidade mas capacidade de armazenamento limitada

##### Memória flash NAND
- trabalha em alta velocidade
- faz acesso sequencial às células de memória e as trata em conjunto, isto é, em blocos de células, em vez de aceess-a-las de maneira individual
- memórias NAND também podem armazenar mais dados que memórias NOR, considerando blocos físicos de tamanhos equivalentes
- tipo mais barato e mais utilizado em SSDs

### Tecnologias de gravação dos dados das memórias flash

##### SLC
Single Level Cell
'primeiros SSDs foram baseados em chips com tecnologia SLC
- guardam um bit em cada célula de armazenamento 
- Esse esquema de um bit por cada celula torna o dispositivo mais caro, pois e necessario ter mais células para armazenar a mesma quantidade de dados
- Bastante confiável

##### MLC
Tecnologia Multiple Level Cell
- Tipo MLC é bastante comum
- consistindo em um processo que utiliza tensões diferenciadas para fazer uma célula de memproria armazenar dois bits j(teoricamenteo  é possivel fazê-la armazenar mais) em vez de apenas um
- os custos de dispositivos de armazenamento Flash se tornaram menores
- aumentando inclusive a oferta de produtos, como pendrives e smartphones com preços mais acessíveis
- desempenho costuma ser inferior na comparação com o tipo SLC

##### TLC
- Triple Level Cell
- armazena três bits por célula
- volume de dados que pode ser guardado na unidade aumenta consideravelmente
- um dos padrões mais reentes do mercado
- desempenho também é menor na comparação com tecnologia SLC

##### QLC
Quad Level Cell
- armazena quatro bits por célula
- maior densidade dos chips de armazenamento, maior quantidade de dados sem aumentar as dimnesções físicas do componentes
- suportam apenas mil operações de leitura e escrita por célula
- SSDs com chips QLC costumam ser direcionados apenas a aplicações muito específicas. 

##### PLC
Penta Level Cell
- pode armazenar até cinco bits por c-elula
- maior capacidade de armazenamento de dados
- chips PLC NAND podem apresentar menos desempenho que unidades baseadas nas tecnologias QLC, TLC, MLC e SLC
- tempo de vida útil de SSDs com PLC tende a ser menor na comparação com modelos baseados nesses padrões
- tecnologia PLC está em desenvolvimento, ainda não há informação sobre taxas máximas de leitura ou gravação de dados, tampouco sobre durabilidade.

Barramento dedicado: apenas uma aplicação, ex barramento de memória
Barramento multiplexado: vários tipos de aplicações, como PCIe que pode colocar GPU, disco, etc

### Barramento SATA
- rendimento total do PCIe 3.0 é de 16Gbps
- PCIe 4.0 tem o dobro de redendimento do PCIe 3.0
- oferece até 16 pistas e pode transferir dados até 32 Gb/s
- enquanto o SATA III transfere até 6 Gb/s

### NVME
Non-Volatile Memory Express
- oferece armazenamento superior, velociade superior e compatibiliade superior
- utiliza soquetes PCIe, que permitem transferências de 25 vezes mais dados do que o equivalente SATA
- é uma interface e driver de comunicação que aproveita a maior largura de banda que o PCIe tem para oferecer
- foi projetado para aumentar o desempenho e a eficiência e, ao mesmo tempo, tornar interoperável uma ampla faixa de sistemas empresariais e de clientes
- NVMe foi projetado para SSDs e se comunica entre a interface de armazenamento e a CPU do sistema usando soquetes PCIe de alta velocidade sem as limitações de formato

Os SSDs NVMe vem em uma variedade de formatos, mas são específicos dependendo do caso de uso ou aplicação.
Produtos Pessoais/lientes usam formato BGA e M.2
Aplicaçãoes em Data Center/Servidor usam o frmatos M.2, U.2, U.3 e EDSFF.

Existem padrões e iniciativas de desenvolvimento no EDSFF (Enterprise and Data Center SSD Form Factor) que oferecem uma série dinâmica de formatos e padrões que compartilham o mesmo protocolo (NVMe), a mesma interface (PCIe) e utilizam o seu próprio conector de borda (SFF-TA-1002), pinout (esquema elétrico)

### M.2
- são um tipo de SSD que se conecta a placa-mãe de um computador por meio da interface M.2
- são extremamente eficientes em termos de energia, comparados com outros tiops de SSDs e ocupam menos espaço
- não precisam de cabos de nenhum tipo para se conectar
- são menores e mais rápidos do que os SSDs NVMe tradicionais

### SAS
- alta performance e segurança na gestão de discos
- uso de discos HDD SATA ou SSD SATA

### DAS - Direct Attached Storage
- são sistemas de armazenamento conecttados diretamente a um computador ou servidor
- utilizados para fornecer capacidade de armazenamento para alguma aplicação de um sistema computacional
- um storages DAS sempre depende de um servidor ou computador host para ser acessado
 - não possuem sistema operacional próprio, são dependentes do sistema instalado no computaaod para funcinar
- Para um PC:
    - Pen-drives, cartões de memória e HDs externos são dispositivos de conexão direta
    - Permite armazenar dados e fazer o backup pessoal

### NAS - Network Attached Storage
- sistemas de armazenamento para conexão em redes locais ou redes remotas
- possui sistema operacional próprio
- funciona como uma uniade de armazenamento em rede autônoma.
- através de uma porta de rede ethernet
    - um NAS pode disponibilizar mais capacidade de armazenamento
    - para diversos servidores, compuatadores, notebooks ou celulares
    - via rede local ou internet
- Dispositivo de armazenamento único ou RAID, sistema de armazenamento de arquivos, Rede Ethernet TCP/IP, usuários limitados, velocidade limitada, opções de expansão limitada, menor custo e fácil configuração

### SAN - Storage Area Network
- são infraestruturas de rede com ue interligam servidores e unidades de armazenamento
- proporcionam maior segurança e performance no tráfego de dados
- unifica os recursos de armazenamewnto numa infraestrutura de dados através de uma rede exclusiva, independente e de alto deseempenho
- infreestrutura SAN exige cabeamento proprio, controladoras de barramento (HBAs) e switches com portas de alta velocidade
- Rede de vários dispositivos, sistema de armazenamento em block, rede Fibre Channel, otimizado para vários usuários, desempenho mais rápido, altamente expansível, custo mais alto e configuração complexa
___

SFIA 8, ou Skills Framework for the Information Age versão 8, é a versão mais recente do modelo SFIA, um framework globalmente reconhecido que define e organiza competências em TI e áreas digitais. Esse modelo define mais de 120 competências de TI e digitais, descritas em 7 níveis de responsabilidade, indo desde o básico até o estratégico, e ajuda empresas e profissionais a entender as habilidades necessárias para cada posição ou função, o que é útil para desenvolvimento profissional, recrutamento e planejamento de carreiras.

Essencialmente, o SFIA 8 serve como um guia para mapear habilidades e responsabilidades em TI, promovendo o alinhamento entre as necessidades de uma organização e o desenvolvimento de seus colaboradores.

Os 7 níveis de responsabilidade são os seguintes:

Nível 3: Projetar componentes de hardware simples, seguir padrões, considerar desempenho e segurança, converter designs lógicos em físicos e testar protótipos. Documentar e enviar para aprovação.

Nível 4: Desenvolver componentes com foco em segurança e confiabilidade, traduzir designs lógicos em físicos, criar protótipos, definir testes de desempenho e gerar relatórios de desenvolvimento.

Nível 5: Projetar sistemas complexos de hardware, selecionar métodos e ferramentas de design, avaliar riscos, revisar projetos de terceiros e contribuir nas políticas de seleção de componentes.

Nível 6: Liderar o design de hardware, influenciar o desenvolvimento de novas tecnologias, criar estratégias de compras e assegurar a adesão aos padrões de design da empresa.

Níveis 1, 2 e 7: Não há prática ou observação da habilidade nestes níveis.
___ 
2.1
- SLC (Single Level Cell): Armazena 1 bit por célula. É caro e altamente confiável, com boa durabilidade e desempenho.
- MLC (Multiple Level Cell): Armazena 2 bits por célula, o que diminui o custo mas reduz o desempenho e durabilidade em relação ao SLC.
- TLC (Triple Level Cell): Armazena 3 bits por célula, aumentando a capacidade e reduzindo custos, mas com durabilidade inferior ao MLC.
- QLC (Quad Level Cell): Armazena 4 bits por célula, permitindo mais dados sem aumentar o tamanho físico do SSD. Durabilidade limitada (cerca de 1000 ciclos de escrita/leitura).
- PLC (Penta Level Cell): Em desenvolvimento; armazena 5 bits por célula, oferecendo maior capacidade mas com menor durabilidade e desempenho.

2.2
SSDs com tecnologias de maior densidade (TLC, QLC, PLC) permitem armazenar mais dados em menos espaço, o que os torna uma escolha popular para usuários comuns e em data centers, onde alta capacidade e custo mais baixo são importantes. Entretanto, SSDs SLC e MLC ainda são preferidos para usos que exigem mais durabilidade e desempenho, como em servidores críticos.
A capacidade de armazenamento dos SSDs para usuários comuns normalmente varia de 120 GB a 8 TB. Para servidores pode chegar a até 100TB, como no caso do ExaDrive DC100 da Nimbus Data, que utiliza a tecnologia TLC.

2.3
SATA : Possui limitado a uma taxa de transferência de até 6 Gb/s (750MB/s) em sua versão mais recente (SATA III). Embora sejam mais lentos comparados ao PCIe, são mais acessíveis e populares em PCs domésticos.

PCIe: É uma interface de comunicação de alta velocidade que suporta transferências muito mais rápidas que SATA. As taxas de transferência variam dependendo da versão e do número de pistas (lanes):
- PCIe 3.0: Até 16 Gb/s por direção (aproximadamente 2 GB/s por direção para cada lane).
- PCIe 4.0: Até 32 Gb/s por direção (aproximadamente 4 GB/s por direção por lane).
- PCIe 5.0: Até 64 Gb/s por direção (8 GB/s por lane).
- PCIe 6.0 (em desenvolvimento): Pode alcançar até 128 Gb/s.
___
3.1 DAS (Direct Attached Storage)
- Conexão direta a um computador ou servidor.
- Dependente de um computador host para funcionar.
- Sem sistema operacional próprio, utiliza o sistema do host.
- Exemplos: Pen-drives, cartões de memória, HDs externos.
- Usado para armazenamento local e backup pessoal.

3.2 NAS (Network Attached Storage)
- Armazenamento em rede acessível via Ethernet (rede local ou internet).
- Possui sistema operacional próprio e é autônomo.
- Capacidade compartilhada entre vários dispositivos (servidores, PCs, celulares).
- Ideal para armazenamento de arquivos em rede.
- Menor custo, fácil configuração, expansão limitada, velocidade e usuários limitados.

3.3 SAN (Storage Area Network)
- Rede dedicada que conecta servidores a unidades de armazenamento.
- Oferece alto desempenho e segurança no tráfego de dados.
- Utiliza rede exclusiva, como Fibre Channel, para armazenamento em blocos.
- Alto desempenho, altamente expansível, custo elevado, configuração complexa.