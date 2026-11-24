# Design: ilustração, ícone, padrão e peça de marca em série

Aqui não tem rosto pra travar: o que precisa ficar igual é o estilo. A primeira peça sai bonita por sorte; a
décima só sai com cara da mesma marca se o estilo estiver escrito e repetido.

## 1. Registrar o estilo (uma vez por série ou marca)

Se a imagem é da marca dela, comece pelo `marca/design-system.md` e pelo `marca/tokens.css`: a paleta vem de lá,
com os hex reais. Se ela mandou referência, extraia o estilo da referência e proponha de volta antes de travar.

Defina:

1. **Estilo de arte** — vetor chapado, 3D isométrico, aquarela, massinha, papel recortado, traço, risografia,
   pixel art, render 3D. Nunca "moderno" ou "bonito".
2. **Paleta** — principal, secundária, destaque e fundo, cada uma com hex e onde aparece. Fechada (só essas) ou com
   variação de tom? Degradê pode?
3. **Linha e forma** — espessura do traço, raio dos cantos, geométrico ou orgânico.
4. **Textura** — chapado, grão (quanto), papel, ruído.
5. **Ícones** (se tiver) — contorno, sólido ou duotone.
6. **Tipografia** (só se aparecer texto) — peso, tratamento.
7. **Grade e respiro** — regra de composição, quanto espaço vazio.
8. **Trava de consistência** — os 2 a 4 elementos que se repetem em toda peça (mesma sombra, mesmo traço, mesmo
   ângulo de luz isométrica). É o campo mais importante.

Mostre em português, peça o "ok" e salve em `imagens/estilos/<nome>.md` (no cliente, `clientes/<nome>/imagens/estilos/`):

```markdown
# Estilo <nome>

Pra quê: <feed da marca, ícones do site, capas do curso>
Vem de: <marca/design-system.md | referência em imagens/estilos/<nome>/ | do zero>

## design_system (em inglês, entra no prompt como está)
(o bloco design_system do JSON abaixo, preenchido)

## O que funcionou
- (data) o que deu certo e o que deu errado
```

## 2. Gerar

Antes de escrever, leia o estilo e liste a trava de consistência em uma linha. Pense a peça: o que mostra e pra
quê, o enquadramento e o ponto focal, se o acabamento pedido combina com o estilo (sombra realista num vetor
chapado não combina: avise antes de gerar) e quais itens da trava valem pra esta peça.

```json
{
  "model_target": "nano_banana_2",
  "mode": "non_person_illustration",
  "subject": {
    "type": "icon / illustration / scene / product_mockup / pattern / infographic / background / non-human character",
    "description": "exact, unambiguous description of what is depicted",
    "reference_image": "@img1 — only if following a style reference"
  },
  "design_system": {
    "art_style": "one specific style",
    "color_palette": {
      "primary": "#HEX — where it is used",
      "secondary": "#HEX — where it is used",
      "accent": "#HEX — where it is used",
      "background": "#HEX — where it is used",
      "rules": "closed palette or tonal variation allowed; gradients yes or no"
    },
    "line_and_shape_language": "stroke weight, corner radius, geometric or organic",
    "texture_and_grain": "flat / grain % / paper / noise",
    "iconography_rules": "outline / solid / duotone (omit if not relevant)",
    "typography_style": "weight and treatment (omit if there is no text)",
    "spacing_and_grid": "composition rule, grid, negative space",
    "consistency_lock": ["element 1 repeated in every piece", "element 2", "element 3"]
  },
  "composition": { "framing": "full scene / centered object / cropped detail", "focal_point": "where the eye lands first", "layout": "centered / rule of thirds / asymmetric / grid", "background_treatment": "solid / gradient / transparent / textured / full scene" },
  "rendering": { "lighting_or_shading": "flat / soft cel-shading / isometric directional light / 3D studio light", "depth": "flat 2D / layered 2.5D / full 3D", "material_finish": "matte / glossy / paper / glass / metal" },
  "environment_or_scene": { "setting": "where (if applicable)", "elements": ["detail 1", "detail 2", "detail 3"], "atmosphere": "overall feel" },
  "technical": { "aspect_ratio": "1:1 / 4:5 / 9:16 / 16:9", "resolution": "1K / 2K / 4K", "background": "transparent or opaque" },
  "negative": "photorealistic rendering, human faces, watermark, text artifacts, inconsistent line weight, off-palette colors, cluttered composition, blurry edges"
}
```

- `model_target`: `nano_banana_2` pra série (rápido e mantém o estilo); `nano_banana_pro` pra uma peça complexa
  (infográfico com dado real, muito texto).
- Fundo transparente: muitas vezes sai um fundo sólido. Peça fundo de uma cor só, contrastante, e recorte depois
  num removedor de fundo.
- Série: gere a primeira, aprove, e anexe ela como `@img1` nas próximas com
  `"match the style of @img1 exactly"`, além do bloco `design_system` inteiro.

## Antes de entregar

- [ ] `art_style` sem ambiguidade
- [ ] Paleta com hex e o papel de cada cor (os da marca, se é da marca)
- [ ] `consistency_lock` com 2 a 4 itens concretos
- [ ] `rendering` coerente com `art_style`
- [ ] `negative` com "human faces" quando não pode ter gente
- [ ] JSON válido, sem placeholder, sem valor em português
