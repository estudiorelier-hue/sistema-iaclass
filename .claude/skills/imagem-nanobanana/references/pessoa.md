# Pessoa: rosto igual em todas as imagens

O Nano Banana mantém o rosto quando recebe a foto **e** uma descrição precisa do que não pode mudar. Só a foto, ele
"melhora" a pessoa: afina o nariz, clareia a pele, deixa simétrica. O dossiê existe pra travar isso.

## 1. Registrar (uma vez por pessoa)

Peça 2 ou 3 fotos nítidas (rosto de frente com luz de janela, uma de meio corpo, uma sorrindo) e o nome que vai
identificar ela. Analise as fotos nestas dez categorias. Seja exato: "olhos castanhos" não trava nada,
"castanho-escuro quase preto, amendoados, levemente caídos no canto externo" trava.

1. **Rosto** — formato (oval, redondo, quadrado, coração, diamante), mandíbula, queixo, maçãs
2. **Olhos [crítico]** — cor exata com variações, formato, tamanho, distância entre eles
3. **Sobrancelhas** — formato, espessura, cor
4. **Nariz [distintivo]** — dorso, ponta, tamanho
5. **Boca e lábios** — espessura de cima e de baixo, largura, arco do cupido
6. **Cabelo [crítico]** — cor detalhada (raiz, luzes), textura, corte, volume, comprimento
7. **Barba** (se tiver) — tipo, densidade, cor, % de grisalho
8. **Pele [crítico]** — tom, subtom (quente, frio, neutro, oliva), textura (poros, sardas, marcas)
9. **Corpo** — biotipo real, postura, ombros, pescoço. Nunca "magra" por padrão: o corpo é o da foto
10. **Marcas** — pintas, cicatrizes, tatuagens, piercings, linhas de expressão, com o lugar exato

Depois, escolha os **5 traços principais**: os que fazem alguém olhar e dizer "é ela". Eles entram em todo prompt.

Mostre o dossiê em português, peça o "ok" e salve em `imagens/pessoas/<nome>.md` neste formato:

```markdown
# <Nome>

Fotos de referência: `imagens/pessoas/<nome>/` (anexar a 1 como @img1 em toda geração)
Autorização de uso da imagem: <sim, dela mesma | sim, contrato do cliente | perguntar>

## 5 traços principais (em inglês, entram no prompt como estão)
1. ...
2. ...

## Dossiê
(as dez categorias, em inglês, uma linha cada)

## O que funcionou
- (data) o que deu certo e o que deu errado com essa pessoa
```

Guarde as fotos em `imagens/pessoas/<nome>/`. Quando a pessoa mudar (cortou o cabelo, pintou), atualize o dossiê
em vez de criar outro.

## 2. Gerar

Antes de escrever, leia o arquivo da pessoa e liste os 5 traços em uma linha. Depois pense a cena em quatro pontos:
o conceito (o que a imagem conta), a fotografia (clima, referência, hora do dia), a técnica (luz, ângulo, cor,
enquadramento) e o realismo (pele, cabelo, lente, de onde vem o brilho no olho).

### JSON (padrão pra pessoa)

Todo campo com conteúdo específico da cena. Nada de copiar o texto de exemplo nem deixar "N/A". Valores em inglês.

