### 📝 Visão Geral
Este resumo detalha os componentes físicos essenciais que formam a base de um sistema de Internet das Coisas (IoT). Abordaremos os microcontroladores como o cérebro do dispositivo, os diversos tipos de sensores responsáveis por captar informações do ambiente e os atuadores que permitem a interação com o mundo físico.

### 🧠 Microcontroladores vs. Microprocessadores
O processamento em um dispositivo IoT é geralmente realizado por um microcontrolador, que possui características distintas de um microprocessador tradicional.

| Característica | Microcontrolador                                                                        | Microprocessador                                                                               |
| :------------- | :-------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------- |
| **Integração** | É um sistema completo em um único chip, com processador, memória e I/O integrados.      | Precisa de componentes externos como memória e periféricos de I/O para funcionar.              |
| **Aplicação**  | Projetado em hardware para executar uma tarefa específica e dedicada.                   | É de propósito geral, capaz de executar um sistema operacional complexo e múltiplos programas. |
| **Segurança**  | Processa apenas as informações para as quais foi projetado, não havendo risco de vírus. | Suscetível a malwares e vírus, pois executa um software mais complexo.                         |

### 📡 Sensores: Coletando Dados do Ambiente
Sensores são dispositivos que detectam eventos ou mudanças no ambiente e enviam essa informação para o microcontrolador. Alguns tipos comuns incluem
* Temperatura
* Proximidade e Movimento
* Pressão, Umidade e Gás
* Luz, Som (MEMS) e Aceleração

Um destaque são os **sensores magnéticos**, que se dividem em dois tipos principais:

| Tipo            | Funcionamento                                                                          | Saída                                                                                         |
| :-------------- | :------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------- |
| **Efeito Hall** | Detecta a presença e a variação de intensidade de um campo magnético.                  | Fornece um sinal de tensão proporcional à intensidade do campo, não apenas um "sim" ou "não". |
| **Reed Switch** | Funciona como uma chave simples que liga ou desliga na presença de um campo magnético. | Um sinal digital (ligado/desligado).                                                          |

### ⚙️ Atuadores: Agindo no Mundo Físico
Enquanto os sensores coletam dados, os atuadores realizam ações.
* **Definição:** São dispositivos que transformam comandos e dados eletrônicos em ações no mundo físico Exemplos incluem motores, relés, LEDs e válvulas.

### 🏁 Conclusão
Os componentes físicos de IoT formam um sistema coeso onde o microcontrolador atua como centro de processamento. Ele recebe dados do ambiente através de uma variedade de sensores e, com base nesses dados, comanda os atuadores para realizar ações físicas. Essa interação entre perceber, processar e agir é o que permite que dispositivos IoT conectem o mundo digital ao físico de forma inteligente.

### 🚫 Tópicos não aprofundados
A lista abaixo contém tópicos que não foram abordados no material de origem, que se concentrou nos componentes básicos:
* Protocolos de comunicação (Wi-Fi, Bluetooth, LoRaWAN, etc.).
* Fontes de alimentação e gerenciamento de energia.
* Modelos específicos de microcontroladores ou sensores.
* Detalhes sobre sensores de som do tipo MEMS.