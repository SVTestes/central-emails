# Como usar a Central de E-mails

Guia rápido pra pedir um e-mail pronto, no padrão de cada cliente, sem depender de decorar nada.

---

## O que é isso, em uma frase

Uma pasta no seu computador (ligada ao GitHub da Special Vision) onde ficam guardadas as
instruções de cada cliente e os e-mails já feitos. Você pede um e-mail em português, e o Claude
monta seguindo o padrão certo daquele cliente.

---

## Antes de começar (só na primeira vez)

Duas coisas precisam estar prontas na sua máquina — se ainda não estiverem, fala com o Victor:

1. O **Claude Code** instalado (vem dentro do app do Claude, na aba **Code**).
2. A pasta **central-emails** baixada no seu computador.

Depois que isso estiver pronto, o dia a dia é só o que vem abaixo.

---

## Como pedir um e-mail (passo a passo)

1. Abra o **app do Claude** e clique na aba **Code** (em cima).
2. Escolha/abra a pasta **central-emails** (o rodapé da tela deve mostrar `central-emails`).
3. Na caixa de mensagem, escreva o pedido **em português normal**, dizendo **qual cliente** e **que
   tipo de e-mail**. Exemplos:

   - *"Preciso de um HTML de Vídeo da Semana pra Unique Cafés."*
   - *"Monta um e-mail de campanha de frete grátis pra Doces Vovó."*
   - *"Faz uma newsletter do blog pra Pedra Mística."*

4. Dê Enter e acompanhe. Pronto.

> Dica: quanto mais claro o pedido (cliente + tipo + o gancho da campanha), melhor sai de primeira.
> Se faltar alguma informação importante, o Claude pergunta antes de escrever.

---

## O que o Claude faz sozinho

Você não precisa mandar ele ler nada — ele já sabe o caminho:

1. Descobre de qual **cliente** é o pedido e abre a pasta dele.
2. Lê as **instruções do cliente** (fonte, cores, jeito de escrever).
3. Lê as regras da **plataforma** daquele cliente (ActiveCampaign, Stripo etc.).
4. Olha os **e-mails antigos** do cliente pra manter a mesma cara.
5. Monta o e-mail e **salva** dentro da pasta daquele cliente, em `clientes/<cliente>/emails/`.

---

## O que VOCÊ faz depois (importante)

O Claude **nunca inventa** preço, ficha técnica, nota de avaliação nem link — isso seria arriscado.
Onde ele não tem o dado real, ele deixa um campo entre colchetes, tipo `[PREÇO PROMOCIONAL]`,
`[LINK DO PRODUTO]`, `[REGIÃO]`. Então, antes de enviar:

1. **Troque cada `[ ... ]`** pelos dados reais, pegos na **página do produto** (nunca "de cabeça").
2. **Suba as imagens** na sua plataforma/CDN e troque as URLs de imagem quando indicado.
3. **Cole no Stripo** e faça o envio de teste antes de disparar.

Isso é de propósito: o Claude cuida do texto e da estrutura; você garante que os números estão certos.

---

## Guardar no repositório (pra ficar salvo pra todo mundo)

O e-mail já fica salvo na sua máquina assim que o Claude cria. Pra mandar pro GitHub (e ficar de
referência pros próximos), é só pedir pra ele no fim:

> *"Salva e faz o commit."*

Ele faz o resto.

---

## O pulo do gato: se travar, continue no GPT

Se em algum momento o Claude Code disser que atingiu o limite (estourou o "token"), **você não
perde nada**. É só abrir o **Codex do GPT na mesma pasta central-emails** e continuar o pedido de
onde parou. Os dois leem exatamente os mesmos arquivos, então o GPT já sabe o padrão do cliente
igualzinho. Nunca mais ficar presa quando o limite chega no meio do trabalho.

---

## Deixar o Claude mais esperto com o tempo

Sempre que você descobrir uma regra nova de um cliente, ou algo der errado e você corrigir, **conta
pra ele**. Exemplo:

> *"Anota nas instruções da Doces Vovó que o rodapé de descadastro já vem no template master."*

Ele grava isso no arquivo do cliente (ou da plataforma, se for algo técnico), e da próxima vez já
faz certo sozinho. Assim a base vai ficando cada vez mais afiada — sem você repetir as mesmas coisas.

---

## Deu dúvida?

Fala com o Victor. E se o Claude fizer algo fora do padrão de um cliente, também vale avisar — é
assim que a gente vai ajustando as instruções.
