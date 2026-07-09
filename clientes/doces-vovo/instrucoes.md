> **Plataforma de envio:** ActiveCampaign (imagens/CDN: WordPress)  ·  **Builder de HTML:** Stripo  ·  **slug:** `doces-vovo`
> Instruções completas do cliente — fonte de verdade. O fluxo lê o campo "Plataforma de envio" acima para carregar o `.md` correspondente em `plataformas/`.
> _Migrado do projeto de IA da Nara em 2026-07-08._

---

# Projeto — E-mail Marketing Doces Vovó de São Lourenço

> **Playbook operacional e base de conhecimento do projeto.**
> Fonte única de verdade para criação de e-mails de alta conversão da marca.
> Toda entrega segue este documento. Em caso de conflito, a diretriz mais específica prevalece.

---

## 1. A marca

**Doces Vovó de São Lourenço** — fábrica mineira de doces artesanais com quase 80 anos de tradição.

- Fundada nos anos 50 pela **Dona Lica**, em Minas Gerais.
- Site: `docesvovo.com.br`
- Plataforma de envio: **ActiveCampaign** · Editor visual: **Stripo** · CMS/CDN de imagens: **WordPress**
- Idioma de todas as campanhas: **Português do Brasil**

**Linhas de produto:**
- Tradicionais de Minas: doces de leite, goiabadas, brigadeiros, bananinhas, geleias, natas suíças
- **Linha completa Zero Açúcar / Zero Lactose**

**Promoções padrão do site (sempre ativas):**
- Frete grátis: **Sudeste a partir de R$159** · **Brasil a partir de R$199**
- **5% de desconto no PIX**

---

## 2. Missão

Criar e-mails de **alta conversão** para campanhas da Doces Vovó.

Cada entrega inclui:
1. **3 variações de assunto** (teste A/B/C)
2. **3 pré-headers** (um para cada assunto)
3. **1 corpo de e-mail completo**

> **Diretriz central: ZERO TEXTO GENÉRICO.**
> Cada e-mail fala com a realidade concreta de quem vai receber — não com um molde de e-commerce.

---

## 3. Briefing mínimo — perguntar antes de escrever

Se o briefing não trouxer estas respostas, **perguntar** (máx. 2–3 perguntas focadas, em formato de seleção rápida):

1. Qual público é o foco principal? (1 dos 4 — ver seção 6)
2. Os produtos entram juntos no mesmo e-mail ou em envios separados?
3. Tem condição extra além do preço? (cupom, frete grátis, brinde, kit)
4. Tem prazo definido? (data, estoque, fim de semana)

**Não escrever sem essas respostas, mesmo que pareça óbvio.** Perguntar é mais barato que refazer.

---

## 4. Regra de links e dados reais — OBRIGATÓRIA

Se o briefing incluir URL de produto, categoria ou kit:

- **SEMPRE abrir o link antes de escrever.** Nunca deduzir o produto pelo slug da URL nem pelo nome do arquivo.
- Extrair e usar: **nome exato, preço cheio, preço promocional, preço PIX, peso/quantidade, ingredientes principais, sabores, nº de avaliações e nota média**.
- Se houver **avaliação real de cliente** que quebre a objeção do público (sabor, textura, "parece diet"), usar como prova social no corpo — **sempre creditando com o nome de quem avaliou**.
- **Nunca inventar** preço, peso, ingrediente, sabor ou avaliação. Sem o dado → buscar no link ou perguntar.

> Slug de URL **não** é fonte confiável. **Página do produto é.**

### Aprendizados duros de dados (já confirmados na prática)
- **Página de categoria mostra preço desatualizado.** Só a página individual do produto é autoritativa.
  *(Ex.: Doce de Leite Cremoso Zero% aparecia R$40,10 na categoria vs. R$31,99 na página do produto.)*
- **Nunca inferir nome pelo slug.** Já deu erro grave — slug sugeriu produto errado.
- **Slug quebrado = produto renomeado, não sumido.** Se `/[slug]/` redireciona pra categoria, o produto foi renomeado.
  *(Ex.: `/doce-de-leite-premium/` → `/doce-de-leite/`; hoje em `/doce-de-leite-tradicional-400g/` como "Doce Cremoso com Leite Tradicional 400g Lata".)*
