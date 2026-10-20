# Ferramentas

A maior parte do sistema funciona só com o Claude Code. Sete skills precisam de uma ferramenta a mais no computador.
Instale só quando for usar; o Claude avisa qual falta. Peça pra ele instalar: ele faz, e você aprova.

| Precisa de | Pra quê | Skills |
|---|---|---|
| **Node.js** | rodar scripts, montar sites, instalar skills novas | `ui-styling`, `web-artifacts-builder`, `find-skills`, `motion-dev-animations` |
| **Python** | scripts de design e de teste | `design`, `ui-styling`, `webapp-testing`, `ui-ux-pro-max` |
| **Playwright** | abrir o site num navegador invisível, tirar print e conferir | `webapp-testing`, `web-artifacts-builder`, `design` |
| **Chave da Gemini** | gerar logo, banner e imagem | `design`, `banner-design` |

## Como instalar

**Mac**
```bash
xcode-select --install            # as ferramentas básicas da Apple (git e Python), uma vez
# Node.js: baixe o instalador "LTS" em nodejs.org e abra. Se tiver o Homebrew: brew install node
npx -y playwright@latest install chromium     # o Playwright, depois do Node
pip3 install --user <pacote>                  # pacotes de Python que uma skill pedir
```

**Windows** (PowerShell)
```powershell
winget install OpenJS.NodeJS.LTS
winget install Python.Python.3.12
npx -y playwright@latest install chromium
```

Feche e abra o terminal depois de instalar, pra ele enxergar o que entrou.

## A chave da Gemini

Grátis em aistudio.google.com → "Get API key". Guarde na pasta do sistema num arquivo `.env` (que fica fora das
versões), assim:

```
GEMINI_API_KEY=cole-aqui
```

Nunca cole a chave numa conversa nem num arquivo que você compartilha.

## Se algo não funcionar

Diga ao Claude "a skill X deu erro" e cole a mensagem. Ele diz o que falta e instala com você.
