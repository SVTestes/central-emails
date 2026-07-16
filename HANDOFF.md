# HANDOFF — Central de E-mails (SVTestes/central-emails)

> Documento de contexto para quem (humano ou IA) precisar operar, corrigir ou evoluir este projeto.
> **Última atualização:** 2026-07-09 · **Status: no ar e validado de ponta a ponta.**
> Para *usar* a central (criar e-mail), leia o `README.md` — este arquivo é sobre o **projeto em si**.

---

## 1. Por que este projeto existe

A Nara (copywriter/SEO da Special Vision) mantinha **um projeto separado no Claude para cada cliente**,
com as instruções de como montar o HTML dos e-mails daquele cliente. Ela puxava as conversas desse
projeto para criar cada e-mail novo.

**O problema:** o limite de token estourava no meio do trabalho e ela ficava travada — e não conseguia
continuar no GPT, porque o contexto estava preso no projeto do Claude.

**A solução:** centralizar tudo num repositório GitHub em arquivos `.md`/`.html`, que **tanto o Claude
Code quanto o Codex do GPT conseguem ler**. Se um estourar o limite, abre o outro na mesma pasta e
continua de onde parou. O contexto vive nos arquivos, não na conversa.

**Objetivo maior:** estrear com a Unique Cafés, mas criar um **padrão que sirva para todos os clientes**
da SV daqui pra frente.

---

## 2. Status atual

| Item | Status |
|---|---|
| Repositório `SVTestes/central-emails` (privado) | ✅ no ar |
| `README.md` (cérebro do fluxo) | ✅ |
| `plataformas/` — activecampaign, fluentcrm, mautic, stripo | ✅ |
| 5 clientes com `instrucoes.md` real | ✅ |
| 9 HTMLs de referência | ✅ |
| `_prompts/` — coleta e importação de cliente | ✅ |
| `CLAUDE.md` + `AGENTS.md` (auto-carregar o fluxo) | ✅ |
| Teste real no Claude Code (Doces Vovó) | ✅ passou — e-mail no repo |
| Teste no Codex Web | ✅ gerou HTML (ficou no ambiente interno — ver §7) |
| Claude Code na máquina da Nara | ✅ instalado |
| `COMO-USAR.md` (guia da Nara) | ✅ |
| E-mail de demonstração (Unique · Mel de Laranjeiras) | ✅ no repo |

---

## 3. Estrutura do repositório

```
central-emails/
├── README.md              ← CÉREBRO: o fluxo obrigatório de criação de e-mail
├── CLAUDE.md              ← adaptador: Claude Code carrega isto sozinho → aponta pro README
├── AGENTS.md              ← adaptador: Codex carrega isto sozinho → replica o fluxo
├── COMO-USAR.md           ← guia de uso escrito para a Nara (não técnico)
├── HANDOFF.md             ← este arquivo
├── plataformas/
│   ├── activecampaign.md  ← REMETENTE (quem dispara)
│   ├── fluentcrm.md       ← REMETENTE
│   ├── mautic.md          ← REMETENTE (nenhum cliente usa hoje)
│   └── stripo.md          ← BUILDER (onde o HTML é montado) — usado por TODOS os clientes
├── clientes/
│   ├── unique-cafes/        instrucoes.md + emails/ (4 refs + 1 gerado*)
│   ├── doces-vovo/          instrucoes.md + emails/ (2 refs + 1 gerado*)
│   ├── pedra-mistica/       instrucoes.md + emails/ (2 refs)
│   ├── hotel-fazenda-ramon/ instrucoes.md + emails/ (1 ref)
│   └── portal-idea/         instrucoes.md + emails/ (VAZIA — ver §6)
├── _modelo-cliente/       ← copiar p/ criar cliente novo
└── _prompts/
    ├── coletar-dados-cliente.md   ← Nara roda no projeto de IA do cliente p/ extrair dados
    └── importar-cliente.md        ← Claude Code monta a pasta do cliente a partir do material
```

