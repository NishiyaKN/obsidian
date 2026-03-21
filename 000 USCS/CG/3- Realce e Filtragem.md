****# ✨ Realce e Filtragem de Imagens Digitais

### 📝 Visão Geral
O realce de imagens visa destacar características específicas ou remover artefatos para tornar a imagem mais adequada a uma tarefa (como diagnóstico médico ou reconhecimento de placas). Diferente de outras técnicas, o realce não aumenta o conteúdo de informação, mas facilita a interpretação visual ou computacional através de operações matemáticas nos pixels.

### 📍 Operações de Ponto (Histograma)
Nesta categoria, o novo valor de um pixel $s$ depende exclusivamente do seu valor original $r$, seguindo a função $s = T(r)$.

* **Brilho:** Adição ou subtração de uma constante $k$. Se $s = r + k$ ultrapassar 255, ocorre o "clipping" (truncamento no branco).
* **Contraste:** Expansão da faixa dinâmica. Imagens de baixo contraste possuem histogramas concentrados; imagens de alto contraste possuem histogramas espalhados por toda a escala (0-255).
* **Histograma:** Gráfico que contabiliza a frequência de cada tom de cinza na imagem.

### 🖼️ Filtragem Espacial (Vizinhança)
Diferente das operações de ponto, o valor do pixel processado depende dos seus vizinhos. Utiliza-se um **Kernel** (máscara ou matriz de pesos) que desliza sobre a imagem realizando uma convolução.

📊 **Comparativo de Filtros Espaciais**

| Tipo de Filtro | Objetivo | Funcionamento Técnico |
| :--- | :--- | :--- |
| **Passa-Baixa (Suavização)** | Reduzir ruído e detalhes finos (borramento). | Os pesos do kernel são positivos e a soma é normalizada (geralmente 1). Ex: Média. |
| **Passa-Alta (Realce/Bordas)** | Destacar transições bruscas e contornos. | Usa pesos positivos e negativos. Em áreas homogêneas o resultado é zero; em bordas, o valor é alto. |

### 🧮 Exemplo de Cálculo de Kernel (Filtro de Média 3x3)
Para calcular o novo valor do pixel central, multiplica-se cada pixel da vizinhança pelo peso correspondente no kernel e divide-se pelo total de pesos.

```cpp
// Lógica simplificada de aplicação de filtro de média 3x3
float aplicarFiltroMedia(int vizinhanca[3][3]) {
    int soma = 0;
    for(int i=0; i<3; i++) {
        for(int j=0; j<3; j++) {
            soma += vizinhanca[i][j];
        }
    }
    return soma / 9.0; // Normalização
}
```

### ⚠️ Tratamento de Bordas e Saturação
* **Underflow e Overflow:** Se o resultado do cálculo for menor que 0, o software arredonda para 0 (preto). Se for maior que 255, arredonda para 255 (branco).
* **Bordas da Imagem:** Como o kernel precisa de vizinhos, os pixels das extremidades da imagem exigem estratégias como ignorar a borda, replicar pixels ou preencher com zeros (padding).

### 🔍 Conclusão
O realce e a filtragem são etapas críticas no pré-processamento de visão computacional. Enquanto as operações de ponto corrigem problemas globais de iluminação e exposição, a filtragem espacial permite a manipulação de frequências da imagem, isolando ruídos ou detectando estruturas geométricas fundamentais para a análise de dados.

### 📑 Tópicos não aprofundados
* Exemplos específicos de filtros não-lineares (como o filtro de Mediana).
* Algoritmos avançados de equalização adaptativa de histograma (AHE).
* Detalhes sobre processamento no domínio da frequência (Transformada de Fourier).
* Implementação específica em bibliotecas como OpenCV.