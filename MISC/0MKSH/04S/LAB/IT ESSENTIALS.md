# Chapter 1

**ESD** - Electrostatic Discharge, < 30 volts can damage pc components
___
### Power supply
- **Types**
	- AT - obsolete, doesn't have +3.3V
	- ATX - obsolete
	- ATX12V - 'most' common, has dedicated power to CPU
	- EPS12V - used for high-end desktop models
- **Connectors**
	- 20/24 pin - motherboard
	- SATA - data cable 7 pins, power cable 15 pins
	- Molex - hard drives, optical drives, etc
	- Berg - floppy drives
	- 4/8 pin - auxiliary power for GPU, CPU
	- 6/8 pin - PCIe power connector
- **Voltage** 
	- 3.3V (digital circuit)
	- 5V (digital circuit)
	- 12V (disk and fan motor)
---
### Motherboard
- **Connections**
	- Chipset - control how system hardware interacts with the CPU, limits how much RAM  can be added
	- BIOS - boot the system and manage the flow of data to every component
	- UEFI - newer BIOS, specifies a different firmware 
	- IDE - old disk drives, 40 pin connector
	- Internal USB - 19 pin for USB 3, 9 pin for USB 1.1 and 2
- **Chipset**
	- Northbridge - high speed data: RAM, GPU, CPU, PCIe - conectados pelo FSB front side bus
	- Southbridge - slow speed data: HDD, BIOS, PCI, peripherals
 - **Form factors**
	 - ATX - most used, 20 pin connector
	 - Micro ATX - used in small pcs
	 - ITX - small, uses little power
	 - Mini ITX - used in thin clients
---
### CPU
- **Architectures**
	- PGA - pin grid array, pins are in the CPU package
	- LGA - land grid array, pins are in the socket
 ---
### Memory - cnp
- **ROM**
	Directly accessed by the CPU, stores basic operation instructions such as boot
	- ROM - Read-Only Memory
	- PROM - Programmable ROM
	- EPROM - Erasable PROM, erased by UV light exposure
	- EEPROM - Electrically EPROM, used for BIOS
		- Flash Memroy is an upgrade from EEPROM
- **RAM**
	Acessed by programs used by the CPU
	- DRAM - Dynamic RAM, used for main memory
	- SRAM - Static RAM, cache memory, low power, much faster than DRAM
	- SDRAM - Synchronous Dynamic RAM, high transfer rates, processes overlapping instructions in parallel
	- DDR SDRAM - Double Data Rate SDRAM, each gen is faster, uses less power, has more pins, etc. 
	- GDDR RAM - Graphics, GPU
	![[Pasted image 20241011204210.png]]
- **Modules**
	Memory modules can be single-sided or double-sided.
	- DIP - Dual Inline Package
	- SIMM - Single Inline Memory Module, small circuit board that holds sevelra memory chips
	- DIMM - Dual Inline Memory Module, holds SDRAM chips
	- SODIMM - Small Outline DIMM, used on laptops, printers and small devices
	- RDDIM -  memória com buffer, que permite uma maior quantidade de RAM mas uma velocidade reduzida. Ela possui um controlador que faz o gerenciamento de grandes quantidades da RAM. Mais comum em servers e workstations
 - **Memory errors**
	 - Nonparity - doesn't check for errors, most common for home and business workstations
	 - Parity - contains eight bits for data and one for error checking (parity bit)
	 - ECC - Error Correction Code memory can detec multiple bit errors and correct single bit errors, used on financial or data analytics servers
 ___
### Hard Disk Drives
- **Magnetic**
	- HDD
		- 1.8'
		- 2.5'
		- 3.5'
	- Tape - used for archiving
 - **Solid State**
	- Disc drive - like HDD, 1,8', 2.5' ,3.5'
	- Expasion cards - plugged directly into the motherboard
	- mSata (M.2) - use a special socket

___
# Chapter 2

