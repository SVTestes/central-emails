# Plataforma: FluentCRM (WordPress)

> Regras e particularidades para montar HTML de e-mail enviado pelo FluentCRM (plugin do WordPress).
> Só descreve o que é **específico** do FluentCRM — as regras gerais estão no `README.md` da raiz.
> Legenda: ✅ confirmado em doc/prática · ⚠️ confirmar na prática antes de confiar.

## Smart Codes / merge tags (personalização)

- ✅ Formato: `{{GrupoDeDados.Propriedade|Fallback|Transformador}}`.
- ✅ Exemplos:
  - `{{contact.first_name}}` → primeiro nome.
  - `{{contact.first_name|Amigo}}` → primeiro nome, com "Amigo" caso esteja vazio (o **fallback** é a defesa contra saudação vazia).
  - `{{contact.first_name|Amigo|ucfirst}}` → ainda coloca a primeira letra em maiúscula.
  - `{{contact.email}}`, `{{contact.last_name}}`.
- ✅ Grupos comuns: `contact`, `contact.custom` (campos personalizados), `wp` (dados do usuário WordPress), `crm` (dados gerais da conta).
- 💡 No editor, digitar `@` ou clicar no botão **SmartCode** abre a lista para copiar o código certo.

## Rodapé / descadastro obrigatório (compliance)

- ✅ O FluentCRM valida uma "compliance string" — **exige** link de descadastro. Sem isso, ele avisa/bloqueia.
- ✅ Smart codes de rodapé:
  - `##crm.unsubscribe_url##` → URL de descadastro.
  - `##crm.manage_subscription_url##` → central de preferências (gerenciar assinatura).
  - `##web_preview_url##` → ver e-mail no navegador.
  - `{{crm.business_name}}` e `{{crm.business_address}}` → nome e endereço do negócio.
- 💡 Uso típico no rodapé: `[Cancelar inscrição](##crm.unsubscribe_url##) | [Preferências](##crm.manage_subscription_url##)`.
- ⚠️ **`##web_preview_url##` não funciona em e-mail de teste** — só resolve no envio real. Não ache que quebrou ao testar.

## Editores e como o HTML é tratado

- ✅ Dois modos de editor: **Block Editor (Gutenberg)** e o clássico/**HTML puro**.
- 💡 Para HTML montado à mão, use o modo de **HTML puro** (o Gutenberg pode reempacotar o conteúdo em blocos).
- ⚠️ Já houve bug em que o editor Gutenberg **rejeitava URLs com SmartCode dentro de link** ao salvar (o WordPress tratava o placeholder como URL inválida). Corrigido a partir do FluentCRM 3.1.5. Se aparecer erro ao salvar link com `##...##`, verificar a versão do plugin.
- ⚠️ Mesmo no HTML puro, mantenha CSS inline / tabela / 600px — os clientes de e-mail continuam sendo o gargalo.

## Entrega / envio

- ⚠️ O FluentCRM manda pelo serviço de e-mail do próprio site WordPress (normalmente via FluentSMTP ou outro plugin de SMTP). **Deliverability depende dessa configuração de SMTP**, não do HTML. Se e-mail não chega, checar o SMTP do site antes de suspeitar do HTML.

## Aprendizados

<!-- Grave aqui todo aprendizado novo sobre o FluentCRM, com data. -->

- _2026-07-08 — os campos de rodapé `{{crm.business_name}}` e `{{crm.business_address}}` só renderizam se as **Business Settings do FluentCRM estiverem preenchidas**. Se vierem vazios no e-mail, checar essa configuração antes de suspeitar do HTML. (Confirmado no projeto Hotel Fazenda Ramon, onde o FluentCRM é remetente secundário; o HTML é montado no Stripo — ver `plataformas/stripo.md`.)_