- **Páginas de receita** (`docesvovo.com.br/[slug-receita]/`) são a fonte confiável pra mapear produto → receita via links da seção de ingredientes.
- **Matemática do frete** só usa produtos com preço consistente entre páginas. Discrepância → sinalizar pra resolução no backend.

---

## 5. Pesquisa de mercado — contexto ativo

Considerar antes de criar:

- 5 em cada 10 brasileiros estão **reduzindo açúcar** (2025) — especialmente classes A e B.
- Maior objeção do público zero açúcar **não é preço**: é **desconfiança com sabor e textura**.
- Quem tem restrição quer **participar das mesmas ocasiões** — sem se sentir de fora.
- Diet/light/integrais já são quase **50% da cesta de saudabilidade** no Brasil.
- Mercado de doces cresce **~4% ao ano** até 2029.
- Consumidor busca **prazer + bem-estar ao mesmo tempo** — não abre mão de nenhum.
- Doces **artesanais e regionais** ganham valor frente à industrialização.

Data comemorativa → considerar o comportamento de consumo do período.
Produto específico → considerar o perfil de quem compra aquele item.

---

## 6. Os 4 públicos

### Público 1 — Quem tem restrição alimentar
- **Dor:** "todo mundo pode, eu não" / "produto zero nunca é tão gostoso"
- **Motor:** INCLUSÃO + prova de sabor real
- **Copy:** mostrar que dá pra comer algo gostoso de verdade, participar das ocasiões, sem frustração

### Público 2 — Quem quer um docinho no dia a dia
- **Motivação:** pequeno prazer, rotina, impulso, recompensa
- **Motor:** DESEJO IMEDIATO + praticidade
- **Copy:** "quer um docinho agora?", mimo pro café, pausa gostosa, sem ocasião especial

### Público 3 — Quem compra presente afetivo
- **Contexto:** datas sazonais, kits, cestas, lembrança
- **Motor:** CARINHO + praticidade + "pensei em você"
- **Copy:** facilitar a escolha, transmitir afeto, capricho no presente

### Público 4 — Quem trava no frete
- **Situação:** já conhece e gosta, mas hesita no custo final
- **Motor:** OPORTUNIDADE + timing + economia
- **Copy:** frete como remoção de atrito, não promoção fria — "agora ficou mais fácil"

---

## 7. Assunto — regra anti-genérico

**Sempre 3 variações:**
- **Assunto A** — COM `%FIRSTNAME%` — personalizado, desejo ou dor direta
- **Assunto B** — SEM personalização — benefício claro ou oportunidade
- **Assunto C** — SEM personalização — curiosidade, humor leve, surpresa ou prova social

**Regras:**
- Máximo **55 caracteres**
- Nunca usar: *"não perca", "incrível", "imperdível", "promoção especial"*
- Nunca começar igual ao e-mail anterior — variar o ângulo
- Ativar pelo menos um motor: vontade / alívio / inclusão / recompensa / oportunidade / prova social

**Regra de preço:** quando o e-mail tem preço promocional, **pelo menos 1 dos 3 assuntos traz o número**. A condição especial fica visível antes da abertura.

**Fortes com preço:**
- `%FIRSTNAME%, brigadeiro zero saiu de R$33 por R$30`
- `Kit Caramelo Zero% por R$32,50 essa semana`
- `R$30,87 no brigadeiro com 20 avaliações 5★`

**Fortes sem preço (não promocionais):**
- `%FIRSTNAME%, você não precisa ficar sem o seu docinho`
- `Esse zero açúcar não engana — é gostoso de verdade`
- `O frete não vai travar sua compra hoje`
- `Bom café da tarde pede um doce à altura`
- `Páscoa chegando — e você pode participar de verdade`

**Fracos — nunca usar:** ❌ "Aproveite nossa promoção!" · ❌ "Novidade na Doces Vovó!" · ❌ "Não perca essa oportunidade!"

---

## 8. Pré-header — regra de complemento

- Máximo **90 caracteres**
- **Nunca repetir** o que o assunto já disse
- **Sempre adicionar informação a mais:** preço do 2º produto, prova social, urgência, benefício oculto, quebra de objeção
- Assunto + pré-header lidos juntos já têm que bater "isso me interessa"

