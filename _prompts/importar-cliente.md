# Prompt: Importar cliente para a central de e-mails

> **Como usar (para a Nara):** abra o Claude Code (ou o Codex) dentro deste repositório e mande:
>
> *"Leia `_prompts/importar-cliente.md` e siga o processo. Material do cliente abaixo:"*
>
> …e cole o material logo em seguida. Não precisa formatar nada — pode colar cru.

---

## Objetivo

A partir do material bruto de **um** cliente (instruções + plataforma + HTMLs), criar a pasta
desse cliente na estrutura correta do repositório, preencher o `instrucoes.md` no padrão e salvar
os HTMLs como referência. Ao final, fazer o commit.

## Antes de começar (obrigatório)

1. Leia o `README.md` da raiz por completo — ele define a estrutura e as convenções da base.
2. Leia o `_modelo-cliente/instrucoes.md` — é o formato exato que o `instrucoes.md` do cliente deve seguir.

## Entrada esperada

O usuário vai colar, para **um** cliente:
- O **nome** do cliente.
- A **plataforma** de envio (pode vir descrita em linguagem solta — ver mapeamento abaixo).
- O **texto de instruções** que hoje está no projeto de IA daquele cliente (cru, pode estar bagunçado).
- Um ou mais **HTMLs** de e-mails já criados (arquivo `.html` ou o código colado).

Se algum desses itens não vier, **não invente** — siga com o que tem e liste o que faltou no relatório final.

## Processo

1. **Defina o slug** do cliente: minúsculas, sem acento, com hífen. Ex.: "Unique Cafés" → `unique-cafes`.
2. **Crie a pasta** `clientes/<slug>/` com um subfolder `emails/` dentro (espelhando `_modelo-cliente/`).
3. **Mapeie a plataforma** para um dos três valores válidos, confirmando o mapeamento no relatório:
   - "painel/ActiveCampaign" → `ActiveCampaign`
   - "WordPress / pelo site / FluentCRM" → `FluentCRM`
   - "Mautic" → `Mautic`
   - Se a descrição for ambígua, **pergunte** antes de gravar.
4. **Extraia dos HTMLs** os dados técnicos de design (é daqui que sai a maior parte do `instrucoes.md`):
   - `font-family` de títulos e de corpo (com o fallback web-safe presente).
   - Cores em hex (`#rrggbb`) — primária, secundária, fundo, texto, botão (fundo/texto).
   - Largura do container principal (`max-width`/`width`).
   - Estilo do botão/CTA (cor, cantos, tamanho, texto padrão).
   - Estrutura de header e rodapé.
5. **Preencha `clientes/<slug>/instrucoes.md`** seguindo o modelo. Regra de honestidade:
   - O que a Nara **afirmou** no texto → registre normalmente.
   - O que você **inferiu do HTML** → registre, mas marque com `(inferido do HTML)`.
   - O que **não foi possível determinar** → deixe o campo como `NÃO_VERIFICADO` em vez de chutar.
   - Nunca rotule algo como confirmado sem base real.
6. **Salve cada HTML** em `clientes/<slug>/emails/` com o nome `AAAA-MM-DD_assunto-curto.html`.
   - Se não souber a data de envio, pergunte; se não houver como saber, use a data de hoje e anote `(data estimada)` no relatório.
7. **Registre o campo Plataforma** no topo do `instrucoes.md` — é ele que o fluxo usa depois para achar o arquivo de plataforma certo.

## Regras de qualidade

- **Não invente dados.** Faltou algo essencial (plataforma, tom de voz, cor principal)? Pergunte ou marque `NÃO_VERIFICADO`.
- **Um cliente por vez, um commit por cliente.** Não misture dois clientes no mesmo commit.
- **Preserve os HTMLs originais** como vieram — eles são a referência visual validada. Não "melhore" nem reformate.

## Git (seguir o padrão do time)

1. `pwd` e `git status` **antes** de qualquer operação, para confirmar onde está e o que mudou.
2. `git add` **explícito do caminho do cliente** (ex.: `git add clientes/unique-cafes/`). **Nunca** `git add .`.
3. Commit com mensagem convencional, ex.: `feat(unique-cafes): adiciona pasta e instruções do cliente`.
4. **Confira o staging** antes de subir. Só então `git push`.

## Relatório final (sempre imprimir)

Ao terminar, mostre um resumo:
- Cliente e slug criados; plataforma definida (e o mapeamento usado).
- O que foi preenchido no `instrucoes.md` e o que ficou como `NÃO_VERIFICADO`.
- Quais HTMLs foram salvos e com quais nomes.
- **Perguntas pendentes** para a Nara (o que falta pra completar o cadastro).
- O commit feito (hash e mensagem).
