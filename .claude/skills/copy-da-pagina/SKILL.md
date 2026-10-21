---
name: copy-da-pagina
description: Escreve a copy inteira de um site (marca, negócio, empresa, portfólio), de uma landing page (vender um curso, um serviço, um produto, uma proposta) ou de um linktree, pra você ou pra um cliente. Descobre o tipo certo, faz as perguntas que faltam em blocos, monta a estrutura na ordem em que quem lê decide e entrega o `copy.md` pronto pra construir. Use em /copy-da-pagina, "escreve a copy", "texto do site", "copy da landing", "página de vendas", "texto do linktree", "link da bio", "o que escrever na página", "melhora o texto desse site".
---

# /copy-da-pagina

Página boa começa no texto. O layout só organiza o que a copy já decidiu: o que a pessoa lê primeiro, o que ela
precisa saber pra confiar e onde ela clica. Sem `copy.md` fechada, o Claude constrói a média da internet e você
passa dias ajustando.

Esta skill escreve **todo** o texto da página, do título ao rodapé, com o objetivo dela na cabeça o tempo todo. Ela
não inventa: o que só a pessoa sabe (número, preço, nome de cliente, depoimento, resultado) ela pergunta, e o que
continuar faltando fica marcado `{{assim}}` no ponto exato.

## Antes de perguntar

1. **De quem é a página.** Sua marca ou de um cliente? Se for de cliente, trabalhe dentro de `clientes/<nome>/` e
   leia o `CLAUDE.md` e o `voz.md` dele. Se for sua, leia `_contexto/perfil.md` ("Como eu escrevo") e
   `_contexto/foco.md`. Se o sistema ainda não foi montado (sem `perfil.md`), siga assim mesmo: a voz sai do
   último bloco das perguntas, e a página mora em `sites/<projeto>/` (crie a pasta).
2. **Onde mora.** `sites/<projeto>/`. Se já existe `pedido.md` ou `copy.md` ali, leia: é continuação ou revisão, não
   começo. Revisão de página que já está no ar: peça o link ou o texto atual e trabalhe em cima dele.
3. **O material.** Antes da primeira pergunta, peça o que já existe: bio do Instagram, site antigo, página de um
   concorrente ou referência, posts que venderam, prints de depoimento, prints de conversa com cliente, áudio
   explicando o negócio. Um material desses responde várias perguntas de uma vez e traz as palavras reais do público,
   que nenhuma pergunta extrai. Pode jogar na `entrada/` do projeto ou do cliente.

## O tipo de página

A pergunta que decide é: **o que a pessoa que abre precisa fazer ali?**

| Ela precisa… | Tipo | O trabalho da página | Leia |
|---|---|---|---|
| decidir comprar ou contratar uma coisa | landing page | vender uma coisa só, com um botão | `references/landing.md` |
| entender quem você é e confiar | site | explicar o negócio e ser encontrado | `references/site.md` |
| ir pro lugar certo saindo do Instagram | linktree | distribuir, com um destaque | `references/linktree.md` |

- "A landing vende, o site explica, o link distribui."
- **Portfólio** é um site cuja prova é o próprio trabalho: siga `site.md`, parte "Portfólio".
- **Proposta ou orçamento por link** é uma landing pra um cliente só: siga `landing.md`, parte "Proposta".
- Se ela pedir "um site" mas o que descreve é vender um curso, diga que é landing, por quê, e pergunte se segue assim.
  Se o negócio precisa das duas coisas, faça uma por vez, começando pela que traz dinheiro mais perto.

## O fluxo

0. **Que tipo de pedido é.** Diga em uma linha qual dos três, antes de tudo:
   - **Do zero** (nada escrito, ou só uma ideia): entrevista completa. Liberdade no ângulo, nenhuma nos fatos.
   - **Já tem texto dela** (rascunho, página antiga, áudio): mantenha o argumento e as palavras dela; corrija o que
     está enterrado, vago ou com cara de I.A. Pergunte só o que o texto não responde.
   - **Ajuste pontual** ("muda o título", "encurta o FAQ"): mexa só no que ela pediu e mostre as linhas trocadas,
     cada uma com o motivo em uma linha. Sem entrevista.