```json
{
  "model_target": "nano_banana_pro",
  "mode": "hyperrealistic_person",
  "identity": {
    "reference_name": "{NOME}",
    "source_image": "@img1",
    "critical_features": [
      "trait 1 — exact description from the dossier",
      "trait 2 — skin tone and undertone",
      "trait 3 — face shape and bone structure",
      "trait 4 — distinctive proportion or feature",
      "trait 5 — harmonizing overall descriptor"
    ],
    "face_shape": "shape + jawline + cheekbones",
    "eyes": { "color": "exact color with variations", "shape": "shape, size, spacing", "expressiveness": "how the eyes behave in this expression" },
    "eyebrows": "shape, thickness, exact color",
    "nose": "bridge, tip, size",
    "mouth_lips": "thickness, width, cupid's bow",
    "hair": { "color": "detailed color", "texture": "straight / wavy / curly / coily", "style": "current cut and styling", "strand_detail": "volume, flyaways, natural shine" },
    "skin": { "tone": "skin tone", "undertone": "warm / cool / neutral / olive", "texture": "visible pores, freckles, marks" },
    "physique": "honest build, posture, shoulders, neck — as in the dossier",
    "distinctive_marks": "moles, scars, tattoos, piercings, expression lines — exact location",
    "expression": "emotional register of this scene"
  },
  "hyperrealism_controls": {
    "skin_micro_texture": "visible pores on nose and forehead, subtle oil sheen on the T-zone, faint under-eye texture, no airbrushing",
    "catchlights": "catchlights matching the key light in size, shape and position — not symmetric studio dots",
    "hair_strand_rendering": "individual flyaways at hairline and crown, natural frizz, no CGI-smooth helmet hair",
    "subsurface_scattering": "light translucency through ear cartilage, nostril edges, thin skin near the eyes",
    "sensor_and_lens_simulation": "shot on [lens/aperture], natural falloff, slight chromatic aberration at the edges, [film or ISO grain]",
    "micro_expression": "natural facial asymmetry, real muscle tension around eyes and mouth"
  },
  "shot": { "type": "close-up / medium portrait / environmental wide / lifestyle", "angle": "eye level / low / high / three-quarter", "lens": "35mm / 50mm / 85mm / 135mm", "framing": "subject position, rule of thirds, negative space", "dof": "what is sharp and what is soft" },
  "subject": { "pose": "body position, weight, orientation", "action": "what she is doing right now", "wardrobe": "garments, fabrics, colors, fit, condition, accessories", "body_type": "honest build, same as the dossier" },
  "lighting": { "source": "specific source", "quality": "hard / soft / diffused / specular", "temperature": "Kelvin value + descriptor", "direction": "exact angle and relationship", "effect": "what the light does to the face and body" },
  "environment": { "setting": "exact place and time of day", "background": "what is behind and how it renders", "elements": ["prop 1", "prop 2", "texture or material", "atmosphere: haze, dust, light rays"], "atmosphere": "how the space feels" },
  "aesthetic": { "style": "editorial / lifestyle documentary / fashion / fine art portrait", "color_grade": "palette + saturation + contrast", "mood": "2 to 4 adjectives", "reference": "photographer, director or campaign as a style anchor" },
  "technical": { "aspect_ratio": "4:5 / 9:16 / 1:1 / 16:9", "resolution": "2K / 4K" },
  "negative": "identity drift, altered facial structure, slimmed face, lightened skin, plastic or airbrushed skin, overly symmetric face, waxy skin, cartoon effect, extra fingers, distorted anatomy, watermark, text overlay"
}
```

- `model_target`: `nano_banana_pro` pra peça única hiper-realista; `nano_banana_2` pra série e variação rápida.
- `negative`: sempre com o bloco de identidade acima; acrescente o da cena (`overexposed sky` ao ar livre,
  `oversaturated neon` à noite).
- Mais de uma pessoa na cena: um bloco `identity` por pessoa (`@img1`, `@img2`) e diga quem está onde.

### Texto corrido (quando ela pedir, ou pra ferramenta que não lê JSON bem)

Mesma exigência, em parágrafos, sem rótulos nem colchetes:

> Using the provided image of the person (@img1), create a [tipo de imagem] where she appears as [papel]. It is
> crucial that she is a perfect likeness of {NOME}, keeping her [traço 1], [traço 2], [traço 3], [traço 4] and
> [traço 5].
>
> [Roupa: material, cor, caimento]. [Pose e ação]. [Expressão]. [Ambiente e fundo].
>
> [Luz: fonte, direção, qualidade, Kelvin, efeito e sombra].
>
> [Composição: plano, ângulo, lente, profundidade de campo].
>
> [Cor: paleta, saturação, contraste, referência]. Avoid: [negativo].

## 3. Pessoa + imagem de referência

Quando ela manda a foto da pessoa **e** uma referência ("quero uma foto assim"):

1. A pessoa: dossiê registrado (ou registrar agora).
2. A referência: só técnica e estética. **O rosto da referência é ignorado.** Tire dela: plano, ângulo, lente,
   pose (como energia, não como identidade), luz, ambiente, estilo de roupa, paleta, clima.
3. O prompt trava a identidade da pessoa e aplica a técnica da referência. Diga o papel de cada anexo:
   `"@img1 is the person — keep her identity. @img2 is only a reference for lighting, pose and composition — ignore its face."`

## Antes de entregar

- [ ] Dossiê relembrado, 5 traços no `critical_features`, nenhum vago
- [ ] `hyperrealism_controls` escrito pra esta cena, não copiado
- [ ] Luz com fonte, direção, qualidade, Kelvin e efeito
- [ ] Paleta com saturação, contraste e referência
- [ ] `negative` com o bloco de identidade
- [ ] JSON válido, sem placeholder, sem valor em português
