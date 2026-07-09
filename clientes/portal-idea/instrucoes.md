> **Plataforma de envio:** ActiveCampaign  ·  **Builder de HTML:** Stripo  ·  **slug:** `portal-idea`
> Instruções completas do cliente — fonte de verdade. O fluxo lê o campo "Plataforma de envio" acima para carregar o `.md` correspondente em `plataformas/`.
> _Migrado do projeto de IA da Nara em 2026-07-08._

---

# Instruções do Projeto — E-mails Portal IDEA

> Documento-mãe para criação de campanhas de e-mail marketing. Referência de marca, tom de voz, estrutura técnica (Stripo/ActiveCampaign) e checklist de entrega.

---

## 1. Contexto do cliente

**Portal IDEA** — Instituto de Desenvolvimento e Aprendizagem LTDA

- Plataforma EAD com mais de 5.000 cursos online gratuitos.
- Modelo de negócio: cursos 100% grátis, paga só quem decidir emitir o certificado oficial.
- Reconhecimento: Selo Ouro ABL (3 anos consecutivos), Selo Águia Master 2022/2023/2024.
- Certificados amparados pela Lei 9.394/1996.

### Dados institucionais

- **CNPJ:** 30.363.776/0001-37
- **Endereço:** Av. Dom Pedro II, 1095 — Centro, São Lourenço — MG — 37470-000
- **Site:** https://portalidea.com.br/
- **WhatsApp atendimento:** http://portalidea.com.br/certificado-whatsapp
- **Redes:** facebook.com/PortalIDEAonline e instagram.com/portal.idea

### Números públicos (uso livre em copy)

- +5 milhões de alunos matriculados
- +5.000 cursos gratuitos
- +2 milhões de certificados emitidos
- Cargas horárias de 2 a 180 horas
- Aplicativos disponíveis no Google Play e App Store

### Ferramenta de envio

**ActiveCampaign (AC)**, com editor visual **Stripo**. Tags de personalização do AC:

| Tag | Função |
|-----|--------|
| `%FIRSTNAME%` | Primeiro nome do contato |
| `%EMAIL%` | E-mail do contato |
| `%UNSUBSCRIBELINK%` | Link de descadastro (obrigatório) |
| `%SENDER-INFO-SINGLELINE%` | Bloco de informações da empresa (obrigatório) |

---

## 2. Tom de voz — regras absolutas

### 2.1. Primeira pessoa SEMPRE

A marca fala em primeira pessoa do plural: **"a gente"** ou **"nós"**. NUNCA em terceira pessoa ("o Portal IDEA faz", "a empresa oferece").

**Correto:**
- "A gente tem mais de 5.000 cursos"
- "Aqui com a gente você estuda de graça"
- "Os nossos certificados são amparados pela Lei"
- "A gente já entregou pra 2 milhões de profissionais"

**Errado:**
- "O Portal IDEA tem mais de 5.000 cursos"
- "No Portal IDEA você estuda de graça"
- "Os certificados do Portal IDEA são amparados pela Lei"
- "A empresa já atendeu 2 milhões de profissionais"

O nome "Portal IDEA" pode aparecer apenas em:

- Headlines/títulos que reforçam identidade ("Aqui no Portal IDEA…")
- Footer e assinatura
- Apresentação inicial em e-mails pra leads frios (primeira menção)
- Citação em terceira pessoa de fontes externas ("o Portal IDEA recebeu o Selo Ouro")

Como **sujeito de ações, serviços ou promessas**, sempre "a gente"/"nós".

### 2.2. Caloroso, humano, direto

- Sem ser piegas.
- Direto ao ponto, especialmente nas aberturas.
- Empático com a jornada do aluno (reconhece esforço, dificuldades, dúvidas).
- Usa "você" e "a gente" (próximo, conversacional).
- Evita jargão corporativo.
- Frases curtas e médias, com quebras frequentes pra dar respiro.

### 2.3. Estrutura narrativa recomendada

A ordem pode mudar conforme briefing, mas estes elementos costumam aparecer:

1. **Label superior** (uppercase, letter-spacing largo, cor de destaque) — contextualiza.
2. **Headline** com personalização `%FIRSTNAME%` quando fizer sentido.
3. **Parágrafo de abertura empático** — valida onde o aluno está.
4. **Oferta ou conteúdo central** (em card destacado ou bloco roxo).
5. **CTA primário visível.**
6. **Quebra de objeções** (em cards com borda lateral roxa).
7. **Fechamento emocional** com CTA final.
8. **WhatsApp** como saída para quem ainda tem dúvida.

