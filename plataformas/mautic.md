# Plataforma: Mautic

> Regras e particularidades para montar HTML de e-mail enviado pelo Mautic.
> Só descreve o que é **específico** do Mautic — as regras gerais estão no `README.md` da raiz.
> Legenda: ✅ confirmado em doc/prática · ⚠️ confirmar na prática antes de confiar.

## Tokens (personalização)

- ✅ Formato: `{contactfield=alias}`. Ex.: `{contactfield=firstname}`, `{contactfield=email}`.
- ✅ Valor padrão (fallback): `{contactfield=firstname|Amigo}` → usa "Amigo" se o campo estiver vazio.
- ✅ Campos de data com formatação: `{contactfield=ALIAS|date}`, `{contactfield=ALIAS|time}`, `{contactfield=ALIAS|datetime}`.
- ✅ Campos personalizados viram token pelo alias: `{contactfield=favorite_product}`.

## Descadastro / view online obrigatórios

- ✅ Tokens de descadastro (colocar no rodapé, no local que preferir):
  - `{unsubscribe_url}` → só a URL (você escreve o texto do link em volta).
  - `{unsubscribe_text}` → já insere a frase padrão com o link (configurável no global settings).
  - `{dnc_url}` → "descadastrar de todos os e-mails" (Do Not Contact).
- ✅ Ver no navegador:
  - `{webview_url}` → só a URL da versão online.
  - `{webview_text}` → frase padrão "Está com problema para ler? Clique aqui.".
- ⚠️ Se você usar `{unsubscribe_url}` (o token cru), o `{unsubscribe_text}` deixa de aparecer — não coloque os dois esperando os dois.

## Code Mode vs Builder (isto evita muita dor de cabeça)

- ✅ Mautic tem dois jeitos de editar: o **Builder GrapesJS** (arrastar e soltar) e o **Code Mode** (HTML direto).
- 💡 **Para HTML montado à mão / de terceiro, use o Code Mode.** No seletor de tema, escolha "code mode"; abre a aba "advanced" para colar o HTML. O builder GrapesJS pode mexer/quebrar HTML colado.
- ⚠️ **Cuidado:** depois que você troca um Tema para Code Mode, o conteúdo vira HTML e **não dá pra voltar** para o Tema. Decida antes.

## Tracking / pixel

- ✅ O Mautic injeta o pixel de rastreio automaticamente logo antes de `</body>`.
- ⚠️ Se quiser controlar onde ele fica, use o token `{tracking_pixel}` no corpo — mas **não** coloque logo depois do `<body>`, porque isso atrapalha o pre-header (texto de prévia) em alguns clientes.
- 💡 Para não rastrear cliques de um link específico, adicione o atributo `mautic:disable:tracking="true"` na tag `<a>`.

## Boas práticas específicas do Mautic

- Sempre "Auto Generate" da versão texto e mandar um envio de teste antes do disparo real.
- Manter CSS inline, layout em tabela, largura ~600px (padrão de e-mail).

## Aprendizados

<!-- Grave aqui todo aprendizado novo sobre o Mautic, com data. -->

- _(vazio por enquanto — vai sendo preenchido conforme a equipe usar)_
