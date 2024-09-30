# Exemplo de como é pra ficar.

<div align="center">
<table>
<tr>

<td>
	<a href="https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fyournextstore%2Fyournextstore&env=ENABLE_EXPERIMENTAL_COREPACK,NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY,STRIPE_SECRET_KEY,STRIPE_CURRENCY&envDescription=Read%20more%20about%20required%20env%20variables%20in%20YNS&envLink=https%3A%2F%2Fgithub.com%2Fyournextstore%2Fyournextstore%2Ftree%2Fupcoming%3Ftab%3Dreadme-ov-file%23add-environmental-variables&project-name=yournextstore&repository-name=yournextstore&demo-title=Your%20Next%20Store&demo-description=A%20Next.js%20boilerplate%20for%20building%20your%20online%20store%20instantly%3A%20simple%2C%20quick%2C%20powerful.&demo-url=https%3A%2F%2Fdemo.yournextstore.com%2F&demo-image=https%3A%2F%2Fyournextstore.com%2Fdemo.png"><img src="https://vercel.com/button" alt="Deploy with Vercel" /></a>
</td>
<td>
<a href="https://www.producthunt.com/posts/your-next-store?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-your&#0045;next&#0045;store">
	<picture>
		<source
			media="(prefers-color-scheme: dark)"
			srcSet="https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=459751&theme=dark"
		/>
		<img
			src="https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=459751&theme=light"
			height="36"
			alt="Your&#0032;Next&#0032;Store - E&#0045;Commerce&#0032;with&#0032;Stripe&#0032;as&#0032;the&#0032;backend | Product Hunt"
		/>
	</picture>
</a>
</td>
</tr>
</table>

</div>

## Demo

https://github.com/user-attachments/assets/64197310-29bd-4dd3-a736-1494340e20e8

## Pré-requisitos
Node.js 20+
Oficialmente, damos suporte à versão LTS atual – 20 no momento da escrita. O YNS deve funcionar nas versões 18, 20 e 22. Se você estiver usando uma dessas versões e encontrar um problema, por favor, nos informe!

## Instalando o Node.js
Siga as instruções para o seu sistema operacional aqui: nodejs.org/en/download

## pnpm 9+
Oficialmente, damos suporte à versão 9 do pnpm, mas faremos o possível para mantê-lo compatível com npm e yarn.

## Instalando o pnpm
A maneira mais fácil de instalar o pnpm é via Corepack do Node.js. Dentro da pasta com o YNS, execute estes comandos:

corepack enable
corepack install

Alternativamente, siga as instruções para o seu sistema operacional aqui: pnpm.io/installation

## Criar conta Stripe
O YNS é totalmente integrado ao Stripe, então você precisa de uma conta Stripe para usar o Your Next Store. Siga as instruções do Stripe para criar uma conta.

É importante lembrar que o Stripe funciona em dois modos diferentes: Modo de Teste e Modo de Produção. Para desenvolvimento e testes locais, você deve usar o Modo de Teste. Assim, o Stripe nunca cobrará dinheiro real, e você poderá usar credenciais de teste especiais, como números de cartão de crédito e números BLIK, para concluir pagamentos. Para mais informações detalhadas, consulte a documentação do Stripe em docs.stripe.com/testing.

Quando estiver pronto para vender seus produtos para clientes reais, você deverá mudar o Modo de Teste para Modo de Produção no Stripe e gerar novas credenciais.

[!DICA] Esta etapa exigirá verificação adicional do Stripe, por isso sugerimos que você inicie o processo imediatamente.

## Adicionar Variáveis de Ambiente
Para o YNS funcionar, você precisará definir algumas variáveis de ambiente. Para desenvolvimento e testes locais, você pode criar um arquivo .env vazio e copiar o conteúdo de .env.example nele.

## Para definir variáveis de ambiente em produção, consulte a documentação do seu provedor de hospedagem escolhido.

## Variáveis de Ambiente Obrigatórias

 - ENABLE_EXPERIMENTAL_COREPACK – Somente no Vercel: Defina como 1 para habilitar o Corepack
 - NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY – Chave publicável do Stripe.
 - STRIPE_SECRET_KEY – Chave secreta do Stripe.
 - STRIPE_CURRENCY – Usado para determinar a moeda da sua loja. Atualmente, apenas uma moeda é permitida, e deve ser um código ISO de três letras (ex: usd).
 - NEXT_PUBLIC_URL – Opcional no Vercel O endereço da sua loja sem a barra final, ex: https://demo.yournextstore.com. Ao construir pela primeira vez, você deve defini-lo para qualquer URL válido, ex: http://localhost:3000.
   
https://github.com/yournextstore/.github/assets/200613/01d27f69-00dc-446e-bc81-5dea2587f346

