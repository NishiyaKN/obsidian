## Amostragem
- fmax: frequência do sinal original - ciclo completo é a distância entre o início de um detalhe e o início do próximo
	- 1. Se uma camisa tem listras de 1mm (1mm preta, 1mm branca), o ciclo total é de 2mm.
	- 2. A frequência desse sinal é 1 / 2mm = 0,5 ciclos por milímetro.
- fs: frequência de amostragem - resolução do equipamento, quantidade de amostras em um determinado espaço
	- Se o sensor da sua câmera tem 10 pixels a cada milímetro, a sua frequência de amostragem (fs) é de 10 amostras/mm.
- nyquist: fs > 2 * fmax
	- A quebra desse teorema resulta em aliasing (ondas estranhas)

## Calculo de peso de arquivo
Tamanho em bits = W * H * D
- Para bytes, divide por 8, para Kbytes divida por 1024

## Limiarização
- Operação de ponto, transforma imagem em binário, preto ou branco, de cordo com o valor de limiar
## LUT
- Look-Up Table
- Faz calculo 256 para cada