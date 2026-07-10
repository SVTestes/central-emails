# CLAUDE.md — Central de E-mails SV

Você está operando a central de e-mail marketing da Special Vision.

**Antes de qualquer tarefa, leia e siga o `README.md` por completo.** Ele é o cérebro do fluxo:
como identificar o cliente, ler as instruções dele, ler as regras de plataforma (remetente) e de
builder (Stripo), usar os HTMLs de referência e onde salvar o e-mail novo.

@README.md

## Regras que valem sempre (resumo — o detalhe está no README e nos .md de plataforma)

- **Nunca invente dados de produto** (preço, ficha técnica, nota, avaliação, peso). Se não tiver o
  dado real da página do produto, use placeholder `[ ... ]` e sinalize.
- Todo e-mail novo é salvo em `clientes/<slug>/emails/` com nome `AAAA-MM-DD_assunto-curto.html`.
- **Aprendizado de cliente** → grave em `clientes/<slug>/instrucoes.md` (seção Aprendizados).
  **Aprendizado de plataforma/builder** → grave em `plataformas/<nome>.md` (seção Aprendizados).
- Git: rode `pwd` + `git status` antes; use `git add` explícito do caminho (nunca `git add .`);
  commit convencional; um commit por unidade lógica.
