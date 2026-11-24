---
name: video-seedance
description: 'Escreve o prompt de vídeo pro Seedance (a versão mais nova que estiver no Magnific), pronto pra colar e gerar. Anima uma foto (a sua, de produto, a que saiu do /imagem-nanobanana), cria uma cena do zero, faz vídeo com começo e fim definidos, sequência com vários planos, b-roll pra Reels, abertura de anúncio e vídeo com fala e som. Diz o que anexar, o papel de cada anexo e o que escolher na ferramenta, e ajusta o prompt com base no que saiu. Use em /video-seedance, "prompt de vídeo", "prompt pro seedance", "anima essa foto", "b-roll", "vídeo com IA", "transforma essa imagem em vídeo", "cena pro reels", "o vídeo saiu tremido/deformado". Não gera o vídeo: quem gera é você, no Magnific.'
---

# /video-seedance

Vídeo com I.A dá errado por excesso: muita coisa se mexendo, câmera fazendo três movimentos, rosto derretendo no
segundo 4. O Seedance responde melhor a um prompt que parece instrução de diretor: quem, fazendo o quê, onde, com
qual movimento de câmera, com qual luz, e o que evitar. Uma ação clara por plano e um movimento de câmera por plano.

Esta skill escreve esse prompt. Quem gera é você, no Magnific: a skill entrega o texto num bloco pra copiar, diz o
que anexar e o que escolher lá, e depois ajusta com base no que saiu.

## Antes de escrever

1. **Pra quem é.** Você ou cliente? Cliente: trabalhe em `clientes/<nome>/` e leia o `CLAUDE.md` dele. Seu: leia
   `_contexto/perfil.md` e, se é peça de marca, `marca/design-system.md`.
2. **Onde mora.** `videos/AAAA-MM-DD-<nome>/prompts.md` (no cliente, `clientes/<nome>/videos/...`). Se a área
   `videos/` não existe, crie a pasta assim mesmo.
3. **Tem pessoa registrada?** Se o vídeo tem uma pessoa que já está em `imagens/pessoas/`, use os 5 traços dela.

## O caminho certo pra cada pedido

| Pedido | Caminho | Por quê |
|---|---|---|
| vídeo com uma pessoa real, produto ou marca que precisa sair fiel | **imagem → vídeo**: primeiro a foto no `/imagem-nanobanana`, depois anima ela como primeiro quadro | o rosto, o produto e a cor ficam decididos na foto; o vídeo só cuida do movimento |
| animar uma foto que ela já tem | **imagem → vídeo** | idem |
| começo e fim definidos (antes e depois, transição, revelação) | **primeiro e último quadro** | o modelo só inventa o meio |
| cena que não precisa ser fiel a nada (textura, ambiente, abstrato, b-roll genérico) | **texto → vídeo** | mais liberdade, menos controle |
| copiar o movimento de câmera de um vídeo de referência | **referência de vídeo** (`@Video1` só pra câmera) | ele lê o movimento, não a história |
| mais de 5 segundos com cortes (mini-sequência, anúncio) | **vários planos com tempo** | um bloco por plano, com o segundo em que começa |

O caminho imagem → vídeo é o padrão sempre que houver dúvida. Em `references/estrutura.md` estão a fórmula, o
vocabulário de câmera, os anexos, o formato de vários planos e exemplos.

## O fluxo

1. **Entender o pedido.** Em uma mensagem, pergunte só o que falta: pra onde vai (Reels/story 9:16, feed 4:5,
   YouTube 16:9), quantos segundos, se tem foto ou vídeo de referência, se precisa de som ou fala. Referência resolve
   mais que perguntas: peça.
2. **Escolher o caminho** pela tabela e dizer em uma linha qual e por quê. Se o caminho é imagem → vídeo e a foto
   ainda não existe, faça a foto primeiro com o `/imagem-nanobanana` (já no formato final, 9:16 pra Reels).
3. **Escrever o prompt.** Em inglês, num bloco de código pra copiar. Antes do bloco, até quatro linhas em português:
   a ação, a câmera, a luz, a duração.
   - Um plano: 60 a 100 palavras. Mais que 150 o modelo começa a ignorar parte.
   - Com foto de primeiro quadro: mais curto. A foto já diz como tudo é; o prompt diz o que **se mexe** e como.
   - Vários planos: formato com tempo de `estrutura.md`.
