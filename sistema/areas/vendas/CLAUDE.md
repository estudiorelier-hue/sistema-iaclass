# vendas/

O que vende o meu serviço: propostas, orçamentos, ofertas, a tabela de preços.

```
vendas/
  tabela-de-precos.md         o que eu cobro por cada coisa e por quê
  ofertas.md                  as ofertas prontas (o que entra, por quanto, pra quem)
  propostas/<cliente>-<data>/ a proposta (em site, PDF ou slides) e o que foi combinado
  orcamentos/                 orçamentos rápidos
```

- Proposta em site: `web-artifacts-builder` ou um `index.html` em `propostas/<cliente>-<data>/`, no design system.
- Proposta em slides: `slides`. Em PDF: a partir do HTML.
- Preço, prazo e escopo são meus: o Claude nunca inventa valor. Sem a tabela, ele pergunta.
- O módulo de vendas do curso enche esta área: precificação, prospecção, negociação.