> `ref_*.html` = e-mail herdado, feito antes da central (referência visual do padrão do cliente).
> `AAAA-MM-DD_*.html` = e-mail criado **pelo fluxo**. Os dois `*gerado*` marcados acima são as saídas
> dos testes de validação e **contêm placeholders `[ ... ]`** — servem de exemplo do fluxo, **não são
> e-mails prontos para disparo**:
> - `unique-cafes/emails/2026-07-09_lancamento-mel-de-laranjeiras.html` (registro Revista, 52,8 KB)
> - `doces-vovo/emails/2026-07-09_newsletter-blog-julho.html` (teste real no Claude Code, 71,7 KB)

---

## 4. O fluxo (resumo — detalhe no `README.md`)

1. Identifica o **cliente** do pedido → abre `clientes/<slug>/`
2. Lê `instrucoes.md` do cliente (tipografia, cores, design, tom de voz)
3. Lê os campos **"Plataforma de envio"** e **"Builder de HTML"** no topo do `instrucoes.md`
4. Lê `plataformas/<remetente>.md` **E** `plataformas/<builder>.md`
5. Usa os HTMLs de `clientes/<slug>/emails/` como referência visual
6. Monta e **salva** em `clientes/<slug>/emails/` (`AAAA-MM-DD_assunto-curto.html`)

**Regra de aprendizado contínuo:** aprendizado de cliente → `.md` do cliente; aprendizado de
plataforma/builder → `.md` da plataforma. É assim que a base fica mais inteligente sozinha.

---

## 5. Decisões travadas (não reabrir sem motivo forte)

1. **Remetente ≠ Builder.** O remetente dispara (ActiveCampaign/FluentCRM/Mautic); o builder monta o
   HTML (Stripo). São arquivos separados em `plataformas/` e o fluxo lê **os dois**.
   *Motivo:* os 5 clientes usam Stripo, e quase tudo que quebra o HTML é regra do Stripo, não do
   remetente. Sem essa separação, a regra ficaria duplicada em 5 lugares.
2. **O `instrucoes.md` de cada cliente é o documento original da Nara**, com um cabeçalho de metadados
   prefixado no topo. *Motivo:* os documentos dela são muito mais ricos que o template genérico —
   espremê-los no template perderia detalhe.
3. **Clientes ficam dentro de `clientes/`**, e os HTMLs dentro de `clientes/<slug>/emails/`.
4. **Nunca inventar dado de produto** (preço, ficha, nota, peso, link). Sem o dado real da página do
   produto → placeholder `[ ... ]`. Esta regra vem dos próprios `instrucoes.md` dos clientes e já foi
   validada no teste real.
5. **Slug:** minúsculas, sem acento, com hífen (`unique-cafes`, `doces-vovo`, `pedra-mistica`,
   `hotel-fazenda-ramon`, `portal-idea`).

---

## 6. Pendências / pontos em aberto

1. **Portal IDEA sem HTML de referência.** É o único cliente com `emails/` vazia — não veio HTML dele
   no material. Quando a Nara tiver um, adicionar.
2. **Rodapé/descadastro da Doces Vovó — CONFIRMAR COM A NARA.** No teste real, o e-mail gerado saiu
   **sem** as merge tags `%UNSUBSCRIBELINK%` / `%SENDER-INFO-SINGLELINE%`. Provavelmente é **por
   design**: o `instrucoes.md` dela diz que o footer laranja é "locked" no template master do Stripo e
   ela transplanta só o corpo. **Se a Nara esperar o e-mail completo com descadastro**, adicionar uma
   linha no `instrucoes.md` da Doces Vovó mandando incluir o bloco de rodapé — e o Claude passa a fazer
   sozinho.
3. **Contradição do `esd-block-html`.** O doc do Portal IDEA usa a diretriz **oposta** à dos outros
   (nunca usar `esd-block-html`, resolver via `bgcolor`/`style` no `esd-container-frame`). Está
   registrada como ⚠️ em `plataformas/stripo.md`. **Confirmar com a Nara qual vale por cliente** — não
   assumir.
