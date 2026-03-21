### 📝 Visão Geral
As transformações geométricas são a base matemática para manipular objetos em ambientes virtuais. Elas permitem alterar a posição, o tamanho e a orientação de modelos 3D e 2D, movendo-os de seu espaço local (Model Space) para o mundo (World Space) e, finalmente, para a perspectiva do observador (View Space). O uso de matrizes é essencial para que essas operações sejam realizadas de forma eficiente pela GPU.

### 🔄 Espaços de Coordenadas
O objeto percorre diferentes "universos" matemáticos até ser renderizado:
1. **Model Space:** Onde o objeto é criado (seu centro é o 0,0,0).
2. **World Space:** Onde o objeto é posicionado no mapa global.
3. **View Space:** Reorienta o mundo inteiro tendo a câmera como o novo centro do universo. Se a câmera "anda" para a frente, o sistema desloca o mundo para trás.

### 🛠️ Tipos de Transformações
As transformações modificam os vértices dos objetos através de operações matriciais.



📊 **Comparativo de Transformações Principais**

| Transformação | Função | Característica Matemática |
| :--- | :--- | :--- |
| **Translação** | Move o objeto no espaço. | Adição de valores às coordenadas (ou multiplicação em coordenadas homogêneas). |
| **Escala** | Altera o tamanho (estica ou encolhe). | Multiplicação das coordenadas por um fator *s*. |
| **Rotação** | Gira o objeto em torno de um eixo. | Usa funções trigonométricas (Seno e Cosseno). |
| **Cisalhamento** | "Entorta" o objeto. | Uma coordenada é alterada proporcionalmente ao valor de outro eixo. |

### 🧮 A Lógica da Rotação e Cisalhamento
* **Rotação:** O valor negativo do Seno na matriz (-sin) garante que a distância do ponto até a origem seja preservada (o objeto não deforma, apenas gira). O sinal negativo no topo define o sentido anti-horário.
* **Cisalhamento (Shear):** Os valores de cisalhamento ocupam as posições que normalmente seriam zero na matriz identidade. Quanto maior a coordenada de um eixo (ex: Y), mais o ponto correspondente é "empurrado" no outro eixo (ex: X).

### 💻 Exemplo de Matriz de Escala (Pseudocódigo)
Na computação gráfica, utilizamos matrizes 4x4 (coordenadas homogêneas) para combinar todas as transformações em uma única operação.

```cpp
// Representação conceitual de uma Matriz de Escala 2D
float matrizEscala[3][3] = {
    {sx,  0,  0},
    { 0, sy,  0},
    { 0,  0,  1}
};

// Novo Ponto = Ponto Original * Matriz
```

### 🔍 Conclusão
As transformações geométricas não são apenas movimentos, mas sim mapeamentos matemáticos entre espaços. Para um desenvolvedor de CG, entender a ordem das transformações (ex: rotacionar antes de transladar produz resultados diferentes de transladar antes de rotacionar) é crucial para evitar comportamentos inesperados na cena e garantir que a projeção em perspectiva seja matematicamente coerente.

### 📑 Tópicos não aprofundados
* Dedução matemática completa das funções de Seno e Cosseno nas matrizes.
* Diferença entre coordenadas cartesianas e coordenadas homogêneas (W).
* Multiplicação de matrizes para composição de transformações (MSR - Model, Scale, Rotation).
* Transformação de Projeção (transforma o volume de visualização em um cubo unitário).