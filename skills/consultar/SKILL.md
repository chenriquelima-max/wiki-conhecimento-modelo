---
name: consultar
description: Responde perguntas usando o wiki/ como base. Use quando um humano ou outro agente pedir conhecimento deste wiki.
---

# Consultar

## Passos

1. Leia `wiki/index.md`.
2. Escolha as páginas ligadas à pergunta e abra só elas.
3. Siga os links `[[...]]` se precisar de mais contexto.
4. Responda citando as páginas usadas. Ex.: `(wiki/trafego/conceitos/cpl.md)`.
5. Se o wiki não tem a resposta, diga isso claramente. Só depois consulte o `raw/`.
6. Se a resposta ficou boa e vai ser útil de novo:
   - salve em `outputs/AAAA-MM-DD-assunto.md`;
   - ofereça transformar em página de síntese no wiki.
7. Acrescente uma linha em `wiki/log.md` com tipo `consulta`.

## Regras

- Não invente. O que não está no wiki é "não encontrado".
- Mostre divergências quando existirem.
