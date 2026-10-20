---
name: comecar
description: Monta o sistema da aluna com uma entrevista curta, cria só as áreas que ela usa e escreve o CLAUDE.md e o contexto. Depois, adiciona área ou cliente. Use em /comecar, "montar o sistema", "primeira vez", "nova área", "novo cliente", "refazer o setup".
---

# /comecar

Monta o sistema pra uma pessoa só: a que está na conversa. O resultado é um `CLAUDE.md` com a cara dela, o contexto
preenchido e apenas as pastas que ela vai usar de verdade. Pasta que não se usa vira ruído.

## Antes de perguntar

1. Leia o `CLAUDE.md` da raiz. Se tem a linha `<!-- estado: não montado -->`, é a primeira vez: siga em **Montar**.
2. Se já está montado, veja o que ela pediu:
   - `/comecar <área>` (ex.: `/comecar vídeos`) → **Adicionar área**.
   - `/comecar cliente <nome>` → **Novo cliente**.
   - só `/comecar` → pergunte: "O sistema já está montado. Quer adicionar uma área, criar um cliente ou refazer o
     contexto?" Refazer reescreve `_contexto/` e o "Quem sou"; nunca apaga áreas.
3. Liste as áreas que existem na raiz (pastas com o mesmo nome das de `sistema/areas/`), pra não criar duplicata.

## Montar

Tom direto, uma pergunta por vez, sem cerimônia. Pergunta fechada vai pelo `AskUserQuestion`; aberta vai no chat.
Se ela responder várias de uma vez, pule as já respondidas.

Abra com uma linha só:

> Vou te fazer oito perguntas pra montar o sistema com a sua cara. Responde do seu jeito; quanto mais concreto, melhor.

Se ela já usa o Claude Code noutra pasta ou outro assistente, ofereça antes: "Se você já tem um `CLAUDE.md` ou
arquivo de contexto em outro lugar, me diz o caminho que eu leio e pulo o que já souber." Com o que ler, confirme
em 4 linhas e pergunte só o que faltou.

1. **Nome e negócio.** "Seu nome, e o nome do seu negócio (ou o que você faz, se não tem nome)."
2. **O dia a dia.** "O que você mais faz e produz numa semana normal? Me dá exemplos do que sai das suas mãos."
3. **Clientes.** Fechada: só pra mim e meu negócio · atendo clientes · os dois.
4. **O que vai usar do curso.** Fechada, múltipla: conteúdo · design · vídeos · sites e landing pages · sistemas ·
   vendas (propostas, orçamentos) · imagens com I.A. Se a 3 incluiu clientes, `clientes/` entra sem perguntar.
5. **Ferramentas.** "Quais ferramentas você usa hoje? Notion, Canva, Drive, CapCut, planilha, Meta Ads, o que for."
6. **Como escreve.** "Como você quer que o Claude escreva por você? E o que mais te irrita em texto de I.A?"
7. **Marca.** Fechada: tenho manual ou arquivos · tenho site · descrevo em texto · ainda não tenho.
8. **Foco.** "O que precisa ter acontecido daqui a dois ou três meses pra você dizer que valeu?"

## O que gerar

Mostre o plano em 5 linhas antes de criar (áreas, arquivos) e crie depois do "ok".

1. **`_contexto/perfil.md`**: preencha os campos com as respostas 1, 2, 3, 5 e a seção "Como eu escrevo" com a 6,
   nas palavras dela, incluindo o que ela odeia. Tire o aviso `<!-- não configurado -->`.
2. **`_contexto/foco.md`**: a resposta 8 em fase, prioridades (até 3) e datas. Tire o aviso.
3. **`CLAUDE.md`**: apague a linha de estado e o aviso "Ainda não montado"; escreva "Quem sou" em três linhas
   (nome, negócio, o que faz e pra quem); na lista de áreas, uma linha por área instalada, no formato
   `- \`conteudo/\` — o que eu escrevo pra postar`. Não mexa nas regras.
4. **As áreas**: copie `sistema/areas/<área>/` (o `CLAUDE.md` e a `historico/`) pra raiz, só as marcadas na 4.
   Clientes: copie `sistema/areas/clientes/`.
5. **A marca**, pela resposta 7:
   - manual ou arquivos → "Joga na `entrada/` que eu monto o design system" e termine chamando o `/marca`;
   - site → termine chamando o `/marca` com o link;
   - descrição → termine chamando o `/marca` do zero;
   - ainda não → deixe o padrão neutro de `marca/` e anote em `tarefas.md`: "montar o design system (`/marca`)".
6. **Versões locais**: se `git` existe e não há `.git` na pasta, rode `git init`, `git add -A` e
   `git commit -m "versão 0: sistema montado"`. Nada de remoto, nada de conta. Sem `git` instalado, pule em silêncio e
   anote em `tarefas.md`: "instalar o git pra ter versões locais (`sistema/ferramentas.md`)".
7. **`tarefas.md`**: risque "Rodar /comecar"; acrescente as pendências acima.
8. **Ferramentas**: não instale nada agora. Diga que algumas skills pedem Node, Python ou Playwright e que você
   avisa na hora em que precisar (`sistema/ferramentas.md`).

## Fechar

Resumo em até 6 linhas: o que foi criado e onde. Depois, o primeiro pedido, um só, escolhido pela resposta 2:
- tem marca → o `/marca`;
- atende clientes → "Me conta de um cliente e eu crio a pasta dele";
- vai construir site ou sistema → "Me manda o `pedido.md` do primeiro projeto, ou me conta o projeto e eu escrevo
  o pedido com você pelo modelo de `sistema/metodo/`";
- conteúdo → "Me passa o tema do próximo post que a gente escreve agora".

## Adicionar área

Copie `sistema/areas/<área>/` pra raiz, acrescente a linha no `CLAUDE.md` e diga em uma frase o que vai ali.

## Novo cliente

Três perguntas (o que é o negócio dele, quem fala com você e por onde, o que você entrega) e crie
`clientes/<nome-em-minusculas-sem-acento>/` com o `CLAUDE.md` de `sistema/areas/cliente-modelo/` preenchido, uma
`entrada/` e um `voz.md` com só o cabeçalho "# Como o <cliente> fala". A `marca/` do cliente só quando ela pedir
(`/marca` dentro da pasta dele). Se `clientes/` não existe, crie pelo modelo.

## Regras

- Uma pergunta por vez. Nunca as oito de uma vez.
- Mostrar o plano antes de criar; não criar o que ela não confirmou.
- Nunca mover ou apagar pasta que já existe.
- Escrever o contexto nas palavras dela, não em adjetivo de manual ("tom próximo e autêntico" não serve).
- Sem conta, sem internet e sem instalação nesta etapa.