---

## 3. Identidade visual

### 3.1. Paleta de cores oficial

| Cor | Hex | Uso |
|-----|-----|-----|
| Roxo principal | `#5330af` | CTAs, headlines de destaque, fundos de seção |
| Roxo escuro hover | `#3d2185` | Estado hover de botões |
| Navy (azul-marinho) | `#1c1c62` | Títulos, footer, texto sobre fundos claros |
| Amarelo destaque | `#ffcc00` | Menu, labels de oferta, CTAs sobre fundo roxo |
| Verde WhatsApp | `#2ba75b` | Sempre que tiver botão pro WhatsApp |
| Fundo claro | `#f8f9f8` | Background neutro entre seções |
| Texto corpo | `#444444` / `#333333` | Parágrafos / listas |
| Texto secundário | `#888888` / `#aaaaaa` | Textos de apoio |
| Borda card | `#efefef` / `#f0f0f0` | Bordas suaves |

### 3.2. Tipografia

- **Body:** `roboto, 'helvetica neue', helvetica, arial, sans-serif`
- **Headlines:** `arial, 'helvetica neue', helvetica, sans-serif` (Arial bold para H1/H2)

| Elemento | Desktop | Mobile |
|----------|---------|--------|
| H1 | 32px | 26px |
| H2 | 24–28px | 22px |
| H3 | 20px | 18px |
| Body | 17px | 16px |
| Labels uppercase | 13px (letter-spacing 2–3px) | — |
| Footer | 13px | — |

### 3.3. Logo header

Sempre usar a imagem oficial:

```
https://content.app-us1.com/zY6qx/2022/12/19/84c21555-fc9d-4232-a914-7acda99033bd.jpeg?id=17955269
```

Largura 648px, dentro de borda 2px sólida `#333333` com fundo `#efefef`.

### 3.4. Menu de navegação (padrão fixo amarelo abaixo do logo)

4 colunas iguais com divisórias brancas, fundo `#ffcc00`, links em `#333333`:

| Link | URL |
|------|-----|
| Home | `https://portalidea.com.br/` |
| Cursos | `https://portalidea.com.br/listacursos` |
| Certificado | `https://portalidea.com.br/nosso-certificado` |
| Quem Somos | `https://portalidea.com.br/saiba-mais` (em alguns templates é "Contato") |

### 3.5. Footer obrigatório

Fundo `#1c1c62` com texto branco/cinza claro, contendo:

- Nome "Portal IDEA" em destaque.
- Dados completos do CNPJ e endereço.
- Ícones sociais (Facebook + Instagram):
  - `https://stripo.cluster.app-us1.com/static/assets/img/social-icons/circle-white/facebook-circle-white.png`
  - `https://stripo.cluster.app-us1.com/static/assets/img/social-icons/circle-white/instagram-circle-white.png`
- Bloco de unsubscribe com `%EMAIL%`, `%UNSUBSCRIBELINK%` e `%SENDER-INFO-SINGLELINE%`.

> ⚠️ **Atenção:** garantir que `bgcolor` e `style="background-color"` no footer estejam consistentes em `#1c1c62`. Templates antigos tinham bug de mostrar azul claro em alguns clientes.

---

## 4. Estrutura técnica (padrão Stripo/AC)

Todo HTML segue a hierarquia obrigatória do Stripo para permitir edição drag-and-drop no AC:

```
esd-email-paddings (td principal do wrapper)
└── esd-stripe (faixa horizontal/seção)
    └── esd-structure (linha de conteúdo)
        └── esd-container-frame (célula de coluna)
            └── Bloco específico:
                - esd-block-text (textos, parágrafos, headlines)
                - esd-block-image (logo, fotos)
                - esd-block-button (CTAs)
                - esd-block-menu (navegação)
                - esd-block-social (redes sociais no footer)
                - esd-block-spacer (divisores horizontais)
                - esd-block-html (layouts customizados)
```

Referência: https://stripo.email/pt/blog/advanced-option-email-templates-adaptation-stripo-builder/

### 4.1. ⚠️ Regra crítica: `esd-block-html`

**SEMPRE** envolver layouts customizados em `<td class="esd-block-html">` — sem isso, o Stripo trata como decoração estática e não é possível editar no modo visual do AC.

Casos obrigatórios de `esd-block-html`:

