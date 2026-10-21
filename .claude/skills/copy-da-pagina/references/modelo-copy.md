# O formato do copy.md

O `copy.md` é o texto final da página, na ordem final, pronto pra quem constrói (você ou o Claude) só montar. Quem
abre o arquivo precisa conseguir ler a página de cima a baixo sem abrir mais nada.

## O modelo

```markdown
# <Nome do projeto> · copy

<landing page · site · linktree> pra <marca ou cliente>. Escrita em <data>.
**O objetivo:** <o que a pessoa que abre precisa fazer, numa frase>.
**Pra quem:** <quem abre, com o momento dela>.
**O botão:** <o texto do botão principal> → <pra onde leva: checkout, WhatsApp, formulário, {{link}}>.

**Falta:** <a lista do que está {{marcado}} no texto, um item por linha>. (Some quando não faltar nada.)

---

## 1 · <NOME DA SEÇÃO>
> Responde: "<a pergunta de quem lê que esta seção responde>"

**Título:** <texto>
**Apoio:** <texto>
<o corpo, com as quebras de linha que vão aparecer na tela>
**Botão:** <texto>
[foto: o que a imagem precisa mostrar]

## 2 · <NOME DA SEÇÃO>
...
```

## As marcações

- **`> Responde:`** em toda seção. É o que impede seção de enfeite e o que o Claude lê pra entender a função dela.
- **Os papéis do texto**, em negrito antes de cada pedaço: **Selo** (a linha pequena acima do título), **Título**,
  **Apoio**, **Botão**, **Item**, **Pergunta** e **Resposta** (no FAQ), **Nota** (letra pequena embaixo do botão).
  Assim ninguém precisa adivinhar o que é título e o que é parágrafo.
- **Quebra de linha é intenção.** A linha quebrada no `copy.md` é a linha quebrada na tela. Parágrafo de página tem
  no máximo três linhas.
- **`[foto: …]`, `[vídeo: …]`, `[print: …]`** dizem o que a imagem precisa mostrar, nunca como desenhar. Cor,
  fonte e efeito são do design system, não da copy.
- **`{{o que falta}}`** pra todo dado que só a pessoa tem, escrito de um jeito que ela saiba o que mandar:
  `{{número de alunas até hoje}}`, `{{link do checkout}}`, `{{3 depoimentos com nome e foto}}`.
- **Títulos alternativos**, só no topo:
  ```
  **Título (recomendado):** ...
  **Opção 2:** ... (o ângulo dela, numa linha)
  **Opção 3:** ...
  ```
  Quando ela escolher, apague as outras.

## Site

Um `copy.md` só, com uma parte por página (`# Início`, `# Sobre`, `# Serviços`, `# Contato`) e, antes delas, o
**menu** (os nomes das páginas como aparecem) e o **rodapé** (que se repete em todas). Cada página começa com
`> Responde:` e o título que aparece na aba do navegador e no Google:

```markdown
# Início
> Responde: "É pra mim?"
**No Google:** <título da aba, até 60 caracteres> · <descrição, até 155 caracteres>
```

## Linktree

Seções TOPO, DESTAQUE, LINKS (ou uma por grupo), CONTATO, RODAPÉ. Cada link:

```markdown
**Item:** <nome do link>
<a linha do que tem lá>
**Botão:** <se for diferente do nome> → <endereço ou {{link: o que é}}>
**Nota:** <preço, data de validade ou "até 30/11", se tiver>
```

As redes no rodapé: `[ícones: Instagram → <link> · YouTube → <link>]`. O destaque com data leva, logo abaixo do
`## DESTAQUE`, a linha `> Até <data>. Depois, entra: <o que entra ou {{o que entra}}>`.
