## 🖥️ Estudo de Caso: Virtualização com VMware ESXi

### 📌 **Objetivo do Trabalho**
- Investigar e implementar virtualização em ambientes computacionais.
- Desenvolver critérios para planejamento de capacidade e eficiência energética/financeira.
- Reduzir CAPEX/OPEX através de consolidação de servidores.

---

### 🔧 **Ambiente de Testes**
#### **Hardware Utilizado**
| **Equipamento**       | **Processador**       | **RAM** | **Armazenamento**       | **Rede**  |
|-----------------------|-----------------------|---------|--------------------------|-----------|
| Dell Optiplex 780MT   | Intel Core2Duo E8400 | 4GB     | 500GB SATA              | 100Mbps   |
| Dell PowerEdge R710   | Intel Xeon E5620     | 48GB    | 1.8TB SAS (RAID6)       | 1Gbps     |
| Dell PowerEdge R720   | Intel E5-2620        | 192GB   | 4.2TB SAS (RAID6)       | 1Gbps     |

#### **Software**
- VMware ESXi 4.1/5.0/5.5, vCenter.
- Ferramentas: ATTO Disk Benchmark, wPrime, Windows Server.

---

### ⚡ **Eficiência Energética e Consolidação**
- **Redução de 79% na demanda energética** após consolidação (9:1).
  - Consumo anterior: 887.8W → Consolidado: 190.2W.
- **Economia de 78% em kWh** (0.87 kWh → 0.19 kWh/hora).

#### **Gráficos de Demanda**
- **Host R710 (9 VMs)**: Uso médio de CPU ~6.6% (recursos ociosos permitem maior escalabilidade).
- **Consolidação 45:1**: Aumento de apenas 3.3% no consumo energético com 45 VMs inativas.

---

### 💻 **Critérios de Eficiência**
#### **Processador**
- **Hyper-Threading**: Aumenta eficiência em até 50% (Xeon E5620 vs. Core2Duo).
- **Turbo Boost**: Melhora desempenho em cargas pontuais (ex: 2.4GHz → 2.66GHz).
- **wPrime Benchmark**:
  - R720 (24 threads): 126s (24 threads) vs. 2,144s com 44 VMs ativas (**-1,660%** de eficiência).

#### **Disco**
- **RAID6 (16 HDDs)**: Velocidade de ~1,000 MB/s (leitura) vs. NVMe PCIe 4.0 (7,000 MB/s).
- **Concorrência**: Desempenho cai 30% com 8 VMs acessando disco simultaneamente.

#### **Memória**
- **Overcommitment**: 192GB RAM suporta 45 VMs (4GB/VM teórico), mas com ballooning ativo.

---

### 📊 **Escalonamento de Recursos**
| **Recurso**       | **Antes (9 VMs)** | **Depois (45 VMs)** | **Ganho**      |
|-------------------|-------------------|---------------------|----------------|
| **CPU (vCPUs)**   | 24                | 367                 | 15x            |
| **RAM**           | 48GB              | 192GB               | 4x             |
| **Disco**         | 1.6TB             | 4.2TB               | 2.6x           |

---

### 🎯 **Conclusões Principais**
1. **Eficiência Energética**:
   - Virtualização reduz consumo proporcionalmente à ociosidade dos recursos.
   - Memória RAM e discos adicionais aumentam demanda mesmo ociosos.

2. **Vantagens**:
   - Redução de espaço físico, cabos, licenciamento (CAPEX/OPEX).
   - Gerenciamento centralizado via vCenter.

3. **Desafios**:
   - Complexidade na administração (ex: diagnóstico de performance).
   - **Limite de escalonamento**: Depende do subsistema de armazenamento e concorrência por recursos.

4. **Recomendações**:
   - Priorizar CPUs com SMT (Hyper-Threading) e Turbo Boost.
   - Usar SSDs/NVMe para reduzir gargalos de I/O.
   - Monitorar **ballooning** de memória e overcommitment de CPU.

---

### 📈 **Dados Chave para Prova**
- **Slide 37**: Configuração de VMs com alocação dinâmica de CPU (0.2% a 1.3% por VM).
- **Redução energética**: 79% em cenário 9:1 (R710).
- **wPrime**: Eficiência cai drasticamente com concorrência (ex: 44 VMs ativas).
