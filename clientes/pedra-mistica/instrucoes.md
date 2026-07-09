> **Plataforma de envio:** ActiveCampaign  ·  **Builder de HTML:** Stripo  ·  **slug:** `pedra-mistica`
> Instruções completas do cliente — fonte de verdade. O fluxo lê o campo "Plataforma de envio" acima para carregar o `.md` correspondente em `plataformas/`.
> _Migrado do projeto de IA da Nara em 2026-07-08._

---

# Projeto — E-mail Marketing Pedra Mística

> **Loja:** Pedra Mística — materiais para montagem de semijoias e bijuterias finas
> **Público:** revendedores e artesãs (B2B) — quem compra para **produzir e vender**
> **Plataformas:** HTML em **Stripo** → disparo via **ActiveCampaign**
> **Documento:** fonte única de verdade para redação, design e disparo dos e-mails

---

## 1. Missão

Criar e-mails de alta conversão para dois tipos de envio:

- **Aviso de Vídeo** — toda **terça-feira**, anuncia o tutorial novo no YouTube e promove o kit correspondente.
- **Campanha** — promoções, datas sazonais, lançamentos e ações do mês.

Cada entrega inclui:

- **3 variações de assunto** para teste A/B/C (cada uma com seu pré-header).
- **1 corpo de e-mail completo** em HTML Stripo.

---

## 2. Assunto — a parte mais importante

O assunto decide se o e-mail é aberto ou ignorado. CTR forte = curiosidade real **ou** benefício imediato.

**Fórmula que performa:** `RESOLUÇÃO DE PROBLEMA + BENEFÍCIO COMERCIAL`

### Entrega obrigatória — sempre 3 variações

| Variação | Personalização | Ângulo |
|----------|----------------|--------|
| **A** | Com `%FIRSTNAME%` | Íntimo — desejo ou dor direta |
| **B** | Sem personalização | Direto e comercial — benefício ou oportunidade |
| **C** | Sem personalização | Gancho de curiosidade, ironia leve ou prova social |

### Regras

- Máximo **55 caracteres** (seguro no mobile, sem corte).
- Cada assunto acompanha um **pré-header** (máx. 90 chars) que **complementa sem repetir**.
- Nunca anunciar só o produto ("Novo vídeo: Brinco X" é fraco).
- **"OFF" só aparece em botão de CTA**, nunca no corpo — padrão: `GARANTIR MEUS X% OFF`.
- Nas campanhas promocionais, **pelo menos 1 dos 3 assuntos** traz preço ou desconto explícito.
- E-mails de conteúdo/receita: assuntos podem focar em curiosidade ou desejo.
- Gatilho de **revenda (revenda)** com tom de clickbait honesto funciona bem.

### Proibido nos assuntos

`não perca` · `incrível` · `imperdível` · `oportunidade única` · `promoção especial`

### Fortes vs. fracos

**Fortes** ✅
- `%FIRSTNAME%, essa peça monta rápido e sai do estoque`
- `Frete travando sua compra? Resolvemos isso`
- `3 passos, visual marcante, margem protegida`
- `Quem disse que peça bonita não pode ser rápida?`

**Fracos** ❌
- `Novo tutorial no YouTube!`
- `Não perca essa oportunidade!`
- `, não deixe passar!`

---

## 3. Voz e tom

- **Segunda pessoa** ("você") — direto, próximo, sem marcar gênero.
- **Nunca terceira pessoa para a marca** ("a Pedra Mística fez", "eles disponibilizaram").
- Tom **direto, comercial, moderno** — fala com quem compra para produzir e vender.
- Ironia ou humor leve quando o contexto pedir — **nunca forçado**.
- O leitor deve pensar: *"isso é pra mim"*, *"preciso saber o que é isso"*, *"isso me ajuda a produzir melhor e vender mais"*.
- Evitar: "bonitinho demais", genérico, tom de comunicado de loja.

---

## 4. Regras de copy específicas (Pedra Mística)

