# AGENTS.md — Central de E-mails SV

Você está operando a central de e-mail marketing da Special Vision.

**Antes de qualquer tarefa, leia e siga o `README.md` por completo** — ele é o cérebro do fluxo e a
fonte de verdade. Este arquivo existe só para garantir que você carregue o fluxo automaticamente.

## Fluxo obrigatório (resumo — detalhe completo no `README.md`)

1. Identifique o **cliente** do pedido e abra `clientes/<slug>/`.
2. Leia `clientes/<slug>/instrucoes.md` por completo (tipografia, cores, design, tom de voz).
3. Identifique a **plataforma de envio** e o **builder** no topo do `instrucoes.md`.
4. Leia `plataformas/<remetente>.md` (ex.: `activecampaign.md`) **e** `plataformas/<builder>.md`
   (ex.: `stripo.md`).
5. Use os HTMLs de `clientes/<slug>/emails/` como referência visual.
6. Monte o e-mail e **salve em** `clientes/<slug>/emails/` (`AAAA-MM-DD_assunto-curto.html`).

## Regras que valem sempre

- **Nunca invente dados de produto** (preço, ficha, nota, avaliação, peso). Sem o dado real, use
  placeholder `[ ... ]` e sinalize.
- **Aprendizado de cliente** → `clientes/<slug>/instrucoes.md`. **Aprendizado de plataforma/builder**
  → `plataformas/<nome>.md`.
- Git: `pwd` + `git status` antes; `git add` explícito do caminho (nunca `git add .`); commit convencional.
