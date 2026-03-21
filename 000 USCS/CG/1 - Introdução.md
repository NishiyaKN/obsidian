### 📝 Visão Geral
Este conteúdo apresenta os fundamentos da disciplina de Computação Gráfica (CG) e Processamento de Imagens (PI). O objetivo central é capacitar o estudante a compreender o pipeline gráfico, manipular transformações geométricas em ambientes 2D e 3D, e aplicar técnicas de tratamento, restauração e compressão de imagens digitais, fornecendo a base teórica e prática necessária para o desenvolvimento de sistemas interativos e visualização de dados.

### 📐 Fundamentos e Pipeline Gráfico
A disciplina aborda a conversão de dados abstratos em representações visuais através de dispositivos gráficos. O fluxo de trabalho (pipeline) envolve desde a definição de primitivas geométricas até a exibição final no dispositivo.

* **Sistemas de Coordenadas:** Essenciais para o posicionamento e orientação de objetos no espaço virtual.
* **Transformações Geométricas:** Uso de matrizes para realizar translação, rotação e escala em objetos 2D e 3D.
* **Representação Visual:** Diferenciação entre o modelo matricial (pixels) e o vetorial (escalável).

### 🎨 Padrões de Cores e Imagens
A representação digital das cores é fundamental para a fidelidade visual e eficiência de armazenamento.

📊 **Comparativo de Modelos de Cor**

| Modelo   | Aplicação Principal           | Características                                                  |
| :------- | :---------------------------- | :--------------------------------------------------------------- |
| **RGB**  | Telas e dispositivos digitais | Aditivo (Red, Green, Blue). Baseado em luz.                      |
| **CMYK** | Impressão e artes gráficas    | Subtrativo (Cyan, Magenta, Yellow, Black). Baseado em pigmentos. |
| **HSV**  | Edição e design               | Baseado na percepção humana (Hue, Saturation, Value/Brilho).     |

### 🖼️ Processamento e Restauração de Imagens
O processamento foca em melhorar a qualidade visual ou extrair informações úteis de imagens existentes.

* **Amostragem e Quantização:** Processo de converter uma imagem contínua em pontos discretos (pixels) e níveis de cor.
* **Realce e Filtragem:** Técnicas para ajuste de contraste, nitidez e redução de ruídos.
* **Restauração:** Uso de modelos matemáticos para corrigir degradações conhecidas (como borrões).
* **Compressão:** Redução do tamanho do arquivo através de algoritmos como RLE, LZW e Huffman, podendo ser com ou sem perda de dados.

### 💻 Exemplo de Estrutura de Pixel
Um pixel em alta fidelidade geralmente armazena informações de profundidade de cor (tipicamente 24 bits para True Color).

```cpp
struct Pixel {
    unsigned char R; // 0-255
    unsigned char G; // 0-255
    unsigned char B; // 0-255
};
```

### 🔍 Conclusão
A disciplina integra matemática aplicada (geometria e matrizes) com algoritmos de alto desempenho para criar interfaces homem-computador eficazes. O domínio dessas técnicas é o pilar para áreas avançadas como Visão Computacional, Realidade Virtual e Inteligência Artificial aplicada ao reconhecimento de padrões visuais.

### 📑 Tópicos não aprofundados
* Cronograma detalhado de aulas e datas específicas de avaliações.
* Critérios detalhados de cálculo da média final (N1, N2, AF, AI).
* Regras de frequência e normas institucionais.
* Bibliografia básica e complementar da disciplina.