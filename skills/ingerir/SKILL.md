---
name: ingerir
description: Lê arquivos novos do raw/ e transforma em páginas do wiki/. Use quando entrar material bruto novo.
---

# Ingerir

## Passos

1. Leia `wiki/log.md` e veja quais arquivos do `raw/` já foram ingeridos.
2. Liste os arquivos do `raw/` que ainda não aparecem no log.
3. Para cada arquivo novo:
   1. Leia o arquivo inteiro.
   2. Crie o resumo em `wiki/<tema>/fontes/<mesmo-nome>.md` (use `templates/fonte.md`).
   3. Liste os conceitos, ferramentas e pessoas citados.
   4. Para cada um: se a página já existe, acrescente o que é novo. Se não existe, crie (use `templates/conceito.md`).
   5. Se a fonte contradiz uma página, registre em `## Divergências`. Não apague a versão antiga.
   6. Ligue as páginas entre si com `[[nome-da-pagina]]`.
4. Atualize `wiki/index.md`.
5. Acrescente uma linha em `wiki/log.md`:
   `2026-10-07 | ingestão | raw/trafego/aula-03.md | 1 fonte, 4 conceitos (2 novos), 1 ferramenta`
6. Mostre ao humano um resumo curto do que mudou.

## Regras

- Nunca edite nem apague nada em `raw/`.
- Uma fonte costuma mexer em 5 a 15 páginas. Isso é normal.
- Na dúvida sobre o tema, pergunte antes de criar pasta nova.
