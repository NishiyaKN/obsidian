- Precisa de barramento de dados de alta performance, como SCSI ou SAS.
- Cabos SCSI tem de 25 a 68 pinos dependendo da versão SCSI
- SAS usa o mesmo padrão de pinagem dos HDDs SATA, mas consegue conectar, por exemplo 4 discos no mesmo cabo
	- SAS 1 -> 3 Gb/s em 2004
	- SAS 2 -> 6 Gb/s em 2009
	- SAS-3 -> 12 Gb/s em 2013
	- SAS-4 -> 22,5 Gb/s em 2017
	- SAS-5 -> em desenvolvimento, velocidade aproximada de 45Gb/s

### RAID 5
- Distribuição de dados em vários discos (stripping)
- Disco de paridade
- Se danificar o disco 3 por exemplo, coloca um disco novo em hot  swap e o conteúdo será regerado nesse disco novo. Tem um bom custo benefício em questão de uso de discos e performance para servidores de médio de grande porte.
- Se um disco falhar, é possível continuar a usar normalmente a matriz
- Se danificar o disco de paridade, teremos problemas, pois há apenas um disco de paridade.
- No mínimo um disco de pariadade e 2 de dados

### RAID 6
- Mesma coisa que o RAID 5, mas:
- Discos de paridade são duplicados
- No mínimo 4 discos, 2 de paridade e 2 de dados.

### RAID 10
- Para empresas pequenas, ou talvez pequena-média
- Separação de setores em discos diferentes de dados
- Espelhamento de dois em dois
- Mais barato usar o RAID 10 do que o RAID 5 ou 6
- Não tem paridade, mas tem um nível de seguraça boa até
- Chance de perder dados é baixa
- Bom custo benefício

- Barramento SAS integrado com o RAID -> maior benefício é uso para seridores críticos, como de comércio eletrônico, usinas ou empresas que devem estar ativas durante 24h, precisa de alta disponibilidade.
- Backup é exigido por lei