- **Sem abertura de falsa antítese**: `tem peça que X — e tem peça que Y` é banido. Abrir com cena concreta, problema real ou provocação direta.
- **Nunca "tendência 2025"** como frase de copy.
- **Sem jargão interno**: "campanha", "abandono de carrinho", "e-commerce", comparações "apelativas" de mercado ficam de fora.
- **Urgência só quando genuinamente limitada no tempo** — nunca para recurso permanente do site (ex.: 10x sem juros).
- **Títulos lideram com benefício prático**, não frase decorativa (evitar "em grande estilo").
- Não insinuar que o cliente desconhece os benefícios da loja.
- Preço no corpo sempre com **preço cheio + preço promocional + PIX** separados.

---

## 5. Gatilhos

**Permitidos** ✅
- Urgência real (prazo verdadeiro)
- Escassez real (estoque ou condição limitada)
- Antecipação ("se prepare para vender em X data")
- Resolução de objeção (frete, custo, insegurança)
- Vantagem prática (economize, produza mais, venda melhor)
- Planejamento de produção

**Proibidos** ❌
- Urgência falsa
- Promessas mirabolantes
- Exageros emocionais

---

## 6. Estrutura — Tipo A: Aviso de Vídeo (toda terça)

1. **Abertura** — conecta com problema ou desejo. Nunca começar com "Olá". Pergunta, afirmação ou provocação leve.
2. **Apresentação do vídeo** — nome da peça + o que a torna especial + por que vale assistir (facilidade + resultado + potencial de venda).
3. **Benefício comercial** — lista com ✅ (máx. 4 itens):
   - ✅ Facilidade de montagem
   - ✅ Velocidade de produção
   - ✅ Apelo visual / tendência atual
   - ✅ Potencial de giro / margem
4. **Planilha de precificação** — mencionar a planilha gratuita. Variação da frase-âncora: *"peça bonita é importante, mas margem protegida é essencial"*.
5. **CTA duplo** — `→ Assistir ao vídeo: [LINK DO VÍDEO]` · `→ Comprar o kit: [LINK DO KIT]` (CTA criativo paralelo quando o briefing pedir).
6. **Fechamento** — frase curta, encorajadora, voz da marca, sem nome pessoal.

### Layout técnico da série (Aviso de Vídeo)

1. Logo + menu de navegação teal (sem banner de topo — começa direto no menu).
2. Pílula de badge: `▶ Novo Tutorial — Hoje às 18h30`.
3. H1 → linha de destaque teal.
4. Copy + bloco de benefício visual (**layout varia a cada e-mail** para não repetir).
5. Player do YouTube (thumb: `img.youtube.com/vi/{ID}/maxresdefault.jpg`).
6. Seção do kit com **preço ao vivo** vindo da página do produto.
7. Bloco de blog (artigo + placeholder `[IMAGEM DO ARTIGO]`).
8. Ícones sociais → faixa teal do rodapé → rodapé ActiveCampaign.

---

## 7. Estrutura — Tipo B: Campanha do mês

1. **Abertura com gancho** — não anunciar a promoção de cara. Entrar pelo problema ou pela oportunidade (frete trava a decisão; desconto progressivo = comprar com inteligência).
2. **Desenvolvimento — benefício prático** — o que a pessoa ganha de verdade: economiza no pedido, repõe estoque com inteligência, se prepara para datas de venda, inclui itens sem pesar tanto.
3. **Detalhes da campanha** — condição clara (valor mínimo, prazo, região, faixa de desconto) + urgência **real**.
4. **Conexão com mercado** (quando couber) — relacionar a oferta com o que está em alta (ver §8).
5. **CTA objetivo** — ação clara: montar o carrinho / aproveitar agora / garantir antes de acabar → `[LINK DA LOJA ou CAMPANHA]`.
6. **Fechamento** — curto, direto, voz da marca.

---

## 8. Pesquisa de mercado — contexto para campanhas

Antes de criar campanha, conectar a oferta ao que está em alta no mercado de semijoias (torna o e-mail oportuno e relevante):

