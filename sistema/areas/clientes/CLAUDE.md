# clientes/

Uma pasta por cliente, e cada uma é um sistema em miniatura: o Claude só mistura clientes se você pedir.

```
clientes/<nome>/
  CLAUDE.md        o que é o cliente, contato, o que entrego, regras dele
  voz.md           como ele fala e pra quem
  marca/           o design system dele (o /marca monta: design-system.md, tokens.css, prova.html, logo)
  entrada/         o que ele manda
  conteudo/  propostas/  sites/  ...   só as áreas que esse cliente usa
```

- Novo cliente: `/comecar cliente <nome>` cria a pasta com o modelo.
- Ao trabalhar dentro de `clientes/<nome>/`, vale o `CLAUDE.md`, a `voz.md` e a `marca/` dele, não os meus.
