# Regras do agente — Wiki de Conhecimento

Você mantém este wiki. O humano escolhe as fontes. Você organiza, resume e liga as páginas.

## Camadas

1. `raw/` — material bruto. **Nunca edite, nunca apague.** Só leia.
2. `wiki/` — o destilado. Só você escreve aqui.
3. Este arquivo — as regras. Só muda com pedido do dono do wiki.

## Onde cada coisa vai

| Tipo | Pasta | Exemplo |
|---|---|---|
| Conceito | `wiki/<tema>/conceitos/` | `cpl.md`, `funil-de-vendas.md` |
| Ferramenta | `wiki/<tema>/ferramentas/` | `meta-ads.md`, `gtm.md` |
| Pessoa ou autor | `wiki/<tema>/pessoas/` | `fulano-de-tal.md` |
| Resumo de uma fonte | `wiki/<tema>/fontes/` | mesmo nome do arquivo no `raw/` |
| Resposta salva | `outputs/` | `2026-10-07-analise-cpl.md` |

Temas novos: crie a pasta `raw/<tema>/` e `wiki/<tema>/` e registre no `wiki/index.md`.

## Formato de toda página do wiki

- Nome do arquivo: minúsculo, com hífen, sem acento. Ex.: `custo-por-lead.md`.
- Comece com o bloco de metadados (frontmatter):

```yaml
---
titulo: Custo por lead (CPL)
tipo: conceito        # conceito | ferramenta | pessoa | fonte | sintese
tema: trafego
fontes: [raw/trafego/aula-03-meta-ads.md]
atualizado: 2026-10-07
confianca: alta       # alta | media | baixa
---
```

- Depois: resumo de 2 a 3 linhas, detalhes em lista, e a seção `## Ligações` com links `[[outra-pagina]]`.
- Todo fato importante cita a fonte do `raw/`.
- Se duas fontes discordam, não escolha sozinho. Registre as duas na seção `## Divergências`.
- Português simples. Frases curtas.

## Rotinas

- Ingerir: siga `skills/ingerir/SKILL.md`.
- Consultar: siga `skills/consultar/SKILL.md`.
- Revisar: siga `skills/revisar/SKILL.md`.

## Sempre

1. Depois de qualquer mudança, atualize `wiki/index.md`.
2. Registre cada ingestão e revisão em `wiki/log.md` (só acrescente, nunca apague).
3. Não coloque segredo, senha, token, CPF ou dado de cliente no wiki.
4. Commit só com allowlist de arquivos. Nunca `git add .`.

## Cursos recebidos de outras pessoas

Alguns cursos chegam prontos de outra pessoa (por exemplo, enviados pelo Henrique).

1. Eles chegam em `raw/<tema>/<curso>/`, sempre com um `ORIGEM.md`.
2. O `ORIGEM.md` diz de onde veio, quem mandou e quando.
3. Trate como qualquer arquivo novo do `raw/`: rode a rotina Ingerir.
4. Não altere o que chegou. Se algo estiver errado, avise o dono do wiki.
