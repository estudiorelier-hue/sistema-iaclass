# Estrutura do prompt de vídeo

## A fórmula (um plano)

```
[quem ou o quê] + [a ação] + [onde] + [a câmera] + [luz e estilo] + [o que evitar]
```

1. **Quem ou o quê** — o assunto, com o que importa da aparência (se não houver foto de primeiro quadro).
2. **A ação** — um verbo principal, com a velocidade: "slowly turns her head toward the camera and smiles".
3. **Onde** — o lugar, a hora do dia, o que está em volta.
4. **A câmera** — um movimento, com ritmo: "the camera slowly pushes in".
5. **Luz e estilo** — fonte e direção da luz, cor, textura (filme, documental, editorial).
6. **O que evitar** — `Avoid: ...` numa frase.

60 a 100 palavras. Com foto de primeiro quadro, corte o item 1 e a aparência do item 3: descreva só o que muda.

## Câmera

| Movimento | Em inglês | Usa pra |
|---|---|---|
| parada | static shot, locked-off camera | fala, produto, quando a ação já basta |
| aproximar | slow push-in / dolly in toward [o quê] | intimidade, foco, revelação de detalhe |
| afastar | slow pull-out / dolly out revealing [o quê] | revelar o lugar, fechamento |
| girar no eixo | slow pan left/right | mostrar o ambiente |
| inclinar | tilt up/down from [x] to [y] | revelar de baixo pra cima (roupa, prédio) |
| acompanhar | tracking shot following [quem] from the side/behind | caminhada, movimento |
| lateral | lateral truck / slide left past [objeto] | parallax, produto em cena |
| orbitar | slow orbit around [o quê], 90°/180° | produto, pessoa como destaque |
| de cima | top-down / slow aerial descending over [lugar] | flat lay, paisagem |
| na mão | subtle handheld, natural micro-shake | documental, bastidor (aumenta o risco de tremido) |
| guindaste | crane up rising above [cena] | abertura, grandiosidade |

Ritmo: slow, smooth, gentle, steady, gradual, subtle. Um movimento por plano. O movimento da câmera vai numa
frase, o de quem está em cena em outra.

## Anexos e o papel de cada um

Os anexos viram `@Image1`, `@Image2`... `@Video1`... `@Audio1`... na ordem em que foram enviados. Diga sempre o
papel de cada um, senão o modelo mistura:

- `@Image1 as the first frame` — o vídeo começa exatamente nessa imagem
- `@Image2 as the last frame` — e termina nessa
- `@Image1 as the character reference` — a aparência da pessoa ou personagem
- `@Image1 as the product reference — keep its shape, color and label unchanged`
- `@Image3 as the background environment`
- `@Image2 as the style reference only — lighting and color, ignore its content`
- `Follow the camera movement of @Video1 only — ignore its content and people`
- `Use @Audio1 as background music / for the rhythm of the cuts`

A quantidade de anexos aceita muda com a versão do Seedance: confira no seletor do Magnific. Vídeo de referência
pra câmera funciona melhor curto (2 a 4 segundos mostrando só o movimento).

## Vários planos (com tempo)

Pra mais de 5 segundos com cortes, um bloco por plano:

```
Style: [estilo geral, luz e cor que valem pro vídeo inteiro]
Duration: [10s]

[00:00-00:03] Shot 1 — [tipo de plano]: [ação]. Camera: [movimento].
[00:03-00:06] Shot 2 — [tipo de plano]: [ação]. Camera: [movimento].
[00:06-00:10] Shot 3 — [tipo de plano]: [ação]. Camera: [movimento].

Keep [a pessoa / o produto] identical across all shots. Avoid: [...]
```

Planos de 2 a 4 segundos. Mesma luz e mesma cor em todos (vai no `Style`), senão parece colagem.

## Som e fala

As versões novas geram som junto. Escreva:

- **ambiente:** `Ambient sound: soft café chatter, espresso machine hiss.`
- **música:** `Background music: slow lo-fi beat, low volume.`
- **fala:** quem fala, a frase curta entre aspas e a língua:
  `She looks at the camera and says in Brazilian Portuguese: "Começa hoje."`

Fala longa sai fora de sincronia: uma frase curta por plano. Se a versão escolhida não gera som, tire essa parte e
junte a voz na edição.

## Exemplos

**Animar uma foto (imagem → vídeo), Reels**
```
@Image1 as the first frame. She slowly lifts her eyes from the laptop to the camera and gives a small, confident
smile, a strand of hair moving with the gesture. Warm late-afternoon window light from camera right stays constant.
The camera makes a slow, steady push-in toward her face. Natural real-time speed, subtle film grain.
Avoid: identity drift, face morphing, jitter, extra fingers. One continuous shot, no cuts.
```

**Produto girando (b-roll de anúncio)**
```
@Image1 as the first frame and product reference — keep its shape, color and label unchanged. The serum bottle
stands still on a wet black stone surface while a single drop runs slowly down the glass. The camera makes a slow
180° orbit around the bottle. Hard rim light from behind outlines the glass, soft cool fill from the front, 5600K,
deep shadows. Avoid: warped label, melting glass, flicker. One continuous shot, no cuts.
```

**Antes e depois (primeiro e último quadro)**
```
@Image1 as the first frame, @Image2 as the last frame. The messy desk gradually tidies itself: papers slide into a
neat stack, the mug moves to the corner, the laptop closes. Static top-down camera. Soft overcast daylight from the
window above, neutral colors. Smooth, steady transformation at a gentle pace.
Avoid: objects disappearing, morphing hands, flicker.
```

**Cena do zero (texto → vídeo), textura pra fundo**
```
Close-up of thick oat milk being poured slowly into black coffee in a matte ceramic cup, swirling into soft brown
spirals. Static macro shot from slightly above. Warm tungsten side light from camera left at 3200K, glossy
highlights on the surface, dark wooden table, shallow depth of field. Calm, natural real-time speed.
Avoid: splashes, jitter, text. One continuous shot, no cuts.
```

**Mini-sequência de 10 segundos**
```
Style: warm editorial lifestyle, golden hour light from camera left, soft amber grade, fine 35mm grain.
Duration: 10s

[00:00-00:03] Shot 1 — wide: @Image1 as character reference. She walks into a sunlit studio carrying a coffee.
Camera: slow tracking shot from the side.
[00:03-00:06] Shot 2 — medium: she sits at the desk and opens the laptop. Camera: static.
[00:06-00:10] Shot 3 — close-up: she looks up at the camera and smiles. Camera: slow push-in.

Keep her identical across all shots. Avoid: identity drift, jitter, extra fingers.
```