![[Pasted image 20241006181418.png]]
![[Pasted image 20241006181842.png]]
![[Pasted image 20241006182003.png]]
![[Pasted image 20241006182107.png]]
![[Pasted image 20241006194214.png]]
![[Pasted image 20241006194841.png]]
![[notes/LAB/Media/Pasted image 20241007165346.png]]
- Memoria buffer é comumente utilizada em servidores
- 5,25" - unidade optica
- PSU fica assegurada por parafusos
- PCIe é serial, PCI é paralelo
- Adaptador de vídeo (GPU) deve precisar de dois conectores de energia de 8 pinos
- Finalidade de um "espelho" I/O é tornar as portas I/O da mobo disponíveis para conexão para uma variedade de gabinetes
- CPU e RAM conectados pelo barramento frontal 
___
# Chapter 3
### POST
Means power-on self-test, and is a **hardware check** performed by the BIOS on boot. Whenever some hardware fails, it will beep x times corresponding to the hardware fail beep code defined by the manufacturer 
### BIOS
- Is a small program contained inside a ROM chip on the motherboard, which controls communication between the OS and the hardware.
- It's settings are saved on a CMOS memory chip.
- When booted, the BIOS look for the configuration set on the CMOS.
- CMOS uses a watch battery
### UEFI
Unified Extensible Firmware Interface, provides additional features and better security compared with legacy BIOS.
Can run on 32-bit and 64-bit systems, support larger boot drives and have things like secure boot. 
Secure boot faz com que apenas sistemas operacionais e drivers confiáveis sejam bootados
### Security features
- Passwords - allows for different levels of access to the BIOS settings
- Drive encryption
- LoJack - locate, lock and delete
- TPM - Trusted Platform Module - chip that stores encyption keys, digital certificates, password and data. Used by BitLocker's full disk encryption
- Secure boot - computer will only boot an OS trusted by the motherboard manufacturer
### Power Fluctuation Types
Unsteady voltages 
 - Blackout - Complete loss of AC power
 - Brownout - Drops below 80% of the normal voltage level or is overloaded
 - Noise - Interferences form generators and lightning (poor quality power)
 - Spike - Sudden increase of voltage, over 100% of normal levels, caused by lightning or when electrical system comes backs
 - Power surge - Dramatic increase in voltage, lasts for a few nanoseconds
### Power Protection Devices
- Surge protector - protects from surge and spikes, diverts extra voltage to the ground
- UPS - Uninterruptible power supply, supplies a **consistent** level of power to a device. Helps on blackouts or brownouts. 
- SPS- Standby power supply, provides a backup battery when voltage drops below the normal level. Not reliable as UPS since it takes time to switch and if may fail.
### CPU Architectures
CPU executes programs (sequence of stored instructions) by following a specific instrcutions set:
- RISC - Reduced Instruction Set Computer, have very small instructions, designed to execute them rapidly. E.g, ARM, PowerPC.
- CISC - Complex Instruction Set Computer, uses a broad set of instructions, fewer steps. E.g., Intel x86.
### CPU Operation
- Hyper-Threading - multiple pieces of code (threads) are executed simultaneously in the CPU. It's like there are multiple CPUs
- HyperTransport - high-speed connection between the CPU and Northbridge chip
The amount of data that a CPU can process at one time depends on the size of the [[FSB]]. 
### Multicore
- Cache L2 e L3 normalmente são separados, L1 é compartilhada
- Multicore usa menos energia e produz menos calor que singlecore

### RAID
###### Stripping
- dados distribuídos por várias unidades
- melhor desempenho
- falha de uma unidade > perde todos os dados

###### Espelhamento
- dados duplicados
- falha de uma unidade > não perde os dados
- espelho pode ser recriado

###### Paridade
- verificação básica de erros
- armazena somas de verificação separados dos dados
- reconstrução de dados sem sacrificar velocidade e capacidade igual o mirror

###### Dupla Paridade
- tolerância a falhas de até duas unidades

### Níveis de RAID

![[Pasted image 20231012092135.png]]