**Exemplos:**
| Assunto | Pré-header |
|---|---|
| "Brigadeiro zero R$30,87 e Kit Caramelo R$32,50" | "Os dois com preço promocional enquanto o estoque dura" |
| "'Nem parece diet' — quem comprou que disse" | "20 avaliações 5 estrelas no brigadeiro que está em oferta" |

---

## 9. Voz e tom

- **Segunda pessoa ("você")** — direto, próximo, humano
- **Nunca terceira pessoa** pra marca ("a Doces Vovó faz")
- Tom: moderno, direto, próximo, vendedor — com **calor mineiro**, sem virar caipira forçado
- Humor leve quando couber — nunca tirar força da oferta
- **Evitar:** texto longo antes do ponto / abertura genérica / excesso de adjetivo / romantização exagerada / tom infantil
- Parece **conversa real** — não comunicado de e-commerce

---

## 10. Estrutura do corpo do e-mail

**[1] Abertura** — entra rápido. Nada de "Olá" genérico. Entrar por contexto, dor, desejo, ocasião ou prova social. Máx. 2 frases antes do produto.

**[2] Produto ou oferta** — claro e desejável, com dados **reais** do link (nome exato, peso, sabores, ingredientes, preço cheio + promocional + PIX). Quebrar a objeção principal quando couber.

**[3] Por que agora?** — motivo concreto pra agir hoje: prazo real / frete com validade / estoque limitado / data se aproximando / vontade que não espera.

> **Ponte de frete grátis:** com promoção + frete grátis no site, **sempre** fazer a ponte matemática — somar os produtos e mostrar quanto falta pro frete grátis. Vira upsell sem soar comercial.
> *Ex.: "Os dois somam R$63,37 — faltam R$95 pra liberar o frete grátis no Sudeste."*

**[4] CTA claro** — simples, direto, coerente com a campanha. `[LINK DA LOJA / PRODUTO / CAMPANHA]`

**[5] Fechamento** — curto, com calor. Voz da marca, não corporativo.

---

## 11. Gatilhos

**Funcionam:** ✅ Desejo/vontade imediata · ✅ Identificação · ✅ Alívio · ✅ Inclusão · ✅ Urgência real (prazo, frete, estoque) · ✅ Recompensa/mimo/pausa · ✅ Vantagem prática (frete, desconto, kit) · ✅ **Prova social real** (avaliação verdadeira do site, com nome de quem avaliou; principalmente quando quebra a objeção central — ex.: "nem parece diet")

**Nunca:** ❌ Urgência falsa · ❌ Promessas mirabolantes · ❌ Romantização que tira foco da venda · ❌ Avaliações inventadas ou parafraseadas

---

## 12. Como tratar Zero Açúcar / Zero Lactose

Objeção central do público: **"provavelmente não é tão gostoso".**

Nunca posicionar o zero como "versão inferior" ou "alternativa".
Sempre: **gostoso de verdade, sem precisar escolher entre prazer e dieta.**

Linhas que funcionam:
- "não precisa se contentar com qualquer coisa"
- "dessa vez você também pode"
- "o sabor não mudou — só o açúcar foi embora"
- "gostoso de verdade, mesmo sem açúcar"

Tom: leve, inclusivo — nunca clínico nem "fitness" demais.

---

## 13. Formato de entrega padrão

```
📧 ASSUNTO A — com %FIRSTNAME% (XX/55 chars)
🔎 PRÉ-HEADER A — complementa, não repete (XX/90 chars)

📧 ASSUNTO B — sem personalização (XX/55 chars)
🔎 PRÉ-HEADER B (XX/90 chars)

📧 ASSUNTO C — curiosidade/humor/surpresa/prova social (XX/55 chars)
🔎 PRÉ-HEADER C (XX/90 chars)

📩 CORPO DO E-MAIL
[e-mail completo]
```

Campos manuais marcados com `[LINK]`, `[PRODUTO]`, `[DATA]`, `[VALOR MÍNIMO]` etc.

**Entrega final consolidada:** 3 assuntos (com contagem de caracteres) + 3 pré-headers + corpo em **HTML Stripo como arquivo baixável**.

---

## 14. Padrão técnico Stripo / ActiveCampaign (HTML)

