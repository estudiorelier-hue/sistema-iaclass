# Mudanças

O que entrou em cada versão do Sistema IA CLASS. O `/atualizar-sistema` mostra daqui o que mudou desde a sua versão.

## 0.3.0 · 24/11/2026

- Skill nova do curso: `imagem-nanobanana`. Escreve o prompt de imagem pro Nano Banana pra você colar no Magnific:
  registra uma pessoa uma vez (dossiê do rosto em `imagens/pessoas/`) e mantém ela igual em todas as imagens; faz
  ensaio, produto, ilustração em série (estilo guardado em `imagens/estilos/`) e edição de imagem; diz o que anexar
  e o que escolher lá, e ajusta o prompt pelo que saiu.
- Skill nova do curso: `video-seedance`. Escreve o prompt de vídeo pro Seedance pra você colar no Magnific: anima uma
  foto, faz b-roll, produto, antes e depois e sequência com vários planos, com som e fala; escolhe o caminho certo
  (imagem → vídeo quando precisa sair fiel) e ajusta pelo que saiu.

## 0.2.0 · 21/10/2026

- Skill nova do curso: `copy-da-pagina`. Escreve a copy inteira de um site, de uma landing page ou de um linktree
  (seu ou de cliente): descobre o tipo certo, pergunta o que falta em blocos, mostra a estrutura antes e entrega o
  `copy.md` pronto pra construir, com `{{marcado}}` o que só você sabe. Também faz portfólio e proposta por link.

## 0.1.0 · 19/10/2026

- Primeira versão: o núcleo (`CLAUDE.md`, `_contexto/`, `marca/` com o design system neutro, `entrada/`,
  `sistema/`), as oito áreas opcionais e o modelo de cliente.
- As skills do curso: `comecar`, `marca`, `atualizar-sistema`. O método do curso (as quatro perguntas, as três
  listas, o rascunho e o pedido) fica em `sistema/metodo/`, como material, sem comando.
- Publicado em github.com/estudiorelier-hue/sistema-iaclass, de onde o `/atualizar-sistema` busca as versões novas.
- As 18 skills de terceiros instaladas da fonte (`sistema/skills.json`), com o catálogo em português.
- Versões locais automáticas ao fim de cada resposta, sem conta e sem internet.
