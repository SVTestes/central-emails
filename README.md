# Central de E-mails — Special Vision

> **Este arquivo é o cérebro do fluxo.** Se você é um agente de IA (Claude Code ou Codex),
> leia este arquivo **inteiro** antes de montar qualquer e-mail. Ele define o passo a passo
> obrigatório e as convenções da base.

## O que é este repositório

Base central de instruções e HTMLs de e-mail marketing dos clientes da Special Vision.
O objetivo é que qualquer pessoa da equipe consiga pedir um e-mail para um cliente e o
agente monte o HTML correto, seguindo o padrão daquele cliente e as regras da plataforma
de envio que ele usa — sem depender de conversas soltas que estouram limite de token.

Como tudo vive aqui em arquivos `.md` e `.html`, o fluxo funciona igual no **Claude Code**
e no **Codex do GPT**: se um estourar o limite, é só abrir o outro e continuar de onde parou.

## Estrutura do repositório

```
central-emails/
├── README.md                  ← este arquivo (o cérebro)
├── plataformas/               ← regras de envio (remetente) e de builder de HTML
│   ├── activecampaign.md      ← remetente
│   ├── fluentcrm.md           ← remetente
│   ├── mautic.md              ← remetente
│   └── stripo.md              ← builder de HTML (usado junto com o remetente)
├── clientes/                  ← uma pasta por cliente
│   └── <slug-do-cliente>/
│       ├── instrucoes.md      ← tipografia, cores, design, tom de voz, plataforma, builder
│       └── emails/            ← HTMLs criados para esse cliente (referência + novos)
│           └── ...
├── _modelo-cliente/           ← modelo para criar um cliente novo (copiar e renomear)
│   ├── instrucoes.md
│   └── emails/
└── _prompts/                  ← prompts reutilizáveis (coleta e importação de cliente)
    ├── coletar-dados-cliente.md
    └── importar-cliente.md
```

> **Remetente x Builder.** O *remetente* é quem dispara (ActiveCampaign, FluentCRM, Mautic).
> O *builder* é onde o HTML é montado (hoje, quase sempre **Stripo**). São coisas diferentes e
> podem ter regras próprias — por isso o cabeçalho do `instrucoes.md` de cada cliente traz os
> dois campos: **"Plataforma de envio"** e **"Builder de HTML"**.

## FLUXO OBRIGATÓRIO para criar um e-mail

Sempre que alguém pedir um e-mail, siga **nesta ordem**, sem pular etapa:

1. **Identifique o cliente** do pedido (ex.: "HTML de Dia do Cliente pra Unique Cafés" → cliente = Unique Cafés).
   - Ache a pasta em `clientes/<slug>/`. Se houver dúvida sobre qual pasta é, **pergunte** antes de continuar; não invente.
2. **Leia `clientes/<slug>/instrucoes.md`** por completo (tipografia, cores, design, tom de voz).
3. **Identifique a plataforma de envio e o builder** desse cliente — estão nos campos "Plataforma de envio" e "Builder de HTML" no topo do `instrucoes.md`.
4. **Leia os `.md` de plataforma que se aplicam**, por completo (o que funciona, o que quebra, tags obrigatórias):
   - Sempre o do **remetente**: `plataformas/<remetente>.md` (ex.: `activecampaign.md`).
   - E o do **builder**, se houver: `plataformas/<builder>.md` (ex.: `stripo.md`).
   - Se o cliente tiver mais de um remetente (ex.: Hotel Ramon = ActiveCampaign + FluentCRM), leia os dois e priorize o primário, salvo indicação do pedido.
5. **Olhe os HTMLs recentes** em `clientes/<slug>/emails/` para copiar o padrão visual e a estrutura já validada.
6. **Só então monte o e-mail**, combinando: o pedido + o `instrucoes.md` do cliente + as regras da plataforma + a referência dos HTMLs.
7. **Salve o HTML novo** em `clientes/<slug>/emails/` (ver convenção de nome abaixo).
8. **Rode o checklist final** (abaixo) antes de entregar.

## Onde salvar e como nomear

- Todo e-mail novo é salvo em `clientes/<slug>/emails/`.
- Nome do arquivo: `AAAA-MM-DD_assunto-curto.html`
  - Ex.: `2026-07-08_dia-do-cliente.html`
- Se for variação de um existente, acrescente sufixo: `..._v2.html`.

## REGRA DE APRENDIZADO CONTÍNUO (importante)

A base tem que ficar mais inteligente sozinha com o tempo. Então:

- **Aprendizado sobre um cliente** (uma regra de escrita, uma preferência de design, um bug que
  aconteceu no e-mail dele) → grave no `clientes/<slug>/instrucoes.md`, na seção **"Aprendizados"**.
- **Aprendizado sobre uma plataforma** (algo do HTML que quebrou, um tag que faltou, um comportamento
  novo) → grave no `plataformas/<plataforma>.md`, na seção **"Aprendizados"**. Repare se o aprendizado é
  do **remetente** (ActiveCampaign/FluentCRM/Mautic) ou do **builder** (Stripo) e grave no arquivo certo —
  assim ele passa a valer para todos os clientes que usam aquela ferramenta.

Sempre registre o aprendizado no **momento** em que ele aparece, com data. Não deixe pra depois.

## Convenções gerais de HTML de e-mail (valem para TODOS os clientes)

Estas são regras de base de e-mail. Cada arquivo de plataforma só descreve as **diferenças**
e particularidades dela — o que estiver aqui vale sempre, salvo indicação em contrário:

- **Layout em tabelas** (`<table>`), não em `<div>` com flex/grid. Clientes de e-mail (Outlook, Gmail) ignoram muito CSS moderno.
- **CSS inline** nos elementos (`style="..."`). Não confie em `<style>` no `<head>` — várias plataformas e clientes removem.
- **Largura máxima ~600px** para o container principal.
- **Imagens hospedadas em URL absoluta** e com `alt` preenchido; nunca embutir imagem como base64.
- **Botões (CTA) feitos com tabela/`<a>` estilizado**, não `<button>`.
- **Fontes web-safe com fallback**; fontes de marca podem não renderizar em todo cliente (definir fallback no `instrucoes.md` do cliente).
- **Sempre incluir link de descadastro e endereço/identificação do remetente** — cada plataforma tem os tags próprios (ver arquivo da plataforma). Sem isso, muitas plataformas **não enviam**.
- **Testar o envio de teste** antes de disparar de verdade.

## Checklist final antes de entregar

- [ ] O e-mail seguiu o `instrucoes.md` do cliente (fonte, cores, tom de voz)?
- [ ] Usei os tags/tokens corretos da plataforma desse cliente (ver `plataformas/<plataforma>.md`)?
- [ ] Incluí descadastro e identificação do remetente no formato que a plataforma exige?
- [ ] Layout em tabela, CSS inline, largura ~600px, imagens em URL absoluta?
- [ ] Salvei o HTML em `clientes/<slug>/emails/` com o nome no padrão `AAAA-MM-DD_assunto.html`?
- [ ] Registrei qualquer aprendizado novo no `.md` do cliente ou da plataforma?
