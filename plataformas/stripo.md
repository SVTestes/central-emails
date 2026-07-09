# Builder de HTML: Stripo

> Stripo é o **builder** onde o HTML dos e-mails é montado hoje em quase todos os clientes da SV.
> Ele não é o remetente — o disparo é feito pelo ActiveCampaign (e, em alguns casos, FluentCRM).
> **Sempre leia este arquivo junto com o `.md` do remetente do cliente.**
> As regras de base de e-mail estão no `README.md`; aqui vão as particularidades do Stripo.
> Legenda: ✅ confirmado na prática (contas SV) · ⚠️ confirmar antes de confiar.

## Por que o Stripo importa tanto

- ✅ O ActiveCampaign edita o e-mail de forma visual (drag & drop) **apenas** quando o HTML segue a
  estrutura de classes do Stripo. Se a estrutura se perde, o bloco aparece **travado** (não editável)
  no editor — é o erro mais comum e o mais chato de descobrir depois.

## Hierarquia OBRIGATÓRIA de classes

Toda célula de conteúdo tem que estar dentro desta cadeia, em todos os níveis de aninhamento:

```
esd-email-paddings            (td principal do wrapper)
└── esd-stripe                (faixa/seção horizontal)
    └── esd-structure         (linha de conteúdo)
        └── esd-container-frame   (célula de coluna)
            └── esd-block-[tipo]  (o bloco em si)
```

- ✅ **Nunca simplifique as tabelas a ponto de perder essas classes.** O Stripo depende delas para
  mover, copiar, salvar e editar blocos.
- ✅ Cards internos (imagem + texto + botão) precisam da hierarquia de 3 níveis **completa por dentro** também.
- ✅ Nenhum `<td>` com conteúdo pode ficar fora dessa cadeia.

### Classes de bloco válidas

`esd-block-banner` · `esd-block-text` · `esd-block-image` · `esd-block-button` · `esd-block-spacer`
· `esd-block-social` · `esd-block-menu` · `esd-block-html` · `esd-block-video`

## `esd-block-html` — a regra que mais gera dúvida

- ✅ Layouts customizados (card colorido com texto+valor, card de preço, card de objeção com borda
  lateral, caixa com ícone+título+descrição, bloco de métrica com número grande, qualquer "tabela
  visual" que não seja texto/botão/imagem puros) devem ser envolvidos em `<td class="esd-block-html">`
  — senão o Stripo trata como decoração estática e **não dá pra editar** no modo visual.
- Texto, botão e imagem puros usam `esd-block-text` / `esd-block-button` / `esd-block-image` (sem `esd-block-html`).
- ⚠️ **Contradição conhecida entre contas/templates:** em alguns projetos usou-se a diretriz **oposta**
  (nunca usar `esd-block-html`, resolver tudo via `bgcolor`/`style` no `esd-container-frame`). O
  comportamento do editor pode variar por conta/template. **Confirmar com a Nara qual abordagem vale
  para aquele cliente antes de iniciar** — não assumir.

## Padding e responsividade

- ✅ Preferir as classes utilitárias de padding do Stripo a styles inline quando der:
  `es-p5t`, `es-p10t`, `es-p15t`, `es-p20t`, `es-p30t`, `es-p40t` (e variações b/r/l).
- ✅ Imagens responsivas: `class="adapt-img"` + `style="display:block;"`.
- ✅ Grids 2×2 e multicoluna estáveis: `class="es-table-not-adapt"` na tabela externa + `style="table-layout:fixed"`.
- ✅ Sempre incluir a media query `@media (max-width: 600px)` no `<head>`.
- ⚠️ Largura do container varia por cliente (visto de **590px a 650px**) — isso é definição do cliente,
  fica no `instrucoes.md` dele, não aqui.

## Compatibilidade Outlook

- ✅ Botões "bulletproof" em VML, sempre pareados com o equivalente HTML dentro de `<!--[if !mso]>...<![endif]-->`.
- ✅ Multicoluna com comentários condicionais MSO + larguras em pixel explícitas + classes float `es-left` / `es-right`.
- ⚠️ Overlay de "play" em CSS sobre thumb de vídeo **não renderiza no Outlook** — o play deve vir
  embutido direto na imagem do banner (arte do designer), não como camada CSS.

## Imagens (hospedagem)

- ✅ Hospedar na CDN da conta (no AC: `content.app-us1.com`). **Nunca** hotlink de domínio externo
  (WordPress, `i.ytimg.com`, `blogspot`) — quebram e podem gerar overlay de play deformado.
- ✅ Ícones sociais costumam vir de `stripo.cluster.app-us1.com`.

## Timers (contagem regressiva)

- ✅ Feitos como **GIF animado** via serviço externo (ex.: Sendtric), dentro de `esd-block-html`.
- ✅ Renderização por cliente de e-mail: **Gmail e Outlook mostram só o 1º frame** (estático);
  **Apple Mail, iOS e Android** reproduzem a animação completa.

## Peso do arquivo

- ✅ Manter o HTML **abaixo de ~102 KB** — acima disso o Gmail corta o e-mail ("[Mensagem cortada]"),
  escondendo rodapé e descadastro.

## Aprendizados

<!-- Grave aqui todo aprendizado novo sobre o Stripo, com data. -->

- _2026-07-08 — arquivo criado consolidando as regras de Stripo que se repetiam nos projetos de Unique Cafés, Doces Vovó, Pedra Mística, Hotel Fazenda Ramon e Portal IDEA._
