# Sistema IA CLASS

A pasta de trabalho de quem faz o IA CLASS. Você abre no Claude Code, responde oito perguntas, e ele passa a saber
quem você é, como você escreve e onde guardar cada coisa que criar. Vem com as skills do curso e mais 18 skills de
design instaladas.

## Baixar

**Pelo navegador, sem precisar de Git**

1. Clique no botão verde **Code**, no alto desta página, e depois em **Download ZIP**.
2. Descompacte o arquivo onde quiser (em Documentos, por exemplo). A pasta vem com o nome `sistema-iaclass-main`;
   pode renomear pra `sistema-iaclass`.

**Pelo terminal, com Git**

```bash
git clone https://github.com/estudiorelier-hue/sistema-iaclass.git
```

## Começar

1. Abra a pasta no Claude Code. No VS Code: Arquivo → Abrir pasta. No terminal: entre na pasta e digite `claude`.
2. Peça `/comecar`. São oito perguntas, uma por vez, uns dez minutos. No fim, o Claude escreve quem você é, cria só
   as pastas que você vai usar e propõe o primeiro pedido.
3. O resto do primeiro dia está em [COMECE-AQUI.md](COMECE-AQUI.md).

## O que vem dentro

| | |
|---|---|
| `CLAUDE.md` | o que o Claude lê toda vez que você abre a pasta: quem você é e como trabalhar aqui |
| `COMECE-AQUI.md` | o primeiro dia em quatro passos |
| `_contexto/` | o seu perfil, como você escreve e o que importa agora |
| `marca/` | o seu design system: cores, fontes, espaço, e uma página pra ver tudo no navegador |
| `entrada/` | onde você joga prints, PDFs e referências sem organizar; o Claude leva pro lugar certo |
| `sistema/` | o método do curso, o catálogo das skills, os modelos das pastas e a versão |
| `.claude/skills/` | as skills do curso (`/comecar`, `/marca`, `/atualizar-sistema`) e as 18 de design |

As pastas de trabalho (conteúdo, sites, vídeos, clientes e as outras) não vêm prontas: o `/comecar` cria só as que
você vai usar.

## Atualizar

Quando sair versão nova, peça `/atualizar-sistema` dentro da pasta. Ele mostra o que mudou e, com o seu ok, troca só
o que é do curso. O que é seu (o perfil, a marca, as pastas e os clientes) fica como está. O que mudou em cada versão
está em [sistema/MUDANCAS.md](sistema/MUDANCAS.md).

## Licenças

As 18 skills de terceiros são de código aberto (MIT e Apache 2.0) e vêm com as licenças originais; a lista com autor e
fonte está em [sistema/LICENCAS.md](sistema/LICENCAS.md). As skills do curso e o conteúdo de `sistema/` são da
Estúdio Relier, feitos pra quem faz o IA CLASS.
