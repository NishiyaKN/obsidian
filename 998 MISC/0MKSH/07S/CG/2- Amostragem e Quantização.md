# 📉 Amostragem e Quantização de Imagens Digitais

### 📝 Visão Geral
Este material explora os processos fundamentais de digitalização de uma imagem: a **Amostragem** (discretização do espaço/resolução) e a **Quantização** (discretização da intensidade/cor). O conteúdo foca na transição do mundo físico analógico (contínuo) para o digital (discreto), abordando os limites matemáticos necessários para evitar artefatos visuais e o cálculo de armazenamento de dados.

### 📍 Amostragem (Sampling): O Espaço
A amostragem define a **resolução espacial** da imagem. Consiste em dividir a cena contínua em uma grade de pontos (pixels).
* **Funcionamento:** Quanto maior o número de amostras (pixels), maior a fidelidade aos detalhes finos da cena original.
* **Subamostragem:** Ocorre quando há poucas amostras para representar os detalhes, resultando em uma imagem "pixelizada".

### 🎨 Quantização: A Intensidade
A quantização define a **profundidade de cor** (Bit Depth). É o processo de atribuir um valor numérico finito à intensidade de luz capturada em cada amostra.
* **Escala de Bits:** Determina quantos tons diferentes um pixel pode assumir ($2^n$).
* **Erro de Quantização:** Se a profundidade de bits for baixa, ocorre o efeito de **falso contorno** ou **posterização** (degradês suaves tornam-se degraus visíveis).

📊 **Relação de Profundidade de Bits**

| Bits por Pixel | Níveis de Tons/Cores | Aplicação Comum |
| :--- | :--- | :--- |
| **1 bit** | 2 ($2^1$) | Binário (Preto e Branco puro) |
| **8 bits** | 256 ($2^8$) | Padrão para tons de cinza ou JPEG (por canal) |
| **24 bits** | ~16,7 milhões ($2^{24}$) | True Color (8 bits para cada canal R, G e B) |

### 📏 Teorema de Nyquist e Aliasing
Para que uma imagem digital represente fielmente a realidade sem inventar padrões inexistentes, deve-se seguir o Teorema de Nyquist.
* **A Regra:** A frequência de amostragem ($f_s$) deve ser maior que o dobro da maior frequência ($f_{max}$) presente no sinal: $f_s > 2 \cdot f_{max}$.
* **Aliasing (Moiré):** Se a regra for quebrada (ex: sensor com poucos pixels para capturar detalhes muito finos como listras de uma camisa), surgem padrões ondulados estranhos ou serrilhados.

### 💾 Cálculo de Armazenamento
Para Ciência da Computação, é vital calcular o peso de arquivos não comprimidos (RAW/BMP).

```cpp
// Exemplo lógico do cálculo de tamanho em bits
long calcularTamanhoBits(int largura, int altura, int profundidade) {
    return (long)largura * altura * profundidade;
}

// Para converter para Bytes: resultado / 8
// Para Kbytes: (resultado / 8) / 1024
```

### 🔍 Conclusão
A qualidade de uma imagem digital é limitada pela sua resolução (amostragem) e sua paleta de cores (quantização). O entendimento do Teorema de Nyquist é crucial para o desenvolvimento de sistemas de captura e processamento, garantindo que a discretização não introduza artefatos que comprometam a análise de dados visuais ou a experiência do usuário.

### 📑 Tópicos não aprofundados
* Exemplos específicos de densidade de pixels de sensores de câmeras comerciais.
* Demonstração visual detalhada de posters (posterização) em imagens de baixa quantização.
* Diferenças matemáticas profundas entre algoritmos de reconstrução de sinal.
* Discussão sobre compressão de dados (mencionada apenas como contexto para o cálculo de tamanho).