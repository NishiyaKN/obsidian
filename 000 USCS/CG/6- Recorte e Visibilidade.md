# 📝 Computação Gráfica: Recorte e Visibilidade

## 🔍 Visão Geral
O documento aborda as técnicas e algoritmos de recorte (clipping) e determinação de visibilidade em computação gráfica. O objetivo central é otimizar a renderização descartando primitivas (linhas, polígonos) e pixels que estão fora da área de visão da câmera ou ocultos por outros objetos, economizando assim processamento computacional antes do desenho final na tela.

## 📚 Tópicos Principais

### O Processo de Recorte (Clipping)
Ocorre no Espaço de Recorte (após a projeção). O sistema verifica a posição das primitivas em relação ao Volume de Visualização (View Frustum):
- **Dentro:** A primitiva é processada normalmente.
- **Fora:** A primitiva é descartada imediatamente (rejeição trivial).
- **Parcialmente dentro:** A primitiva é cortada. Novos vértices são gerados exatamente sobre a borda da janela para manter a forma fechada.

### Visibilidade e Descarte (Culling)
Técnicas aplicadas antes da pintura dos pixels para evitar processamento inútil:
- **Back-Face Culling:** Descarta as faces dos modelos 3D que estão voltadas para "trás" (opostas à câmera), utilizando o produto escalar entre o vetor normal da face e o vetor de visão. Pode reduzir o processamento pela metade.
- **Occlusion Culling:** Descarta objetos inteiros que estão escondidos atrás de outros maiores (ex.: uma árvore atrás de um prédio).

### Remoção de Superfícies Ocultas (Z-Buffering)
Após o recorte, a GPU precisa determinar qual objeto está na frente do outro, pixel a pixel. Para isso, utiliza-se o Z-Buffer (Depth Buffer).

```python
# Lógica conceitual do Z-Buffer
if Z_novo < Z_atual:
    Z_atual = Z_novo     # Atualiza a profundidade
    Cor_atual = Cor_nova # Sobrescreve o pixel com a nova cor
else:
    # O pixel está atrás de algo já desenhado e é descartado
    descartar_pixel()
```

## 📊 Algoritmos de Recorte

| Algoritmo              | Foco Primário | Método / Estratégia Principal                                                                                                                                                           |
| :--------------------- | :------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Cohen-Sutherland**   | Linhas        | Divide a tela em 9 regiões e usa *Outcodes* (códigos de 4 bits). Avalia operações lógicas (`AND`/`OR`) para rejeição ou aceitação trivial.                                              |
| **Sutherland-Hodgman** | Polígonos     | Pipeline do tipo "Dividir para Conquistar". Corta o polígono contra uma borda por vez (esquerda, direita, cima, baixo), criando novos vértices ao entrar/sair da janela.                |
| **Liang-Barsky**       | Linhas        | Altamente eficiente matematicamente. Usa equações paramétricas da reta baseadas no tempo/progresso ($u$). Determina a visibilidade cruzando limites de entrada ($u_1$) e saída ($u_2$). |

## 🎯 Conclusão
A eficiência de um motor gráfico moderno depende diretamente da sua capacidade de não processar o que o usuário não pode ver. A combinação de algoritmos clássicos de recorte matemático com técnicas de culling e testes de profundidade em hardware (Z-Buffer) garante que o poder computacional da GPU seja gasto exclusivamente nos pixels que formarão a imagem visível final.

## ✂️ Tópicos não aprofundados
- Cálculos algébricos passo a passo para encontrar as coordenadas das intersecções no método de Cohen-Sutherland.
- Casos iterativos detalhados de substituição de vértices pelo algoritmo de Sutherland-Hodgman.
- Demonstração da fórmula de equações paramétricas e cálculo das variáveis $\Delta x$, $\Delta y$ e limites $u$ no Liang-Barsky.
- Exercício prático numérico detalhando a sobreposição sequencial de janelas para testar a profundidade no Z-Buffer.ggkkk