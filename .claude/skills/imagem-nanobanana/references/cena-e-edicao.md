# Cena e edição

## Cena: produto, comida, ambiente, objeto

Sem pessoa pra travar, o prompt pode ser texto corrido. A ordem que funciona vai do geral pro detalhe:

```
[estilo e clima] + [o assunto, com material e textura] + [ambiente e fundo] + [luz] + [lente e enquadramento] + [cor] + [o que evitar]
```

Passe pra JSON quando tiver muitos elementos pra posicionar (mesa posta com dez objetos, vitrine, cenário de época).

### Modelos

**Produto em fundo limpo (e-commerce)**
```
Professional e-commerce photograph of [produto, com material, cor e acabamento].
Seamless pure white background (RGB 255,255,255) with a soft natural contact shadow under the product.
Large softbox key light from 45° camera left at 5600K, white bounce card camera right filling the shadows,
highlighting [textura: the brushed metal, the fabric weave, the condensation on the glass].
Shot on a 100mm macro lens at f/8, everything sharp edge to edge, eye-level angle, product centered with generous margins.
True-to-life color, neutral grade, crisp detail.
Avoid: harsh reflections, color cast, floating product, warped label, extra objects, watermark.
```

**Produto em cena (lifestyle)**
```
Editorial still life of [produto] placed on [superfície: travertine countertop, linen tablecloth, oak shelf],
surrounded by [2 a 4 objetos que contam o contexto]. Late-afternoon window light from camera right at 4200K,
long soft shadows falling left, warm highlights on [parte do produto]. 50mm lens at f/2.8,
product sharp in the left third, background softly blurred. Muted warm palette of [cores], low saturation,
gentle contrast, in the style of a slow-living lifestyle magazine.
Avoid: clutter, plastic look, oversaturated colors, text, watermark.
```

**Ambiente (escritório, estúdio, loja)**
```
Wide interior photograph of [espaço], [estilo de decoração e materiais].
[Fonte de luz principal e secundária, com direção e Kelvin]. 24mm lens at eye level,
vertical lines kept straight, [o que fica em primeiro plano e o que fica no fundo].
[Paleta e referência]. Avoid: distorted perspective, empty sterile look, people, text.
```

**3D, miniatura, diorama**
```
Isometric 3D render of [assunto] as a miniature diorama on a [base], rendered in Cinema 4D with
[matte clay / glossy PVC / soft plastic] materials, toy-like scale, soft studio lighting from top left,
[paleta com hex], clean [cor] background, subtle ambient occlusion.
Avoid: realistic textures, clutter, text, harsh shadows.
```

### Texto dentro da imagem

O Nano Banana Pro escreve bem quando o texto é curto e bem especificado:

- o texto exato entre aspas, como ela escreveu: `the headline "Agenda aberta" ...`;
- a fonte (serifada, sem serifa, condensada), o peso, a cor (hex), o tamanho relativo e a posição;
- o papel do texto (título de capa, etiqueta, placa na parede).

Mais de uma linha ou texto pequeno costuma sair errado. Nesses casos, gere a imagem com o espaço reservado
("clean empty area in the top third for a headline") e escreva o texto por cima depois.

## Edição de uma imagem que já existe

Anexe a imagem como `@img1` e diga, nesta ordem: **o que muda**, **o que fica exatamente igual** e **como a mudança
se encaixa** (luz, sombra, perspectiva da imagem original).

**Trocar o fundo**
```
Keep the person/product in @img1 exactly as it is — same pose, face, clothing, edges and lighting on the subject.
Replace only the background with [novo fundo, com luz e profundidade]. Match the new background's light direction
and color temperature to the light already on the subject, add a natural contact shadow, blend the edges seamlessly.
Avoid: cut-out halo, mismatched lighting, changed face, changed proportions.
```

**Mudar a proporção (expandir a imagem)**
```
Extend @img1 from [4:5] to [9:16] by continuing the scene naturally above and below.
Keep every existing pixel of the original unchanged. Continue [o chão, a parede, o céu] with the same texture,
light and perspective. Avoid: repeated patterns, new people, visible seams, stretched subject.
```

**Trocar a roupa**
```
Keep the person in @img1 identical — face, hair, body, pose, background and lighting.
Change only the outfit to [roupa: peça, tecido, cor, caimento], with folds and shadows that follow her pose
and the existing light. Avoid: changed face, changed body shape, floating fabric, extra limbs.
```

**Limpar (tirar gente ou objeto do fundo)**
```
Remove [o que tirar] from @img1 and fill the area with the background that would naturally be behind it
([continuação do que está em volta]). Keep everything else unchanged. Avoid: smudges, repeated textures, ghosting.
```

**Mudar o estilo mantendo a pessoa**
```
Recreate @img1 as [estilo: 35mm film photo from the 90s / editorial black and white / watercolor illustration],
keeping the composition and the person's identity — [os 5 traços, se ela estiver registrada].
[Características do estilo: grão, cor, luz, textura]. Avoid: identity drift, [o que o estilo costuma estragar].
```

Edição que envolve rosto de pessoa registrada leva os 5 traços do dossiê também.