4. **Dois HTMLs de referência da Unique acima do limite do Gmail:** `ref_lancamento.html` (~104 KB) e
   `ref_newsletter.html` (~103 KB), contra o limite de ~102 KB. Não foram alterados (são referência
   fiel), mas ao gerar e-mail novo **vigiar o peso**.
5. **Padrão de commit da Nara — DECIDIR.** Ela usa GitHub Desktop (Commit + Push) **ou** pede
   "salva e faz o commit" pro Claude Code? Escolher **um** caminho e escrever no `COMO-USAR.md`, pra
   ela não misturar.
6. **Codex como plano B — decidir se ativa.** Exige conta ChatGPT paga. O encanamento já existe
   (`AGENTS.md`). Ver §7 sobre a diferença de comportamento.
7. **Campos `NÃO_VERIFICADO`** que sobrarem em algum `instrucoes.md` → completar conforme o dado real
   aparecer.

---

## 7. Claude Code vs. Codex — diferença que importa

| | Claude Code | Codex Web |
|---|---|---|
| Onde roda | Local, na pasta da máquina | Nuvem (ambiente interno) |
| Lê | `CLAUDE.md` | `AGENTS.md` |
| Salva | Direto na pasta local | Numa pasta interna → precisa **"Create PR"** pra ir ao GitHub |
| Continuidade | — | Trabalha em cima do que **já está no GitHub** |

⚠️ **Consequência prática:** se o Claude Code travar no meio, é preciso **subir o que já tem**
(commit + push) **antes** de continuar no Codex Web — senão ele não enxerga o trabalho.

⚠️ **No Codex, o e-mail gerado fica na pasta interna dele e some quando a tarefa fecha.** Sempre
mandar ele abrir o PR ("Create PR"), senão o e-mail não entra na base.

**Avaliação honesta:** o Claude Code sozinho já reduz muito o problema original (lê arquivos sob
demanda em vez de acumular contexto na conversa). O Codex é **seguro extra**, não requisito.

---

## 8. Troubleshooting — problemas já vividos e como resolver

