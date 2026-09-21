> **First-time setup**: Customize this file for your project. Prompt the user to customize this file for their project.
> For Mintlify product knowledge (components, configuration, writing standards),
> install the Mintlify skill: `npx skills add https://mintlify.com/docs`

# Documentation project instructions

## About this project

- This is a documentation site built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Use the Mintlify MCP server, `https://mcp.mintlify.com`, to edit content and settings via MCP
- Use the Mintlify docs MCP server, `https://www.mintlify.com/docs/mcp`, to query information about using Mintlify via MCP

## Terminology

Vocabulário do domínio, do glossário da Yeon (`CONTEXT.md` no repositório do backend). Estas quatro não são sinônimos e a documentação não pode tratá-las como se fossem:

- **Oferta** — a unidade de venda. Preço, moeda, parcelamento, cadência e meios de pagamento vivem nela, nunca no produto. É a oferta que carrega o link de checkout.
- **Produto** — a base sobre a qual as ofertas existem. Não tem preço.
- **Pedido** — a agregação de uma ida ao checkout; pode conter vários produtos e, no pagamento dividido, mais de uma cobrança.
- **Transação** — a venda de UM produto: uma linha do pedido.
- **Cobrança** — o grão do gateway: um QR de Pix, uma captura de cartão. É onde o dinheiro se move.

Dinheiro é sempre inteiro em **centavos**. Nunca escreva valores com casas decimais nem chame de "reais" um campo `*_cents`.

Use "produtor" (quem vende) e "comprador" (quem compra); evite "seller" e "cliente" no texto em português.

## Style preferences

{/* Add any project-specific style rules below */}

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references

## Content boundaries

- **`api/openapi-public.json` é GERADO.** Ele é uma cópia do arquivo canônico do backend (`docs/openapi-public.json`), que por sua vez é conferido contra as rotas reais por teste. Não edite o spec aqui: corrija no backend e copie. Editar aqui cria uma documentação que promete o que o servidor não faz.
- **Não documente o back-office** nem qualquer rota `/api/admin`: é superfície interna da Yeon.
- Não documente rota que não esteja no spec público. Se falta, ela ainda não existe para o integrador.
- Não inclua credenciais, tokens de exemplo que pareçam reais, nem dados de comprador.