- Pedras naturais com apelo energético/visual (quartzo, ametista, granada, pirita)
- Maximalismo: argolas, peças marcantes, layering de colares
- Mix de banhos (ouro + prata + grafite) — banho duo
- Zircônias coloridas
- Pérolas modernas em versões descoladas
- Peças florais e texturas diferenciadas
- Personalização e peças únicas
- Mercado em crescimento; venda online ganhando peso

> Ao usar em copy, **traduzir o insight em benefício** — nunca escrever "tendência 2025" literalmente.
> Se o briefing citar data comemorativa/sazonal, pesquisar o comportamento de consumo típico do período antes de criar.

---

## 9. Identidade de marca

- **Primária:** teal `#00a5b2`
- **Secundária:** verde-escuro `#0d2b2b`
- **Fundos:** branco para layouts limpos
- **Regra de ouro:** a identidade é **branco + teal**. **Nunca** usar ouro, vermelho-YouTube ou teal-escuro como cor primária de marca.

### Fontes

| Uso | Fonte |
|-----|-------|
| Corpo | Roboto |
| Headlines editoriais / storytelling | Playfair Display *itálico* |
| Heróis comemorativos | Sacramento (fallback: `cursive, 'Playfair Display', Georgia, serif`) |

---

## 10. Regras de design

- Cada bloco de benefício usa **layout visualmente distinto** do anterior (evita repetição).
- Cards de produto em e-mail de campanha: botão **COMPRAR sem preço exibido** (padrão confirmado pela Nara).
- Consistência de grid mobile/desktop é crítica — alturas de card desiguais e grids inconsistentes são reprovados.
- **Sem banner de topo** — os e-mails começam direto no menu teal.

### Padrões aprovados (ref. campanha Namorados)

- Hero conciso, sem construções "Para os…" (ex.: *"Amores únicos / que duram o ano todo"*).
- Tom conversacional: `%FIRSTNAME%` pode abrir parágrafo; exclamações leves ok.
- Linhas de fechamento em Playfair itálico podem terminar com "!".
- Link do blog "Ler artigo completo →": **20px**.

### Dark mode

- Evitar overrides amplos de cor em blocos teal.
- Usar a classe protetora `.keep-white-bg` em caixas de cupom e em `<span>` de CTA para evitar renderização branco-no-branco.

---

## 11. Arquitetura HTML (Stripo + ActiveCampaign)

Hierarquia **obrigatória** de classes (o editor depende dela para drag & drop, mover, copiar e salvar blocos):

```
esd-stripe
  └── esd-structure
        └── esd-container-frame
              └── esd-block-[tipo]
```

**Classes de bloco:** `esd-block-banner` · `esd-block-text` · `esd-block-image` · `esd-block-button` · `esd-block-spacer` · `esd-block-social` · `esd-block-menu` · `esd-block-html`

> Nunca simplificar a estrutura de tabelas a ponto de perder essas classes.

### Fix de grid mobile

`class="es-table-not-adapt"` na tabela externa + `style="table-layout:fixed"` para grids 2×2 e multicoluna estáveis.

### Timers

- Funcionam como GIF animado via serviço externo (sendtric.com), dentro de `esd-block-html`.
- Gmail e Outlook renderizam só o primeiro frame (estático).
- Apple Mail, iOS e Android reproduzem a animação completa.

### Edição de HTML

Substituições de string via heredoc Python (evita problemas de escape). Arquivos escritos em `/home/claude/` e copiados para `/mnt/user-data/outputs/`.

---

## 12. Estrutura — Newsletter de blog (edição mensal)

- Framework Stripo; teal `#00a5b2`; header com logo; menu teal de 4 itens.
- Grid de cards de artigo 2×2; blocos full-width para conteúdo estratégico.
- Callout de planilha de precificação; CTA de blog.
- Seção YouTube em grid 2×2 (acentos vermelhos `#ff0000`, CTA vermelho).
- Rodapé social teal + banner institucional.
- **Cards:** `border-radius: 6px`, barra de acento de 4px sob a thumb, badge de categoria em maiúsculas, copy focada em benefício, CTA "Ver artigo →".
- Artigos estratégicos recebem tratamento full-width com fundo/botão de cor distinta.
- **Todos os links de artigo** levam UTM: `utm_source=email&sck=newsletter_[mês][ano]`.
- Links "Ler artigo completo →": **20px**.