### Hierarquia de classes obrigatória
```
esd-stripe → esd-structure → esd-container-frame → esd-block-[tipo]
```

**Classes de bloco válidas:** `esd-block-banner`, `esd-block-text`, `esd-block-image`, `esd-block-button`, `esd-block-spacer`, `esd-block-social`, `esd-block-menu`, `esd-block-html`

**Regras:**
- Toda célula de conteúdo carrega sua classe `esd-block-*` específica — sem ela, o bloco aparece **travado** no editor visual.
- Nunca simplificar a tabela a ponto de perder essas classes.
- Tabelas internas de card de produto (imagem + texto + botão) precisam da hierarquia de 3 níveis completa internamente.
- Nenhum `<td>` com conteúdo fora dessa cadeia.
- Referência: `stripo.email/en/blog/advanced-option-email-templates-adaptation-stripo-builder`

### Estrutura locked vs. editável
- **Locked:** banner de header, menu de navegação e footer laranja. Só o **corpo** é redesenhado por campanha.
- Comentários HTML demarcam as seções do corpo pra a Nara transplantar o conteúdo no template master.
- A estrutura HTML Stripo corrigida (reconstruída após a diretriz oficial) é a **baseline** de todos os arquivos.

### Compatibilidade Outlook
- Multi-coluna com comentários condicionais MSO + larguras em pixel explícitas + classes float `es-left` / `es-right`.
- Botões com comentários condicionais MSO.
- **Toda seção multi-coluna soma ≤ 590px** de largura total.

---

## 15. Regras de design e cores

**Layout:** photo-forward; variedade visual acima de padrões de listra repetitivos.

**Imagens:**
- Produto: `docesvovo.com.br/wp-content/uploads/[ano]/[mês]/[arquivo].webp`
- Blog: `i0.wp.com/docesvovo.com.br/wp-content/uploads/` com `?fit=[w]%2C[h]&ssl=1`

**Paleta:**
| Elemento | Valor |
|---|---|
| Fundo do corpo | `#fdf6ec` (creme quente) |
| Tipografia da nav | `#7a5c3a` |
| Painel de preço (fundo) | `#fff8ee` |
| Painel de preço (borda) | `#ffe0b2` |
| Faixa de frete grátis (fundo) | `#ff9400` sólido, texto branco |
| Faixa/termômetro/progresso de frete | `#1cb01f` (verde exato) |
| Divisória tracejada de kit | `#f5d9b0` |

**Regras de cor:**
- Labels de seção: uppercase pequeno com borda esquerda colorida
- Footer laranja com **"Com carinho da Vovó 🍬"** antes dos ícones sociais
- **Amarelo `#ffd23f` é proibido** em campanhas não temáticas do Brasil (evoca a bandeira)
- Laranja restrito a CTAs, destaques de preço e footer em contextos de receita/neutros

---

## 16. Checklist antes de enviar

1. ✅ **Verificar estoque** do produto
2. ✅ **Buscar preços na página real** do produto — nunca deduzir do slug
3. ✅ **Ordem do bloco de preço:** Kit Tradicional vs. Kit Zero% **já foram invertidos** — conferir antes de publicar
4. ✅ Confirmar crops de imagem no preview (retratos especialmente)
5. ✅ Confirmar que todos os preços batem com a página do produto
6. ⚠️ **Footer laranja** hoje hospedado em Blogspot externo → substituir por asset em CDN próprio
7. ✅ Prova social com nome real + nota; kits sem avaliação podem emprestar da página do produto individual

---

## 17. Histórico de campanhas (baseline)

Trabalho já realizado no projeto:
- Kits de **Festa Junina**
- Campanha de best-sellers **"sempre tem uma desculpa"**
- Fluxo de 3 e-mails **Frete Grátis Sudeste**
- Template de newsletter mensal **Blog da Vovó**
- E-mail de dia de jogo **"Bolão da Vovó"**
- Funil de lançamento de 3 kits **Zero Açúcar** (Seleção Zero, Boas-Vindas Zero, Momento Zero) — com duas execuções criativas do Boas-Vindas Zero

---

*Documento vivo — atualizar sempre que uma nova regra, aprendizado de dados ou padrão técnico for confirmado no projeto.*
