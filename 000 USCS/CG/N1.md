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
- Faz calculo 256 para cada operação de ponto e armazena numa tabela
	- Em vez de fazer calculo para cada pixel especifico
## Filtragem Especial
- Olha o pixel e os ao redor dele, convolução
- Passa-baixa: smooth, todos os pixels tem o mesmo peso 1 (divide por 9 depois)
- Passa-alta: destaca bordas, usa pesos negativos e positivos, como -1 nos vizinhos e 8 no meio
	- Se for perto de 0, quer dizer que não tem borda, mas quanto mais distante for, seja -570 ou +255, quer dizer que tem uma borda

## Matrizes
### Translação - Soma
Matriz Identidade
- Mover, girar, escalar
![[Pasted image 20260401221422.png]]

vamos mover um ponto P que está na posição
(2, 3, 1). Queremos deslocá-lo:
+5 no eixo X (Direita)
+2 no eixo Y (Cima)
+10 no eixo Z (Frente)
![[Pasted image 20260401221610.png]]
### Escala - Multiplica
Diminui ou aumenta o tamanho do objeto
![[Pasted image 20260401221745.png]]

Imagine que você tem um cubo e um dos seus vértices está no ponto P = (2, 4, 3, 1).
Você quer aplicar as seguintes mudanças:
Dobrar a largura (Eixo X): sx = 2
Reduzir pela metade a altura: sy = 0.5
Manter a profundidade (Eixo Z): sz = 1
![[Pasted image 20260401221751.png]]
![[Pasted image 20260401221817.png]]
### Rotação
