---
name: atualizar-sistema
description: Traz a versão nova do Sistema IA CLASS (método, catálogos, skills do curso e skills de terceiros) sem tocar no que é da aluna. Use em /atualizar-sistema, "atualiza o sistema", "tem versão nova?", "a skill X está desatualizada".
---

# /atualizar-sistema

O que é do curso mora em `sistema/` e nas skills do curso; o que é dela mora no resto. Esta skill troca só o
primeiro grupo. Nunca toca em `CLAUDE.md`, `_contexto/`, `marca/`, `entrada/`, `tarefas.md` nem nas áreas.

## 1 · Comparar

1. Leia `sistema/manifest.json`: a versão local e o repositório.
2. Busque o manifesto remoto: `https://raw.githubusercontent.com/<repositório>/main/sistema/manifest.json`
   (com `curl -s`; no Windows o `curl` também existe). Sem internet ou repositório fora do ar: diga em uma linha e
   pare.
3. Mesma versão: "Você já está na versão X, a mais nova." e pare.
4. Versão nova: busque `sistema/MUDANCAS.md` remoto e mostre o que mudou desde a versão dela, em até 10 linhas.
   Pergunte se atualiza.

## 2 · Atualizar

1. Baixe o zip da versão nova (`https://github.com/<repositório>/archive/refs/heads/main.zip`) numa pasta
   temporária e descompacte.
2. Substitua, e só isso, os caminhos listados em `nosso` do manifesto remoto: `sistema/`, as skills do curso em
   `.claude/skills/` e `COMECE-AQUI.md`. Antes de substituir uma skill, se a versão local tiver sido editada por ela
   (compare com o manifesto; na dúvida, pergunte), guarde a cópia dela em `historico/skills/<nome>/`.
3. Skills de terceiros (`sistema/skills.json`): se há Node, rode `npx -y skills@latest update -p -y`. Se não há,
   diga que elas ficam como estão até o Node ser instalado (`sistema/ferramentas.md`).
4. Se o manifesto novo tiver áreas novas em `sistema/areas/`, não instale: diga que existem e que entram com
   `/comecar <área>`.
5. Apague a pasta temporária.

## 3 · Fechar

Diga a versão que ficou, o que foi trocado (contagem) e o que não foi tocado. Anote em `tarefas.md` qualquer passo
manual que a versão nova pedir (uma ferramenta nova, por exemplo).

## Regras

- Só os caminhos de `nosso`. Em dúvida, não troca e pergunta.
- Mostrar o que mudou antes de atualizar; nunca atualizar sem o "ok".
- Sem internet, sem drama: dizer e parar.
