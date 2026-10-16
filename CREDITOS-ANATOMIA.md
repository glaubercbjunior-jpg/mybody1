# Créditos e licença dos modelos anatômicos

O arquivo `anatomia.glb` deste repositório contém as malhas 3D dos órgãos
mostrados no avatar do MYBODY. **Essas malhas não são originais deste projeto.**

## Origem

- **Z-Anatomy** — <https://github.com/Z-Anatomy/models-of-human-anatomy>
  O atlas 3D livre de anatomia, de Gauthier Kervyn e Marcin Zielinski.
  Licença **CC BY-SA 4.0**.
- **BodyParts3D** — <https://dbarchive.biosciencedbc.jp/en/bodyparts3d/>
  The Database Center for Life Science (Japão), de onde o Z-Anatomy deriva
  seus modelos. Licença **CC-BY-SA 2.1 Japan**.

## O que foi feito aqui

As malhas originais foram, nesta ordem:

1. extraídas do arquivo Blender do Z-Anatomy;
2. soltas da hierarquia de rótulos (no arquivo original, cada peça é filha
   de um objeto de texto com escala própria — a transformação anatômica real
   está na matriz do próprio objeto);
3. convertidas de quadriláteros para triângulos, com vértices repetidos
   soldados e normais recalculadas;
4. convertidas do sistema do Z-Anatomy (+x esquerda, −y frente, +z altura em
   metros do chão) para o do avatar (y = altura/100 − 0,90, +z frente), com
   ajuste de escala medido comparando o esqueleto do Z-Anatomy (1,72 m) com
   a malha do avatar (1,80 m), fatia por fatia:
   `x' = 0,960·x`, `y' = 1,0465·z − 0,90`, `z' = −0,820·y − 0,045`;
5. deslocadas para trás, por faixa de altura, onde o tórax mais raso do
   avatar faria o órgão furar a pele (de 0 a 2,7 cm, curva suavizada);
6. simplificadas para um orçamento de triângulos por órgão, somando cerca de
   41 mil triângulos no total.

Nenhuma coordenada anatômica foi inventada: toda posição vem do modelo
original, só reescalada para o corpo do avatar.

## Obrigações que vêm junto

A CC BY-SA 4.0 exige **as duas coisas**:

1. **Atribuição** — citar a origem. Está feito aqui e dentro do app, no aviso
   de privacidade.
2. **CompartilhaIgual** — qualquer trabalho derivado dessas malhas precisa ser
   distribuído sob a **mesma licença**. Isso vale para o `anatomia.glb` e para
   versões modificadas dele.

Na prática: **o `anatomia.glb` deste repositório está sob CC BY-SA 4.0.**

Isso importa se um dia o MYBODY virar produto fechado ou pago. O resto do
código do app não fica contaminado só por carregar o arquivo, mas o arquivo
de anatomia em si não pode ser redistribuído sob licença restritiva. Se isso
se tornar um problema, os caminhos são comprar uma licença comercial de um
atlas anatômico ou encomendar malhas próprias.

## O que não vem daqui

Os valores clínicos de referência do app — estadiamento KDIGO, CKD-EPI 2021,
classificação de pressão arterial, graduação GOLD — vêm das diretrizes citadas
em cada ficha dentro do app, não destes modelos.