- Cards com background colorido + texto + valor (cards de preço).
- Cards com borda lateral (objeções).
- Caixas com ícone + título + descrição (categorias, passos, benefícios).
- Métricas com número grande e descrição.
- Qualquer "tabela visual" customizada que não cabe em text/button/image puros.

Texto puro, botão e imagem usam `esd-block-text`, `esd-block-button` e `esd-block-image` respectivamente — sem `esd-block-html`.

> **Nota de histórico:** em algumas conversas anteriores usou-se a diretriz oposta (nunca usar `esd-block-html`, resolver tudo via `bgcolor`/`style` no `esd-container-frame`). Este documento consolida a versão vigente do briefing atual. Confirmar com a Nara qual abordagem vale antes de iniciar a campanha, pois o comportamento do editor visual do AC pode variar entre contas/templates.

### 4.2. Classes de padding utilitárias

Sempre que possível, usar as classes do Stripo no lugar de styles inline:

`es-p5t`, `es-p10t`, `es-p15t`, `es-p20t`, `es-p30t`, `es-p40t` (e b/r/l correspondentes).

### 4.3. Largura padrão

- Container principal: **650px** (sempre máx 650, responsivo abaixo de 600px).
- Imagens: `class="adapt-img"` para responsividade.

### 4.4. Responsividade mobile

Todos os media queries `@media only screen and (max-width: 600px)` devem estar no `<style>` do head, com:

- Textos: 16–18px no mobile.
- H1: 26px no mobile.
- Tabelas: `width: 100% !important`.
- Imagens: `width: 100% !important; height: auto !important`.
- Cards lado a lado: `display: block !important; width: 100% !important;` (pra empilhar).

### 4.5. Compatibilidade Outlook (crítico)

Botões devem ter fallback VML para Outlook:

```html
<!--[if mso]>
<v:roundrect xmlns:v="urn:schemas-microsoft-com:vml" ...>
  ...
</v:roundrect>
<![endif]-->
<!--[if !mso]><!-- -->
<span class="es-button-border">
  <a class="es-button" ...>...</a>
</span>
<!--<![endif]-->
```

Degradação graceful aceitável no Outlook desktop:

- Border-radius (cantos retos em vez de arredondados).
- Borda lateral em cards (pode não renderizar).
- Border-radius 50% (círculos viram quadrados).

Conteúdo continua legível em todos os casos.

### 4.6. Pré-header invisível (boa prática)

Adicionar logo após o `<body>` um div oculto com texto de preview:

```html
<div style="display:none; font-size:1px; color:#f8f9f8; line-height:1px; max-height:0; max-width:0; opacity:0; overflow:hidden;">
  [Texto do pré-header aqui]
  &zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;[repetir várias vezes para empurrar o conteúdo do body pra fora do preview]
</div>
```

O campo "Preview text" do AC também precisa ser preenchido — alguns clientes mobile usam aquele em vez do invisível.

---

## 5. URLs principais do site (usar nos CTAs conforme objetivo)

| URL | Quando usar |
|-----|-------------|
| `https://portalidea.com.br/matricula` | Cadastro gratuito (CTA pra leads frios) |
| `https://portalidea.com.br/matricula-promocional` | Compra de certificados (CTA pra ofertas mensais) |
| `https://portalidea.com.br/listacursos` | Catálogo geral de cursos |
| `https://portalidea.com.br/nosso-certificado` | Página explicativa sobre o certificado |
| `https://portalidea.com.br/saiba-mais` | Sobre o Portal IDEA |
| `https://portalidea.com.br/acessar` | Login do aluno |
| `https://portalidea.com.br/categoria-{slug}-1` | Categoria específica (ex: `categoria-saude-1`) |
| `http://portalidea.com.br/certificado-whatsapp` | WhatsApp do atendimento |

### Categorias mais usadas

| Categoria | Slug |
|-----------|------|
| Saúde | `categoria-saude-1` |
| Educação | `categoria-educacao-1` |
| Administração | `categoria-administracao-1` |
| Tecnologia | `categoria-tecnologia-1` |
| Construção Civil | `categoria-construcao-civil-1` |
| Culinária | `categoria-culinaria-1` |
| Marketing | `categoria-marketing-1` |
| Estética e Beleza | `categoria-estetica-e-beleza-1` |

---

## 6. CTAs — padrões

### 6.1. CTA primário (ação principal)

