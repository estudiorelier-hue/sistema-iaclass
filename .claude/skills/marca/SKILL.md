---
name: marca
description: Monta ou atualiza o design system (marca/design-system.md, tokens.css e prova.html) do zero, de um manual de marca, de um produto irmão ou de um export do Claude Design, pra sua marca ou pra um cliente. Use em /marca, "design system", "identidade visual", "cores e fontes", "manual da marca".
---

# /marca

O design system são as decisões de design escritas num lugar só, que o Claude lê antes de construir qualquer coisa
visual. Com ele na pasta, tudo já nasce com a cara certa. Sem ele, cada página sai de um jeito.

## Qual marca

- **A minha:** `marca/` na raiz.
- **De um cliente:** `clientes/<nome>/marca/`. Se não existe, crie copiando os três arquivos neutros de `marca/`
  (`design-system.md`, `tokens.css`, `prova.html`) e as pastas `logo/`, `fontes/`, `referencias/`.
- Nunca misture: um design system por marca. Dentro de `clientes/<nome>/`, vale o dele.

Leia o design system atual antes de mexer. Se já foi montado (sem o aviso `<!-- pendente -->`), é atualização:
mude só o que ela pediu e registre a decisão no fim do arquivo.

## As quatro entradas

**1 · Do zero.** Peça material, não adjetivo: prints e links do que ela gosta e do que odeia (em
`marca/referencias/`, cada um com uma linha do porquê), o logo, as fontes se tiver. Leia as imagens. Depois, até
quatro perguntas fechadas: fundo claro ou escuro; uma cor principal (ou "escolhe pra mim"); a sensação em duas ou
três palavras dela; tem fonte ou escolhemos uma livre. Proponha a paleta com o papel de cada cor, as fontes
(Google Fonts livres, ou as dela), o espaço, os tipos de seção que o negócio dela usa, o movimento e o proibido
(o que ela odiou vai aqui). Mostre antes de gravar.

**2 · Do manual de marca.** Ela joga o PDF ou as imagens na `entrada/`. Leia e extraia cores (em hex), fontes,
regras de uso e o que o manual proíbe. Escreva o design system a partir disso e liste o que o manual não diz
(espaço, movimento, tipos de seção) com uma proposta pra cada.

**3 · De um produto irmão.** Leia o `design-system.md` e o `tokens.css` de outra pasta (outro cliente, outro
produto), copie e mude o que ela disser. Diga o que ficou igual e o que mudou.

**4 · Do Claude Design.** Ela exportou de lá um zip ou pasta com `styles.css`, `guidelines/`, `components/` e
`assets/`. Guarde o export inteiro em `marca/claude-design/`, leia `styles.css` e as guidelines, mapeie pros nossos
tokens e copie fontes e logo pra `fontes/` e `logo/`. O export fica como fonte; o nosso formato é o que as skills leem.

## O que escrever

- **`design-system.md`**, nas sete seções do modelo: cores e o papel de cada uma (tabela, hex), fontes, espaço,
  tipos de seção, movimento, o proibido, referências. Tire o aviso `<!-- pendente -->`. No fim, uma seção
  "Decisões" com a data e o que mudou e por quê.
- **`tokens.css`**, com as mesmas decisões. Mantenha os nomes das variáveis que já existem (`--fundo`, `--tinta`,
  `--destaque`…): site feito antes não pode quebrar. Pode acrescentar variáveis. Fonte dela: `@font-face`
  apontando pra `fontes/`.
- **`prova.html`**: já lê o `tokens.css`; só reescreva se mudou a estrutura (seções novas, componentes dela).
- **Contraste:** texto sobre fundo e texto sobre o destaque com pelo menos 4,5:1. Se a cor dela não passa, diga e
  proponha a versão que passa, mantendo a dela pra forma (filete, ícone, brilho).

## Conferir

Abra a `prova.html` no navegador (`open` no Mac, `start` no Windows; ou tire o print com a `webapp-testing` se
estiver instalada) e olhe antes de dizer que está pronto. Mostre pra ela e peça o "ok". O design system só vale
depois do ok.

## Deixar amarrado

- A regra "leia `marca/` em todo trabalho visual" já está no `CLAUDE.md` da raiz. Em cliente, garanta a linha no
  `CLAUDE.md` dele: "o visual deste cliente é `marca/design-system.md` desta pasta".
- Anote em `tarefas.md` o que ficou pendente (logo em SVG, fonte licenciada, seção não decidida).

## Regras

- Hex sempre; nada de "um azul parecido".
- Nunca renomear variável do `tokens.css`.
- Nunca inventar regra de marca que ela não deu: o que falta vira pergunta ou proposta marcada como proposta.
- O design system diz o que fazer; a `prova.html` mostra. Os dois sempre batem.
