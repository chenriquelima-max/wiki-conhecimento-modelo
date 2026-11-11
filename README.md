# Wiki de Conhecimento (método LLM Wiki do Karpathy)

Repositório para guardar conhecimento **fora dos cérebros operacionais**.
Os agentes consultam aqui quando precisam, por exemplo, para analisar campanhas.

Baseado no método publicado por Andrej Karpathy em abril de 2026:
[gist "LLM Wiki"](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

## A ideia em 3 frases

1. Você joga o material bruto em `raw/` (transcrições de aula, vídeos do YouTube, artigos, PDFs).
2. O agente lê esse bruto e escreve o destilado em `wiki/` (conceitos, ferramentas, pessoas, fontes).
3. Quando alguém pergunta, o agente consulta o `wiki/`, não o bruto.

> Você explora e escolhe as fontes. O agente organiza e mantém.

## Estrutura

```text
wiki-conhecimento/
├── CLAUDE.md          ← regras do agente (o "schema")
├── AGENTS.md          ← mesmo conteúdo, para Kimi/Hermes/Codex
├── raw/               ← material bruto. Só entra, nunca é editado
│   └── <tema>/
├── wiki/              ← o destilado. Só o agente escreve
│   ├── index.md       ← catálogo de tudo que existe no wiki
│   ├── log.md         ← diário: o que foi ingerido, quando
│   └── <tema>/
│       ├── conceitos/
│       ├── ferramentas/
│       ├── pessoas/
│       └── fontes/    ← um resumo por arquivo do raw
├── outputs/           ← respostas e relatórios gerados por consultas
├── skills/            ← rotinas: ingerir, consultar, revisar
└── templates/         ← modelos de página e de ORIGEM.md
```

## As 3 rotinas

| Rotina | Quando usar | O que faz |
|---|---|---|
| **Ingerir** | Entrou arquivo novo no `raw/` | Lê, resume, cria ou atualiza páginas do wiki |
| **Consultar** | Precisa de uma resposta | Lê o `index.md`, abre as páginas certas, responde com fonte |
| **Revisar** (lint) | 1 vez por semana | Acha contradição, página órfã, link quebrado, lacuna |

Detalhes em [skills/](skills/).

## Como usar

1. Coloque o arquivo bruto em `raw/<tema>/`. Exemplo: `raw/trafego/aula-03-meta-ads.md`.
2. Peça ao agente: **"ingere os arquivos novos do raw"**.
3. Para consultar: **"segundo o wiki, como devo analisar CPL alto?"**.

## Cursos que chegam de outra pessoa

Este wiki começou vazio. Os cursos chegam aos poucos.

1. O curso chega em `raw/<tema>/<curso>/` por um commit no GitHub.
2. Dentro dele vem um `ORIGEM.md`: de onde veio, quem mandou, quando.
3. Você faz `git pull` e pede ao agente: **"ingere os arquivos novos do raw"**.
4. O agente cria as páginas do `wiki/` do seu jeito, ligadas ao que você já tem.

Você também pode colocar seus próprios cursos em `raw/`. Funciona igual.

## Como outro agente usa este wiki

Este repositório fica separado. Os outros repositórios só apontam para cá.

Exemplo dentro de uma skill de marketing:

```markdown
## Base de conhecimento
Antes de analisar campanhas, consulte o wiki de tráfego:
1. Leia `wiki-conhecimento/wiki/index.md`.
2. Abra as páginas de `wiki/trafego/` ligadas ao problema.
3. Cite a página usada em cada recomendação.
Não copie o conteúdo do wiki para este repositório.
```

O agente precisa ter acesso de leitura a este repositório (clone local ou chave de deploy).

## Crédito

Método: Andrej Karpathy, "LLM Wiki" (abril de 2026).
Esta é uma adaptação em português, criada pelo Henrique e compartilhada como modelo.
