

Virtualização tipo 1 é mais segura porque não depende de um SO hospedeiro, que pode ter vulnerabilidades
Xen é um hipervisor Tipo 1
Implementar bare-metal em um ambiente de TI exige gerenciamento cuidadoso, pois não há abstração para migração dinâmica de instâncias entre diferentes recursos do hardware. Bare-metal não tem virtualização, então não suporta migração ao vivo (live migration) como VMs.
Partições logicas podem conter sistemas operacionais (ex.: Linux pode ser instalado em partições lógicas)
BIOS/MBR requer uma primária para o bootloader, enquanto o GPT UEFI permite bootar de qualquer partição
O bootloader não é parte do firmware nem permanece em execução após carregar o kernel.
O Volume Boot Record (VBR) fica no início da partição e contém o código para carregar o bootloader do sistema operacional. Também armazena informações sobre o sistema de arquivos, como NTFS, FAT32 e ext4, garantindo a inicialização correta."
BIOS + MBR: O Boot Manager (ex.: GRUB) pode ser instalado no MBR ou em uma partição dedicada.
UEFI: Usa uma partição EFI (FAT32) para armazenar bootloaders, facilitando o gerenciamento de múltiplos SOs.
VBR só existe em partições formatadas (não em discos sem SO ou não inicializáveis).
O bootloader não permanece em execução: Ele é carregado pelo VBR, transfere controle ao kernel do SO e encerra sua execução.
A MBR está localizada no setor 0 do disco e contém:
	Código de boot (bootloader primário).
	Tabela de partições (4 entradas para partições primárias).
	Assinatura (0x55AA).
CHS (Cilindro-Cabeça-Setor) é obsoleto em discos modernos (era usado em HDs antigos).
LBA (Logical Block Addressing) é o padrão atual e é compatível com todos os sistemas modernos.
O setor de boot presente na MBR pode conter código executável que carrega um sistema operacional ou um gerenciador de boot como o GRUB.
Os bootloaders em UEFI são armazenados na ESP como arquivos executáveis, geralmente no diretório \EFI\NomeDoSO. Diferente do BIOS/MBR, a ESP permite múltiplos sistemas operacionais sem sobrescrever um único setor de inicialização._
O UEFI não obrigatoriamente necessita de um bootloader externo para carregar um SO
A ESP deve ser formatada em FAT32 (ou FAT16 em casos raros) para ser reconhecida pelo UEFI.
O total de setores depende de: Número de cilindros × cabeças × setores por trilha.
O código de boot do MBR (446 bytes) pode ser substituído por gerenciadores como GRUB (Linux) ou BOOTMGR (Windows) para controlar o processo de inicialização.
Em partições MBR, o boot manager e bootloader estagio 1 ficam no mbr, o bootloader estagio 2 fica no VBRÇ


# 🖥️ **Resumo de Conceitos de Boot, Partições e Virtualização**  

## **🔍 Virtualização**  
- **Tipo 1 (Bare-metal)**:  
  - Mais seguro (não depende de SO hospedeiro).  
  - Exemplo: **Xen**.  
  - Desvantagem: Sem migração ao vivo (live migration).  

## **💽 Particionamento**  
- **Partições lógicas**: Podem conter SOs (ex: Linux instalável nelas).  
- **MBR vs. GPT**:  
  - **BIOS/MBR**: Exige partição primária para bootloader.  
  - **UEFI/GPT**: Permite boot de qualquer partição.  

## **🔧 Boot Process**  
### **MBR (BIOS Legacy)**  
- Local: **Setor 0** do disco.  
- Contém:  
  - Código de boot (446 bytes).  
  - Tabela de partições (4 entradas).  
  - Assinatura **`0x55AA`**.  
- **Bootloader**:  
  - **Estágio 1**: No MBR.  
  - **Estágio 2**: No VBR da partição ativa.  

### **UEFI/GPT**  
- **ESP (EFI System Partition)**:  
  - Formato **FAT32** (obrigatório).  
  - Armazena bootloaders em **`/EFI/NomeDoSO/`** (ex: `bootx64.efi`).  
  - Permite múltiplos SOs sem conflitos.  
- **Vantagens**:  
  - Suporte a **Secure Boot**.  
  - Mais flexível que MBR.  

### **Volume Boot Record (VBR)**  
- Fica no **início da partição**.  
- Funções:  
  - Carrega o bootloader.  
  - Armazena info do sistema de arquivos (NTFS, FAT32, ext4).  
- **OBS**: Só existe em partições formatadas/inicializáveis.  

## **⚙️ Outros Conceitos**  
- **CHS (Cilindro-Cabeça-Setor)**: Obsoleto (discos antigos).  
- **LBA (Logical Block Addressing)**: Padrão atual.  
- **Bootloader**:  
  - Não é parte do firmware.  
  - Encerra após carregar o kernel.  

## **📌 Comparação Rápida**  
| **Tópico**          | **BIOS/MBR**                     | **UEFI/GPT**                     |  
|----------------------|----------------------------------|----------------------------------|  
| **Local do Bootloader** | MBR ou partição dedicada       | ESP (arquivo `.efi`)             |  
| **Limite Partições** | 4 primárias (com estendida/logicas) | Até 128 partições (sem estendida) |  
| **Segurança**        | Menor (sem Secure Boot)         | Maior (com Secure Boot)          |  
