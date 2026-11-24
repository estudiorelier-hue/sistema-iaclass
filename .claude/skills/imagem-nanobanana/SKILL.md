---
name: imagem-nanobanana
description: Escreve o prompt de imagem pro Nano Banana (Pro, 2 ou o mais novo), pronto pra colar no Magnific e gerar. Foto de pessoa com o rosto igual em todas as imagens (registra a pessoa uma vez e reaproveita), ensaio, cena de produto, ilustração, ícone, capa, fundo e edição de uma imagem que já existe (trocar fundo, roupa, proporção, estilo). Guarda a pessoa e o estilo registrados pra próxima vez e anota o que funcionou. Use em /imagem-nanobanana, "prompt de imagem", "prompt pro nano banana", "gera uma foto minha", "ensaio com IA", "foto de produto", "prompt em JSON", "o rosto saiu diferente", "melhora esse prompt de imagem". Não gera a imagem: quem gera é você, no Magnific.
---

# /imagem-nanobanana

O Nano Banana devolve o que você descreve, e o que você não descreve ele preenche com a média. Prompt curto dá
foto de banco de imagem. O que separa uma imagem que parece campanha de uma que parece I.A é detalhe: de onde vem a
luz, que lente, que cor, que textura de pele, o que não pode aparecer.

Esta skill escreve esse prompt. Quem gera é você, no Magnific: a skill entrega o texto num bloco pra copiar, diz o
que anexar e o que escolher lá, e depois ajusta o prompt com base no que saiu.

## Antes de escrever

1. **Pra quem é.** Pra você ou pra um cliente? Se for cliente, trabalhe em `clientes/<nome>/` e leia o `CLAUDE.md`
   dele. Se for seu, leia `_contexto/perfil.md` e, se a imagem é de marca, `marca/design-system.md` (paleta e
   estilo saem de lá, não da cabeça).
2. **Onde mora.** Uma pasta por ensaio ou peça: `imagens/AAAA-MM-DD-<nome>/prompts.md` (no cliente,
   `clientes/<nome>/imagens/...`). Se a área `imagens/` não existe, crie a pasta assim mesmo.
3. **O que já está registrado.** Veja `imagens/pessoas/` (dossiê de cada pessoa) e `imagens/estilos/` (estilos de
   série). Se a pessoa ou o estilo já existe, use. Não registre de novo o que já está lá.

## Que tipo de imagem é

| Pedido | Tipo | Formato do prompt | Leia |
|---|---|---|---|
| foto de uma pessoa real que precisa sair igual (você, cliente, aluna) | **pessoa** | JSON | `references/pessoa.md` |
| ilustração, ícone, padrão, infográfico, peça de marca em série, sem rosto real | **design** | JSON | `references/design.md` |
| produto, comida, ambiente, objeto, cena sem pessoa específica | **cena** | texto corrido (JSON se tiver muitos elementos) | `references/cena-e-edicao.md` |
| mexer numa imagem que já existe (fundo, roupa, proporção, limpar, mudar estilo) | **edição** | texto corrido | `references/cena-e-edicao.md` |

Pra luz, lente e cor, em todos os tipos: `references/luz-lente-cor.md`.

Quando ela pedir JSON ou texto corrido, siga o pedido. Sem pedido, use a tabela.

## O fluxo

1. **Entender o pedido.** Em uma mensagem, pergunte só o que falta pra escrever bem: pra onde vai (feed 4:5, story
   9:16, capa 16:9, quadrado), o que a imagem precisa comunicar e se tem referência. Referência visual (print de
   Pinterest, foto de campanha) resolve mais que cinco perguntas: peça. Se o pedido já diz tudo, não pergunte.
2. **Registrar, se for a primeira vez.**
   - Pessoa nova: peça 2 ou 3 fotos (rosto de frente com luz boa, uma de corpo, uma sorrindo) e o nome que vai
     identificar ela. Monte o dossiê de `pessoa.md`, mostre, peça o "ok" e salve em `imagens/pessoas/<nome>.md`.
   - Estilo novo de série: monte o sistema de `design.md` (parte da paleta da marca, se existir), mostre, peça o
     "ok" e salve em `imagens/estilos/<nome>.md`.