- Sobre fundo claro → **roxo `#5330af`** com texto branco.
- Sobre fundo roxo → **amarelo `#ffcc00`** com texto navy `#1c1c62`.
- Border-radius: `9px`.
- Padding: `14px 30px`.
- Font-size: `20px` desktop / `17px` mobile.
- Font-weight: bold.
- Sempre acompanhado de emoji relevante (🎓, 🚀, ✨) — um por botão, antes do texto.

### 6.2. CTA secundário/outline

- Background transparente, borda `2px solid #5330af`, texto roxo.
- Mesmas dimensões do primário.
- Usado pra ações alternativas ("ver todos os cursos", "saber mais").

### 6.3. CTA WhatsApp (suporte)

- Verde `#2ba75b` com texto branco.
- Font-size: 17px.
- Sempre como último recurso de conversão antes do footer.

### 6.4. Regra de ouro de contraste

**Nunca usar botão na mesma cor do fundo da seção.** Se o fundo é roxo, o botão é amarelo. Se o fundo é claro, o botão é roxo.

---

## 7. Assuntos e pré-headers

### 7.1. Estrutura ideal do assunto

- Começar com **emoji** que reflete o tom (🔓 oferta / 🎯 personalização / 💥 escassez / 🎓 conquista / ⏰ urgência / 📚 descoberta).
- 40–60 caracteres no total.
- Personalização com `%FIRSTNAME%` quando aumentar relevância.
- Evitar caps lock total (cai no spam).
- Não usar mais de 1 emoji.

### 7.2. Preheader (texto de preview)

- 40–90 caracteres.
- Complementa o assunto SEM repetir.
- Cria curiosity gap ou contextualiza.
- Reforça o benefício principal ou cria urgência.

### 7.3. Sempre entregar 3 opções com lógicas diferentes pra teste A/B

- **Opção A:** personalização + benefício direto (relevância).
- **Opção B:** curiosity gap ou quebra de objeção (curiosidade).
- **Opção C:** identidade aspiracional ou conquista (ego/emoção).

### 7.4. Exemplos validados

| Assunto | Preheader |
|---------|-----------|
| `🔓 A maior oferta da história, desbloqueada pra você` | `Você concluiu o curso. Falta só um passo — e ele nunca foi tão acessível.` |
| `🎯 %FIRSTNAME%, você parou bem na linha de chegada` | `Seu certificado está pronto. Liberamos uma condição especial pra você finalizar.` |
| `🔓 É grátis mesmo? Onde tá o pega?` | `A pergunta que 5 milhões de alunos fizeram antes de criar a conta com a gente.` |

---

## 8. Quebra de objeções (padrão visual)

Quando o e-mail precisa quebrar dúvidas, usar cards brancos com **borda lateral esquerda roxa de 4px**:

- Background: `#ffffff`
- Border-left: `4px solid #5330af`
- Border-radius: `8px`
- Padding: `20px 22px`
- Pergunta em bold navy (`#1c1c62`, 16px)
- Resposta em cinza (`#555555`, 15px, line-height 165%)
- **Envolver cada card em `<td class="esd-block-html">`** pra ficar editável.

Sempre tratar as objeções como perguntas reais do aluno, escritas entre aspas.

### Objeções variam por audiência

- **Lead frio:** dúvidas sobre o modelo ("é grátis mesmo?", "tem cartão?", "vou ter que pagar algo escondido?").
- **Aluno ativo/concluinte:** dúvidas sobre processo ("certificado vale em concurso?", "demora pra emitir?", "qual a diferença físico/virtual?").
- **Aluno que já comprou:** dúvidas sobre próximo passo ("posso usar pra promoção?", "como combinar com outros?").

Ajustar conforme briefing.

---

## 9. Imagens

### 9.1. Hospedagem

- Imagens próprias do Portal IDEA: `content.app-us1.com` (CDN do ActiveCampaign).
- Imagens antigas em uso: `1.bp.blogspot.com` (manter quando o template original já usa).
- Ícones sociais: `stripo.cluster.app-us1.com`.
- **Não usar Unsplash, Pexels ou bancos externos** sem aprovação.

### 9.2. Arte mensal do Rodrigo

Cada mês, o Rodrigo prepara a arte da oferta. A Nara faz upload na biblioteca do AC e passa o URL pra colocar no HTML.

Padrão de fluxo:

1. Nara envia briefing + arte do Rodrigo (jpg/png).
2. Deixo placeholder no HTML (`URL_ARTE_RODRIGO_AQUI`).
3. Nara sobe a arte no AC, copia URL gerada.
4. Substitui o placeholder antes de enviar.