### `fatal: not a git repository`
Você está fora da pasta do repo. Rode `pwd` — tem que mostrar
`C:\Users\Victor\Documents\GitHub\central-emails`. **Sempre `cd` + `pwd` antes de qualquer operação.**
*(Já aconteceu: um `Copy-Item` rodou em `C:\Users\Victor\` e criou um `clientes\` órfão na pasta pessoal.)*

### Zip aninhado (pasta dentro de pasta com o mesmo nome)
Sintoma: `git status` mostra uma pasta `central-emails/` **dentro** de `central-emails/`.
Correção:
```powershell
Move-Item -Path .\central-emails\* -Destination . -Force
Remove-Item .\central-emails -Recurse -Force
```
*Sempre conferir com `Get-ChildItem` se os arquivos estão no nível certo antes de commitar.*

### `Get-ChildItem : não é possível localizar o caminho 'C:\Downloads\...'`
Variável de ambiente errada. É **`$env:USERPROFILE`** (não `$env:Victor`). Ou use o caminho completo:
`C:\Users\Victor\Downloads\...`

### Claude Code no terminal: `API Error: 401 Invalid authentication credentials`
Sessão expirada. Rode `/login` dentro do Claude Code. **Alternativa que funcionou:** usar o
**app do Claude → aba Code** (já logado na conta Special Vision · Max) em vez do terminal.

### `warning: LF will be replaced by CRLF`
**Não é erro.** É só o Git ajustando quebra de linha no Windows. Ignorar.

### Repositório não aparece no Codex
- Repo privado/novo demora ~5 min pra indexar. Esperar e recarregar.
- Repo em **organização (SVTestes)** pode exigir que um owner **instale/aprove o GitHub App do
  ChatGPT na organização** — não basta acesso pessoal.

### Copiar HTML do Codex sem lixo de diff
Peça: *"Mostra o conteúdo completo desse arquivo HTML dentro de um bloco de código, sem mais nada"* →
use o botão de copiar do bloco. Copiar da tela de diff traz `+` no início das linhas.

### Histórico: o repo já se chamou `email-marketing-ia`
Foi renomeado para `central-emails`. O remote local já foi atualizado
(`git remote set-url origin https://github.com/SVTestes/central-emails.git`). Se algo apontar pro nome
antigo, é isso.

---

## 9. Convenções

**Git:** `pwd` + `git status` antes de qualquer operação · `git add` **explícito do caminho**
(nunca `git add .`) · um commit por unidade lógica · mensagem convencional
(`feat:`, `docs:`, `chore:`) · `main` é a fonte de verdade.

**Nome de arquivo de e-mail:** `AAAA-MM-DD_assunto-curto.html` · variação: sufixo `_v2` ·
referências herdadas usam prefixo `ref_`.

**Ambiente:** Windows + PowerShell · GitHub Desktop (Nara) · app do Claude → aba **Code**.

---

## 10. Pessoas

| Pessoa | Papel neste projeto |
|---|---|
| **Nara** | Dona do conteúdo: copy, SEO, instruções de cada cliente. **É a usuária final.** Fonte de verdade sobre tom de voz e regras de cliente. |
| **Victor** | Montou e mantém a base. Ponto de apoio técnico da Nara. |
| **Samuel** | Tech lead — gate de decisões arquiteturais estruturais. |
| **Lucas** | Hospeda imagens na CDN (`content.app-us1.com`) e implementa no Stripo (Unique). |
| **Carlos** | Automações, RSS, timers Sendtric (Unique). |
| **Rodrigo / Vih** | Design/arte — play buttons embutidos no banner (compatibilidade Outlook). |

---

## 11. Clientes e plataformas

| Cliente | Slug | Remetente | Builder |
|---|---|---|---|
| Unique Cafés | `unique-cafes` | ActiveCampaign | Stripo |
| Doces Vovó | `doces-vovo` | ActiveCampaign (imagens via WordPress) | Stripo |
| Pedra Mística | `pedra-mistica` | ActiveCampaign | Stripo |
| Hotel Fazenda Ramon | `hotel-fazenda-ramon` | ActiveCampaign (primária) + FluentCRM (secundária) | Stripo |
| Portal IDEA | `portal-idea` | ActiveCampaign | Stripo |

> Nenhum cliente usa **Mautic** hoje. O `.md` dele existe porque estava no escopo original.

---

## 12. O que foi validado empiricamente (não é teoria)

- **Teste real no Claude Code** (Doces Vovó, newsletter de blog): ele leu as regras certas sozinho,
  aplicou a paleta correta (`#fdf6ec`, `#1cb01f`, `#7a5c3a`), montou com hierarquia Stripo válida,
  ficou em **71,7 KB** (abaixo do limite do Gmail) e **não inventou preço** — os únicos valores `R$`
  eram os de frete grátis documentados no `instrucoes.md`.
- **ActiveCampaign:** o rodapé padrão só some com **`%UNSUBSCRIBELINK%` + `%SENDER-INFO%`** (ou
  `%SENDER-INFO-SINGLELINE%`) — os **dois**. Só um → o rodapé padrão continua.
- **ActiveCampaign:** toda `<a>` de imagem precisa de `href`, senão o validador acusa "Empty Text/Image".
- **FluentCRM:** `{{crm.business_name}}` / `{{crm.business_address}}` só renderizam se as **Business
  Settings** estiverem preenchidas.
- **Stripo:** sem a hierarquia `esd-stripe → esd-structure → esd-container-frame → esd-block-*`, o bloco
  aparece **travado** (não editável) no editor.
- **Gmail** corta e-mail acima de **~102 KB**, escondendo rodapé e descadastro.