3. **Relembrar antes de escrever.** Em toda geração, leia o dossiê ou o estilo e liste em uma linha os traços que
   vão travados no prompt. É isso que mantém o rosto igual na décima imagem.
4. **Escrever o prompt.** Em inglês (o modelo responde melhor), num bloco de código pra copiar. Antes do bloco, até
   quatro linhas em português: a ideia da cena, a luz, a lente, a cor.
5. **Dizer o que fazer no Magnific.** Logo depois do bloco, curto:
   - o modelo: **Nano Banana Pro** pra peça única com muito detalhe, pessoa hiper-realista ou texto na imagem;
     **Nano Banana 2** (ou o mais novo da lista) pra série, variação rápida e teste;
   - o que anexar e em que ordem (a primeira imagem anexada é a `@img1` do prompt, a segunda a `@img2`);
   - a proporção e a resolução, que se escolhem na ferramenta (o prompt repete, mas quem manda é o seletor);
   - quantas gerar: peça 2 a 4 variações e escolha, em vez de refazer o prompt por uma imagem só.
6. **Anotar.** Acrescente em `prompts.md` da pasta: data, o prompt, o modelo, o que anexou. Quando ela contar o que
   saiu, anote embaixo ("rosto ok, mão estranha, luz fria demais") e o ajuste feito.
7. **Ajustar com base no que saiu.** Ela descreve ou manda o print do resultado. Mexa só no que errou e diga o que
   mudou. Tabela de problemas abaixo.

## Regras de todo prompt

- **Luz nunca é genérica.** "Good lighting", "natural light", "dramatic lighting" estão proibidos. Diga a fonte, a
  direção, a qualidade, a temperatura em Kelvin e o efeito visível. Detalhes em `luz-lente-cor.md`.
- **Cor sempre definida.** Uma paleta só, com saturação, contraste e uma referência de estilo.
- **Composição intencional.** Tipo de plano, ângulo, lente, profundidade de campo, onde fica o assunto no quadro.
- **O que não pode aparecer, escrito.** Todo prompt termina com o que evitar (no JSON, o campo `negative`).
- **Pessoa: o dossiê vence tudo.** Os cinco traços principais entram em toda geração, mesmo na centésima.
- **Marca: a paleta é a da marca.** Com hex. Nada de "cores modernas".
- **Fatos são dela.** Texto que aparece na imagem (nome, preço, frase) vem dela, letra por letra, entre aspas no
  prompt. Se não veio, pergunte.

## Quando o resultado não sai certo

| Saiu assim | O que mudar no prompt |
|---|---|
| rosto diferente da pessoa | reforce os 5 traços em `critical_features`, anexe mais uma foto de rosto, use o Pro, tire do prompt o que briga com o rosto (maquiagem pesada, ângulo extremo) |
| pele de plástico, cara de I.A | preencha `hyperrealism_controls` com poros, oleosidade, assimetria; cite lente e grão; ponha "airbrushed, waxy skin" no negativo |
| luz chapada, sem profundidade | troque a luz por uma fonte com direção (45° de um lado, contraluz do outro) e diga a sombra que ela faz |
| cor errada, muito saturada | escreva a paleta com hex e a saturação ("muted, low saturation") e ponha "oversaturated" no negativo |
| texto torto ou com letra trocada | use o Pro, texto curto, entre aspas, com fonte, peso e posição; se continuar, gere sem texto e escreva por cima depois |
| mão ou dedo estranho | dê uma ação clara pra mão (segurando a xícara pela alça) ou tire a mão do quadro; "extra fingers, distorted hands" no negativo |
| série sem cara de série | volte no estilo registrado e repita o `consistency_lock` inteiro em todas as peças |
| ignorou a referência | diga o papel de cada anexo ("use @img2 only for lighting and composition, ignore its face") |

## O que não fazer

- Não escrever prompt de uma pessoa real sem a foto e o "ok" dela (ou do cliente) pra usar a imagem dela.
- Não imitar marca, logo ou pessoa famosa de outra pessoa.
- Não gerar a imagem por outro caminho nem pedir chave de API: o fluxo desta skill é prompt aqui, geração no Magnific.
- Não reescrever o prompt inteiro pra corrigir um detalhe.
