# KARV Shopify

Repositório oficial do tema Shopify da KARV para `k-arv.com`.

## Papel na arquitetura KARV

- **Shopify / k-arv.com**: casa digital principal da KARV; identidade, navegação, catálogo, produtos, carrinho, checkout e operação comercial.
- **Astro / KARV Core**: camada editorial, performance, SEO/GEO, metadata e experiências de aquisição.
- **RYUJIN / MANDALA / futuras edições**: experiências autorais construídas sobre o KARV Core e conectadas à Shopify para conversão.

## Regras

1. Nunca desenvolver diretamente no tema publicado da Shopify.
2. Toda alteração deve nascer em tema duplicado/não publicado e branch dedicada.
3. `main` representa a base estável versionada do tema Shopify.
4. Mudanças entram por Pull Request.
5. Não mover LPs Astro para este repositório.
6. Não duplicar conteúdo editorial do KARV Core na Shopify sem necessidade.
7. Preservar produto, variantes, preço, disponibilidade, carrinho e checkout nativos.
8. Publicação somente após validação e aprovação explícita da KARV.

## Estrutura esperada após importação do tema

```text
assets/
config/
layout/
locales/
sections/
snippets/
templates/
```

## Próxima etapa

Importar uma cópia do tema Shopify atualmente utilizado em `k-arv.com`, manter o tema de produção intacto e iniciar o novo layout KARV em branch dedicada.