1. **Entrevista.** Leia `references/perguntas.md`. Um bloco por mensagem, esperando a resposta. Pergunta fechada vai
   pelo `AskUserQuestion`; aberta vai no chat. Pule o que o material ou o contexto já respondeu e diga o que já sabe
   em uma linha ("Pelo seu perfil, já sei que…"). Insista quando a resposta vier genérica, com o motivo, no máximo
   duas vezes na mesma pergunta; depois vira `{{dado que falta}}`. As respostas ficam em
   `sites/<projeto>/briefing.md`, pra próxima rodada não perguntar de novo.
2. **O esqueleto, antes do texto.** Mostre em até 12 linhas: a frase central da página (a promessa, ou o que o
   negócio é numa frase), o quanto quem chega já sabe (tabela de `landing.md`), a estrutura na ordem com a pergunta que cada seção responde, e o que ainda falta. Peça o "ok".
   Seção que não responde pergunta de quem lê, sai.
3. **A copy.** Leia `references/escrita.md` e o arquivo do tipo. Escreva a página inteira no formato de
   `references/modelo-copy.md`, em `sites/<projeto>/copy.md`. Três opções de título só no topo (a recomendada
   primeiro); o resto sai uma versão só, decidida.
4. **Revisão que muda o texto.** As quatro ações de `escrita.md` ("Revisar"), sempre. Reescrever as linhas fracas faz
   parte da entrega.
5. **Entrega.** No chat, curto: o que você escolheu e por quê (o ângulo, a ordem, o título recomendado), a lista do
   que está `{{marcado}}`, e uma pergunta só pra calibrar a próxima rodada. A copy fica no arquivo, não no chat.
6. **Próximo passo.** Se não existe `pedido.md`, ofereça escrever com o que a entrevista já trouxe (modelo em
   `sistema/metodo/pedido-modelo.md`): as seções 1 a 3 já estão respondidas. Depois, é construir a partir do
   `copy.md` com o design system de `marca/`.

## Regras

- **Fato é da pessoa.** Número, preço, prazo, nome de cliente, depoimento, história, resultado, contagem de alunos:
  só o que ela disse. O resto é `{{o que falta}}`. Depoimento nunca se escreve: se não tem, a seção fica com
  `{{depoimentos: prints ou texto de quem já comprou}}` ou sai da estrutura.
- **Fato é dela, leitura pode ser sua.** O diagnóstico do problema ("o que ela acha que é e o que é de verdade") e o
  ângulo da página podem ser uma leitura sua das respostas, desde que saiam do que ela contou. Mostre essa leitura
  no esqueleto, como leitura, pra ela confirmar antes de virar texto.
- **Uma página, um objetivo.** Landing tem um botão (repetido), site tem um próximo passo principal, linktree tem um
  destaque. Dois objetivos de mesmo peso dividem o clique.
- **Escrever pra quem lê, não pra quem vende.** O público da página é o cliente da pessoa (ou o cliente do cliente),
  quase nunca ela mesma. Toda dor e todo desejo vêm do que ela contou sobre esse público.
- **Na voz dela.** O registro vem de `perfil.md` ou do `voz.md` do cliente. Sem amostra de voz, escreva na voz de
  `escrita.md` e avise que vai ficar mais neutro até ela mandar textos dela.
- **Uma pergunta (ou um bloco) por vez.** Nunca o questionário inteiro de uma vez.
- **Correção que vale pra sempre** ("não uso essa palavra", "prefiro falar 'a gente'"): pergunte se salva. Voz dela →
  uma linha em `_contexto/perfil.md`; de um cliente → no `voz.md` dele. Sem reescrever o arquivo.
- **Não construir nada aqui.** Esta skill entrega texto e estrutura. HTML, design e publicação vêm depois, com o
  `copy.md` fechado.

## De onde vem

O jeito de ensinar do IA CLASS (módulo 4: a diferença entre os três, a landing na ordem das perguntas, a página que
responde uma pergunta por seção, o link na bio como vitrine) e as páginas que a gente escreveu e pôs no ar. Somados a
ideias de skills abertas de copy: `coreyhaines31/marketingskills` (copywriting, copy-editing, cro, offers), a
StoryBrand de `wondelai/skills`, `TheMattBerman/landing-page-factory`, os mapas de consciência de Eugene Schwartz e o
guia de landing pages de Julian Shapiro. Nada foi copiado; tudo foi reescrito pro português e pro nosso jeito.