### Portas antigas
- Serial: 9 ou 25 pinos, periféricos como impressoras, scanners e modems, conexão de console (configurar coisas de rede), verde agua
- Paralelo: 25 pinos, impressoras, rosa escur0
- Jogo: 15 pinos, joystick, amarelo
- PS/2: 6 pinos, roxo para teclado e verde para o mouse
- Áudio: 1 pino, analógico, tem vários, sistema de som externo, microfone, alto-falante, fones

- VGA: 15 pinos, analógica, azul
- DVI: vários pinos quadrados, vídeo digital, suporta digital, analógico e ambos
- HDMI: 19 pinos, DVI + áudio e controle digital, 
- DisplayPort: 20 pinos, áudio e vídeo alta performance
### USB
- 1.0 - 1.5 Mbps a 12 Mbps
- 2.0 - 480 Mbps
- 3.0 - 5 Gbps (SuperSpeed)
- 3.2 - 20 Gbps
### Coaxial
- RG-6 - TV e internet
- RG-59 - CCTV
- BNC - áudio e vídeo

# Chapter 4
![[Pasted image 20241010203402.png]]
![[Pasted image 20241010203412.png]]
Processo de solução de problemas
1. Identificar o problema 
2. Estabelecer uma teoria de causa provável
3. Teste da teoria para determinar a causa
4. Estabelecer Plano de Ação para Resolver o Problema e Implementar a Solução
5. Verifique a funcionalidade completa do sistema e, se aplicável, implemente medidas preventivas.
6. Documentar as descobertas, as ações e os resultados.

###### Exam
- RAM insuficiente faz com que dados sejam trocados constantemente com o disco rígido


### ACPI energy state

A universal threat management (UTM) device is a security device that can provide firewall, IDS/IPS, and proxy server functionality as well as email filtering and DoS/DDoS protection.


The Advanced Configuration and Power Interface (ACPI) standard has specific sleep states that can be assigned to a device in order to conserve power. PCIe is a motherboard interface. Bluetooth and 802.11 are wireless standards.


SDRAM ( Synchronous Dynamic RAM) works in synchronization with the memory bus and has higher transfer rates because it can process overlapping instructions in parallel.

An IPv6 address is made up of 128 bits that are represented as eight blocks of four hexadecimal digits that are called hextets. Because each hexadecimal digit represents four bits, each hextet represents 16 bits. The /64 network prefix indicates that the first 64 bits, or first four hextets, represent the network portion of the address. Because there are 128 bits in an IPv6 address, this leaves the last 64 bits, or last four hextets, to represent the host identifier. The value for the last four hextets is 0607:1234:aa10:ba01.


VMware ESX/ESXi and Microsoft Hyper-V 2012 are Type 1 hypervisors that have direct access to the hardware resources. Type 1 hypervisors are more efficient than hosted architectures, and enable greater scalability, performance, and robustness. They are used to support enterprise VMs in data centers. Oracle VM VirtualBox, VMware Fusion, and Microsoft Virtual PC are host based Type 2 hypervisors.

A call center technician must provide the level of support that is outlined in the SLA for that individual customer.


DNS poisoning
SYN flood
zero-day

**What is an accurate description of asymmetric encryption technology?**
- **It is an encryption process that uses a public and private key pair to encrypt/decrypt data.**

BitLocker needs TPM to work

  
**19. A technician is troubleshooting a Windows 10 laptop infected with a virus that has damaged the master boot record. The technician has booted the laptop using the installation media and is attempting to repair the laptop from the command line interface. Which command can the technician use to repair the corrupt master boot record?**
- **bootrec /fixmbr**

**A user reports that a Windows 10 PC displays the error message “Invalid Boot Disk” during the boot process. The IT technician attempts to boot the computer and finds that the error message occurs immediately after the POST. What could be the possible cause?**
- **The MBR/GPT is corrupted.**


**The NIC cards on the new PCs are not PXE-enabled.**
wtf is pxe

wtf is dynamic disk windows


To perform a custom Windows Unattended installation, setup.exe must be run with the user options found in the answer file. Additional packages, such as applications or drivers, can be added to the answer file. The Windows System Image Manager (SIM) is used to create the setup answer file.