### 9.3. Diretrizes técnicas

- Largura máxima: 650px.
- Sempre `class="adapt-img"` e `style="display:block;"`.
- Sempre com `alt` descritivo (acessibilidade + spam score).
- Imagens clicáveis envoltas em `<a>` quando levarem a uma página.

### 9.4. Imagem do certificado/depoimento (Gabriel Martins)

URL atual em uso:

```
https://1.bp.blogspot.com/-sVcXA51n0w4/YPWULUDLvhI/AAAAAAAAr34/rhj94rMs4rQZhMZLumNO8t9aVIAN7K4kACNcBGAsYHQ/s1708/01--Corpo.jpg
```

---

## 10. Briefing (o que a Nara passa antes de começar)

Pra entregar o e-mail acertando de primeira, é preciso ter clareza sobre:

```
AUDIÊNCIA:          [lead frio / aluno ativo / aluno concluinte / mista]
PERÍODO:            [mês ou data da campanha]
OBJETIVO PRINCIPAL: [matrícula / certificação / reativação / engajamento]
OFERTA / GANCHO:    [descrever a oferta do mês ou tema]
ARTE DO RODRIGO:    [URL hospedada no AC, ou "ainda vou subir"]
TOM ESPECÍFICO:     [empático / urgência / descoberta / conquista — ou misto]
OBSERVAÇÕES:        [qualquer coisa específica do mês]
```

Quanto mais campos preenchidos, mais certeira a primeira versão. Se algum campo vier vago, perguntar antes de criar.

---

## 11. Checklist final antes de entregar

### Estrutura visual e marca

- [ ] Logo do Portal IDEA no topo com borda 2px e fundo `#efefef`
- [ ] Menu amarelo com 4 links funcionais
- [ ] Footer com dados completos da empresa e cor consistente `#1c1c62`
- [ ] Bloco de unsubscribe presente com tags do AC
- [ ] Todas as cores seguem a paleta oficial
- [ ] CTAs com contraste forte (amarelo sobre roxo / roxo sobre claro)

### Tom de voz

- [ ] Marca em primeira pessoa em todo o e-mail ("a gente"/"nós")
- [ ] Nenhuma frase com "o Portal IDEA" como sujeito de ação/promessa
- [ ] Headlines com `%FIRSTNAME%` quando fizer sentido
- [ ] Quebra de objeções relevantes pra audiência específica

### Estrutura técnica AC/Stripo

- [ ] Estrutura Stripo aplicada (`esd-stripe`, `esd-structure`, `esd-container-frame`, blocos)
- [ ] Todo conteúdo customizado envolvido em `<td class="esd-block-html">` (cards de preço, objeção, áreas, passos, métricas, qualquer caixa visual)
- [ ] Fallback VML para botões (compatibilidade Outlook)
- [ ] Media query `@media (max-width: 600px)` no head
- [ ] Imagens com `adapt-img` e alt descritivo
- [ ] Tags do ActiveCampaign (`%FIRSTNAME%`, `%EMAIL%`, `%UNSUBSCRIBELINK%`, `%SENDER-INFO-SINGLELINE%`)
- [ ] Pré-header invisível no início do `<body>`
- [ ] Arquivo abaixo de 102 KB (pra não ser truncado pelo Gmail)

### Entregáveis adicionais

- [ ] Pelo menos 3 sugestões de assunto com lógicas distintas + preheader complementar
- [ ] Lembrete pra preencher campo "Preview text" no AC
- [ ] Lembrete sobre substituir placeholders (URL da arte do Rodrigo, etc)

---

## 12. Quando pedir ajuda à equipe

Para tarefas que vão além de criar o HTML, recomendar:

| Demanda | Quem chamar |
|---------|-------------|
| Edição de imagens (sorrisos, retoques, ajustes visuais) | Rodrigo / Nycollas / Thiago Maciel |
| Integração técnica, APIs, automações no AC, upload de imagens, ajustes em código | Lucas / Carlos / Dblack |
| Estruturação de dashboards de performance dos e-mails (CTR, abertura, conversão) | Carlos |
| Revisão de tom de voz ou estratégia SEO/conteúdo | Nara |
| E-mail que dialoga com ações físicas, experiência ou influenciadores | Fer |

---

*Documento de referência interna — Portal IDEA / Email Marketing.*