## Variáveis de Ambiente Opcionais
 - NEXT_PUBLIC_UMAMI_WEBSITE_ID – ID do site Umami para análises
 - NEXT_PUBLIC_NEWSLETTER_ENDPOINT – Prévia: O endpoint para o formulário de newsletter no futuro. Deve aceitar solicitações POST com um JSON { email: string } e retornar JSON { status: number }.
 - STRIPE_WEBHOOK_SECRET – Prévia: Segredo do Webhook do Stripe para lidar com eventos do Stripe. Leia mais abaixo.
 - ENABLE_STRIPE_TAX – Prévia: Defina como qualquer valor (ex: 1) para habilitar o Stripe Tax no YNS. Leia mais abaixo.
 - NEXT_PUBLIC_LANGUAGE – O idioma da loja.

## Executar a loja
Depois de seguir as etapas acima, execute pnpm install para instalar as dependências necessárias e depois execute pnpm dev para iniciar o servidor de desenvolvimento em sua máquina. Your Next Store estará disponível em localhost:3000.

## Adicionar produtos
O Your Next Store obtém todos os produtos, preços, descrições e categorias do Stripe. Então, se você já conhece o Stripe, se sentirá em casa!

Você precisa adicionar produtos ao Painel do Stripe para exibi-los no YNS. Após fazer login, clique em Mais na barra lateral esquerda e selecione Catálogo de produtos. Você também pode usar o link direto:

No Modo de Teste: dashboard.stripe.com/test/products
No Modo de Produção: dashboard.stripe.com/products
Em seguida, clique em Adicionar produto e preencha todas as informações necessárias:

 - nome,
 - descrição,
 - preço – atualmente, apenas pagamentos únicos são suportados,
 - uma imagem do produto.
 - Metadados

Além disso, o Your Next Store usa metadados do produto para fornecer mais informações de contexto sobre os produtos. Você pode especificar os seguintes campos de metadados:

Campo	  Obrigatório	Descrição
slug	  Sim		O slug do produto é usado para URLs. Precisa ser único, exceto para variantes.
category  Não		A categoria do produto usada para agrupar produtos.
order	  Não		A ordem do produto usada para classificar produtos. Números menores aparecem primeiro.
variant	  Não		O slug da variante do produto. Leia abaixo para mais detalhes.

Agora você deve ver todos os produtos adicionados no Your Next Store.


## Variantes
O Your Next Store suporta variantes simples de produtos. Para criar um produto com variantes, você deve adicionar vários produtos ao Stripe com o mesmo campo de metadados slug. O YNS usa o campo de metadados variant para distinguir entre diferentes variantes do mesmo produto. Por exemplo, se você tiver uma camiseta em vários tamanhos, pode criar três produtos com o slug de t-shirt e valores de variant de pequeno, médio e grande.

As variantes são exibidas na página do produto. Variantes podem ter preços, descrições e imagens diferentes. É importante observar que a category deve ser a mesma para todas as variantes do mesmo produto para uma melhor experiência de navegação.

[!NOTA] No futuro, planejamos adicionar a possibilidade de editar produtos e variantes dentro de um painel de administração integrado. Se você tiver alguma ideia ou sugestão, nos avise!

## Webhooks do Stripe
O Your Next Store usa Webhooks do Stripe para lidar com eventos do Stripe. Atualmente, o endpoint é usado para revalidar automaticamente a página do carrinho e para criar transações de impostos (se habilitado). Para configurar os Webhooks, siga a documentação do Stripe. As etapas exatas dependem de você ter ativado o Stripe Workbench em sua conta Stripe: docs.stripe.com/webhooks#add-a-webhook-endpoint.

O endpoint para o webhook é https://{YOUR_DOMAIN}/api/stripe-webhook. O único evento necessário é payment_intent.succeeded. Quando o webhook estiver configurado no Stripe, defina a variável de ambiente STRIPE_WEBHOOK_SECRET para a chave secreta criada pelo Stripe.

[!NOTA] No futuro, planejamos adicionar mais eventos ao webhook para melhorar a experiência do usuário.

## Stripe Tax
O Your Next Store vem com uma prévia do suporte ao Stripe Tax. Para habilitá-lo, defina a variável de ambiente ENABLE_STRIPE_TAX para qualquer valor (ex: 1).

Para que esse recurso funcione, você deve definir suas configurações de impostos no Painel do Stripe: dashboard.stripe.com/register/tax. Quando habilitado e configurado, os impostos serão calculados automaticamente e adicionados ao preço total do produto com base em:

 - preço do produto – o imposto pode ser incluído ou exclusivo
 - código fiscal do produto
 - endereço do cliente
 - ID fiscal do cliente
   
[!AVISO] Esse recurso ainda está em estágio inicial, e pode haver casos especiais que não são suportados. Estamos trabalhando ativamente nisso, então, se você encontrar algum problema ou tiver sugestões, nos avise!
