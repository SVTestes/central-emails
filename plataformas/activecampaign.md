# Plataforma: ActiveCampaign

> Regras e particularidades para montar HTML de e-mail que vai ser enviado pelo ActiveCampaign.
> Só descreve o que é **específico** do AC — as regras gerais estão no `README.md` da raiz.
> Legenda: ✅ confirmado em doc/prática · ⚠️ confirmar na prática antes de confiar.

## Tags de personalização

- ✅ Formato: `%TAG%`. Ex.: `%FIRSTNAME%`, `%LASTNAME%`, `%EMAIL%`.
- ✅ Os tags são gerados automaticamente a partir dos campos da conta. O nome do campo vira o tag.
- ✅ **Não use hífen** em tags de campos personalizados — o AC remove hífens automaticamente.
- ✅ Se o tag for uma URL, ela precisa incluir o esquema (`https://`), senão não vira link clicável.
- ⚠️ Campanhas em **texto puro (plain-text) não suportam tags de personalização** nem edição de rodapé. Sempre que precisar de personalização, use a campanha HTML.

## Rodapé obrigatório (isto aqui quebra o envio se faltar)

- ✅ O ActiveCampaign **exige** link de descadastro e endereço físico do remetente. Sem isso, a campanha não envia.
- ✅ Para substituir/remover o rodapé padrão, o e-mail precisa ter **os dois** tags:
  - `%UNSUBSCRIBELINK%` → o link de descadastro.
  - `%SENDER-INFO%` (várias linhas) **ou** `%SENDER-INFO-SINGLELINE%` (uma linha) → o endereço/identificação do remetente.
- ✅ Só quando **os dois** estão presentes é que o rodapé padrão some e passa a valer o seu. Se só um estiver, o AC mantém o rodapé padrão dele em cima do seu.
- ⚠️ Escrever "Cancelar inscrição" ou digitar o endereço como texto **não funciona** — tem que ser via os tags acima.

## Como o HTML é tratado

- ✅ Dois editores: **Email Designer** (novo, 2022) e **Classic Designer**. Para HTML montado à mão, importe como HTML personalizado.
- ⚠️ Mantenha CSS inline e layout em tabela (padrão de e-mail). O AC processa/reescreve parte do CSS — não confie em `<style>` no head.
- ⚠️ Largura ~600px, imagens em URL absoluta.

## Boas práticas específicas do AC

- Preferir **Preference Center / gerenciamento de preferências** em vez de só descadastro seco, quando o cliente tiver isso configurado (reduz descadastro total).
- Testar sempre o preview e um envio de teste antes de disparar, porque o rodapé só aparece montado no envio real.

## Aprendizados

<!-- Grave aqui todo aprendizado novo sobre o ActiveCampaign, com data.
Ex.: "2026-07-08 — tag %FIRSTNAME% veio vazio quando o campo estava em branco; usar saudação neutra de fallback no texto." -->

- _(vazio por enquanto — vai sendo preenchido conforme a equipe usar)_
