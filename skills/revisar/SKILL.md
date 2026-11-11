---
name: revisar
description: Faz a checagem de saúde do wiki (lint). Use 1 vez por semana ou quando o wiki crescer muito.
---

# Revisar (lint)

## O que procurar

1. **Contradições** entre páginas.
2. **Páginas órfãs**: nenhuma outra página aponta para elas.
3. **Links quebrados**: `[[pagina]]` que não existe.
4. **Faltando no índice**: página que não aparece em `wiki/index.md`.
5. **Fonte não ingerida**: arquivo do `raw/` que não está no log.
6. **Informação velha**: `atualizado` com mais de 6 meses em tema que muda rápido.
7. **Lacunas**: conceito citado várias vezes que não tem página própria.

## Saída

1. Salve o relatório em `outputs/AAAA-MM-DD-revisao.md`.
2. Corrija sozinho só o que é mecânico: índice, links, formatação.
3. Contradições e lacunas: liste e pergunte ao humano.
4. Acrescente uma linha em `wiki/log.md` com tipo `revisao`.