4. **Dizer o que fazer no Magnific.** Logo depois do bloco, curto:
   - o modelo: o **Seedance mais novo da lista** (2.x aceita várias referências, som e vários planos; o 1.5 Pro é a
     opção quando o mais novo não estiver liberado na conta). Se a versão escolhida não aceitar algo do prompt
     (referência de vídeo, áudio), diga o que tirar;
   - o que anexar, em que ordem, e o papel de cada um (a primeira imagem é a `@Image1`, o primeiro vídeo o `@Video1`);
   - a proporção, a duração e a resolução, que se escolhem na ferramenta (o prompt não manda nisso);
   - quantas gerar: 2 variações, escolher a melhor. Vídeo gasta mais crédito que imagem: teste curto (5 s) e só
     depois a versão longa.
5. **Anotar.** Em `prompts.md` da pasta: data, prompt, modelo, anexos, duração. Quando ela contar o que saiu, anote
   embaixo e o ajuste feito.
6. **Ajustar com base no que saiu.** Mexa só no que errou e diga o que mudou. Tabela abaixo.

## Regras de todo prompt

- **Uma ação principal por plano.** "Ela vira o rosto pra câmera e sorri" é uma ação. "Ela anda, pega a xícara,
  senta e acena" são quatro: vira quatro planos ou vira bagunça.
- **Um movimento de câmera por plano**, escrito separado do movimento de quem está em cena.
- **Ritmo em palavras, não em números.** slow, smooth, gentle, steady, gradual. Nada de fps ou abertura. Só uma
  coisa na cena pode ser "fast".
- **Luz sempre descrita.** É o que mais muda o resultado: fonte, direção, cor (vocabulário em
  `.claude/skills/imagem-nanobanana/references/luz-lente-cor.md`).
- **Nada de palavra vazia.** "Cinematic", "epic", "amazing", "dynamic" sozinhas não dizem nada. Diga o que se vê.
- **O que evitar, escrito no fim**, numa frase: `Avoid: identity drift, morphing, jitter, extra fingers, warped text.`
  Não existe campo separado de negativo: vai no próprio prompt.
- **Plano único sem corte:** termine com `One continuous shot, no cuts.`
- **Texto no vídeo, não.** Letreiro, legenda e logo saem tortos: ponha na edição depois. Deixe o espaço livre no
  prompt se precisar.
- **Reels:** o assunto no meio do quadro, longe das bordas de cima e de baixo, onde ficam a legenda e os botões.

## Quando o resultado não sai certo

| Saiu assim | O que mudar |
|---|---|
| o rosto muda, derrete ou vira outra pessoa | vá pelo caminho imagem → vídeo; menos movimento de cabeça; plano mais aberto; "identity drift, face morphing" no Avoid; vídeo mais curto |
| tremido, imagem pulando | câmera fixa ou um movimento lento só; tire "handheld"; "jitter, flicker" no Avoid |
| a câmera ignorou o movimento pedido | um movimento só, no começo da frase de câmera, com ritmo ("slow push-in toward her face") |
| mexe demais, parece bagunçado | uma ação, ritmo lento, menos elementos em cena; tire os adjetivos de energia |
| câmera lenta sem querer | diga a velocidade da ação ("at natural real-time speed") |
| mão, dedo, objeto deformando | ação simples pras mãos ou mãos fora do quadro; "bent limbs, extra fingers" no Avoid |
| cortou no meio quando era pra ser um plano | `One continuous shot, no cuts.` |
| produto mudou de forma ou o rótulo virou outro | use a foto do produto como primeiro quadro, câmera lenta, "keep the product shape and label unchanged" |
| a plataforma recusou a foto de rosto como referência | anexe a foto como **primeiro quadro** (imagem → vídeo) em vez de referência; se ainda recusar, a regra é da plataforma: use um plano em que o rosto não é o assunto |
| a fala não bateu com a boca ou saiu em outra língua | fala curta, entre aspas, com quem fala e "in Brazilian Portuguese"; se a versão não faz fala, grave a voz e junte na edição |

## O que não fazer

- Não fazer vídeo com o rosto de alguém real sem o "ok" dela (ou do cliente).
- Não imitar marca, personagem ou pessoa famosa de outra pessoa.
- Não gerar por outro caminho nem pedir chave de API: o fluxo é prompt aqui, geração no Magnific.
- Não reescrever o prompt inteiro pra corrigir um detalhe.