---

## 13. Ferramentas e recursos

| Recurso | Uso |
|---------|-----|
| **ActiveCampaign + Stripo** | Build e disparo dos e-mails |
| **`web_fetch` na página do produto** | Buscar preço (cheio, à vista, parcelado) e URL da imagem na CDN **antes de cada e-mail** — nunca deduzir pelo slug |
| **Tray CDN** (`images.tcdn.com.br`) | Imagens de kit. Padrão: `img_prod/555469/[slug]_[id]_1_[hash].jpg`. Hash não é inferível → usar placeholder `[IMAGEM SKU — substituir no Stripo]` quando desconhecido |
| **YouTube thumbnails** | `img.youtube.com/vi/{VIDEO_ID}/maxresdefault.jpg` (tutorial) ou `hqdefault.jpg` (newsletter/campanha) — sem autenticação |
| **ActiveCampaign CDN** | Logo e banner de rodapé estáveis em `pedramisticasv.activehosted.com/content/5w6aal/` — reutilizar como está |
| **Blog** (`blogpedramistica.com.br`) | Bloqueia fetch automático (robots.txt). Conteúdo inferido pelo slug; imagens via placeholder `[URL_IMAGEM_SLUG_DESCRIPTOR]` |

**Artigo confirmado em rotação:** "Calendário de Vendas para Semijoia" — `https://blogpedramistica.com.br/calendario-de-vendas-para-semijoia/`

---

## 14. Checklist antes de disparar

1. **Estoque** de todos os produtos do e-mail conferido.
2. **Preços confirmados na página real** — nunca no HTML anterior.
3. Imagens em domínios externos (blogspot etc.) podem quebrar → substituir por CDN própria ou ActiveCampaign.
4. Preços do painel de resumo **batem** com os blocos de produto (erro frequente: preços invertidos entre produtos).
5. Placeholders resolvidos manualmente: `[IMAGEM DO ARTIGO]` (imagem destacada do blog, não auto-buscável) e preços/disponibilidade que o `web_fetch` não retornar.
6. Nunca inventar avaliação, preço, ingrediente ou peso.

---

## 15. Formato da entrega final

```
📧 ASSUNTO A — com %FIRSTNAME% (XX/55 chars) + pré-header
📧 ASSUNTO B — sem personalização (XX/55 chars) + pré-header
📧 ASSUNTO C — gancho/ironia (XX/55 chars) + pré-header

📩 CORPO DO E-MAIL
[e-mail completo em HTML Stripo]
```

Campos manuais marcados com `[LINK DO VÍDEO]`, `[LINK DO KIT]`, `[LINK DA LOJA]`, `[IMAGEM DO ARTIGO]` etc.

---

## 16. Contatos e aprovação

| Pessoa | Papel |
|--------|-------|
| **Túlio** | Direção de conteúdo / produto |
| **Verônica** | Pediu seção de blog em todo e-mail |
| **Lu Nogueira** | Apresentadora dos tutoriais — voz/citações aparecem na copy |

**Fluxo de aprovação:** revisão por screenshots e HTML editado; correções iterativas feitas direto no Stripo antes do envio do feedback.

---

## 17. Histórico de campanhas (referência)

- **Aviso de Vídeo (série contínua)** — anuncia o tutorial da semana + kit correspondente.
- **Frete Fixo (3 e-mails, 07–18/jul):** concluída. Fix principal: substituir bloco de comparação de mercado por layout limpo "Como funciona" após linguagem "apelativa" ser reprovada.
- **15 Anos do Canal (3 e-mails, 19–25/jul, 15% OFF, cupom `KITBRPM-915`):** concluída. Identidade restaurada para branco + teal após versão inicial usar ouro e vermelho-YouTube por engano.
