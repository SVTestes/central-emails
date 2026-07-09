> **Plataforma de envio:** ActiveCampaign (primária) + FluentCRM (secundária)  ·  **Builder de HTML:** Stripo  ·  **slug:** `hotel-fazenda-ramon`
> Instruções completas do cliente — fonte de verdade. O fluxo lê o campo "Plataforma de envio" acima para carregar o `.md` correspondente em `plataformas/`.
> _Migrado do projeto de IA da Nara em 2026-07-08._

---

# Projeto — Hotel Fazenda Ramon

**Cliente:** Hotel Fazenda Ramon — São Lourenço, Minas Gerais
**Agência:** Special Vision
**Escopo:** Produção completa de campanhas de e-mail marketing
**Última atualização:** Julho de 2026

---

## 1. Contexto

O Hotel Fazenda Ramon é um hotel-fazenda histórico localizado em São Lourenço (MG), que se descreve como o **primeiro Hotel Fazenda do Brasil**, com mais de um século de tradição. A comunicação deve carregar esse peso histórico e o caráter acolhedor de hospitalidade, sem soar corporativa ou fria.

O trabalho abrange a produção integral das campanhas: templates HTML de e-mail, copywriting, linhas de assunto (subject lines), pré-header e configuração de compliance.

### Divisão de responsabilidades

| Etapa | Responsável |
|---|---|
| Direção de conteúdo e correções editoriais | Special Vision |
| Design, narrativa e código | Assistente (IA) |
| Substituição manual das imagens | Special Vision (após a entrega) |

> Este é o mesmo esquema de trabalho aplicado a outras contas (Doces Vovó e Pedra Mística).

---

## 2. Identidade de Marca

### Paleta e tipografia

| Elemento | Especificação |
|---|---|
| Cor primária | Verde `#009a3d` |
| Cor de destaque | Amarelo/dourado `#f4b800` |
| Fundo | Branco |
| Fonte principal | Roboto |
| Fonte decorativa (post-it) | Caveat (manuscrita) |
| Largura do e-mail | 590px |

### Estrutura visual base

- **Navegação verde** no topo: Casa · Espaço · Contato
- **CTAs** direcionando para WhatsApp
- **Rodapé verde** com ícones sociais: Facebook, Instagram, TikTok e localização

### Contatos WhatsApp

- (35) 2143-0282
- (35) 3332-3422

---

## 3. Diretrizes Editoriais e de Tom

### Princípios de copy

- **Conversacional e em primeira pessoa** — "leve de ler", parecido com uma conversa.
- Evitar linguagem genérica ou excessivamente formal.
- Transformar informação em conexão, mantendo o equilíbrio entre acolhimento e objetivo comercial.

### Tom de escassez / urgência

- Deve ser **elegante e orientado à exclusividade** — nunca no estilo varejo agressivo.
- A escassez é usada como **gatilho estratégico**, não como afirmação factual.

### Calibragem contextual do tom

- O tom precisa ser ajustado ao contexto da data comemorativa.
- Exemplo real: a expressão *"e muito amor"* foi sinalizada como **tonalmente inadequada para o Mês dos Pais** (romântica demais para um contexto de Dia dos Pais).

### Design

- Escolhas genéricas ou previsíveis (ex.: grids padrão de cards 2x2) são **ativamente rejeitadas** em favor de tratamentos visuais mais distintivos.

---

## 4. Especificações Técnicas

### 4.1. ActiveCampaign (plataforma primária) + Stripo (builder)

**Hierarquia de classes Stripo** — deve ser aplicada em todos os níveis de aninhamento:

```
esd-stripe → esd-structure → esd-container-frame → esd-block-*
```

**Links em imagens:**

- Toda tag `<a>` de imagem **precisa incluir o atributo `href`**.
- A omissão dispara o aviso de link inválido "Empty Text/Image" no validador do ActiveCampaign.
- **Correção padrão:** apontar todos os links de imagem para a URL de contato do WhatsApp.

### 4.2. FluentCRM (plataforma secundária)

**Personalização:**

```
{{contact.first_name|Visitante}}
```

**URLs de compliance:**

```
##crm.unsubscribe_url##
##crm.manage_subscription_url##
##web_preview_url##
```

**Campos dinâmicos de rodapé:**

```
{{crm.business_name}}
{{crm.business_address}}
```

> Estes campos exigem que as **Business Settings do FluentCRM estejam preenchidas** para renderizar corretamente.

---

## 5. Estrutura das Campanhas

Cada e-mail segue uma **estrutura de 11 imagens**, extraída dos posts em carrossel do Instagram correspondentes (os carrosséis do Instagram são a fonte de referência dessa estrutura).

---

## 6. Histórico de Campanhas

### Junho

Duas versões:

- **Padrão** (programação normal)
- **Variante de escassez** ("últimas vagas")

Ganchos temáticos: Corpus Christi, Dia dos Namorados, Festa Junina e Copa do Mundo.

### Julho

Campanha **reconstruída após correção de erro de mês**, com quatro destaques temáticos em formato post-it:

- Férias Escolares
- Festa Julina
- Copa do Mundo
- Inverno na Serra

**Inovação de design:** post-it com fonte manuscrita Caveat, bandeirinhas decorativas (amarelo/verde/vermelho) e fundos verde-escuro — uma quebra do template base que pode se manter nas próximas campanhas.

### Agosto

Campanha construída em torno do **Mês dos Pais** e da reta final da temporada de Festa Caipira.

- Nova seção recorrente: **Feirinha do Ramon**, com **Festival de Pastel às sextas-feiras**.

---

## 7. Fluxo de Trabalho e Boas Práticas

### Correções iterativas

Special Vision sinaliza problemas (tonais, estruturais ou técnicos) e a IA oferece correções direcionadas — **sem reescritas desnecessárias**.

### Checagem de datas — atenção crítica

Já ocorreram erros de mês/data que exigiram **find-and-replace sistemático** em todos os elementos da campanha. Uma **verificação cuidadosa de referências de data é obrigatória antes de cada entrega**.

### Comunicação com leads

Orientações ao cliente (ex.: alertas de phishing para leads) são enquadradas no **tom de hospitalidade do hotel** — cuidado atencioso, não alerta de segurança.

---

## 8. Checklist de Pré-Entrega

- [ ] Todas as referências de mês/data conferidas e corretas
- [ ] Hierarquia Stripo completa aplicada em todos os níveis
- [ ] Todas as tags `<a>` de imagem com `href` (WhatsApp)
- [ ] Shortcodes de compliance presentes (unsubscribe, manage, preview)
- [ ] Business Settings do FluentCRM preenchidas (se aplicável)
- [ ] Tom calibrado ao contexto da data comemorativa
- [ ] Estrutura de 11 imagens alinhada ao carrossel do Instagram
- [ ] Design distintivo (sem grids genéricos)
- [ ] Escassez tratada com elegância/exclusividade

---

## 9. Ferramentas e Recursos

| Categoria | Ferramenta |
|---|---|
| Plataforma de e-mail (primária) | ActiveCampaign |
| Plataforma de e-mail (secundária) | FluentCRM |
| Builder de HTML | Stripo |
| Fonte de referência de conteúdo | Carrosséis do Instagram |
