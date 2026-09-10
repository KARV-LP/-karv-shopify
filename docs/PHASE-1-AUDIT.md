# Auditoria Shopify — Fase 1

Data de conclusão: 2026-09-10  
Loja: **KARV — `loja.k-arv.com`**  
Repositório: `KARV-LP/-karv-shopify`

## Resultado

**Fase 1 concluída.**

O tema publicado foi identificado pela Shopify Admin API, exportado integralmente em modo somente leitura, versionado em uma branch isolada e conferido contra a origem. Nenhuma alteração foi feita no tema publicado.

## Tema de origem

| Campo | Valor |
|---|---|
| Nome | `Cópia de Dawn` |
| Função | `MAIN` — tema publicado |
| Shopify Theme Store ID | `887` — Dawn |
| Atualizado em | `2026-07-07T20:48:56Z` |
| ID Shopify | `gid://shopify/OnlineStoreTheme/147402457158` |

## Snapshot versionado

| Campo | Valor |
|---|---|
| Branch | `audit/shopify-production-2026-09-10` |
| Commit | `36bb90d22356ed61578ed5e79c43417f29083bc7` |
| Arquivos | 367 |
| Tamanho informado pela Shopify | 4.639.974 bytes |
| Arquivos faltantes | 0 |
| Arquivos extras | 0 |

A branch do snapshot representa exclusivamente o código do tema publicado. Ela **não deve ser mesclada diretamente** sobre `main`; serve como referência histórica e base de comparação.

## Estrutura validada

| Diretório | Arquivos |
|---|---:|
| `assets/` | 185 |
| `config/` | 2 |
| `layout/` | 3 |
| `locales/` | 51 |
| `sections/` | 61 |
| `snippets/` | 39 |
| `templates/` | 26 |
| **Total** | **367** |

A estrutura integral exigida para um tema Shopify foi confirmada.

## Temas encontrados na loja

| Nome | Função | Observação |
|---|---|---|
| `Cópia de Dawn` | `MAIN` | Tema publicado e origem do snapshot |
| `shogun-preview-devtheme` | `DEVELOPMENT` | Tema de desenvolvimento do Shogun |
| `Cópia de Cópia de Dawn` | `UNPUBLISHED` | Três cópias não publicadas existentes |
| `-karv-shopify/main` | `UNPUBLISHED` | Tema KARV conectado ao repositório e mantido fora de produção |

## Apps instalados

| App | Desenvolvedor | Papel identificado | Relação com o tema |
|---|---|---|---|
| Messaging | Shopify | Atendimento/chat | Embed ativo do Shopify Inbox em `config/settings_data.json` |
| Shogun Landing Page Builder | Shogun Labs | Páginas editoriais | Dependência direta: layouts, sections, snippets e templates Shogun |
| Mercado Pago Cartões | Mercado Pago | Pagamento | Integração operacional; nenhuma referência explícita encontrada no código do tema |
| Canva Connect | Seguno | Conteúdo/mídia | Administração; nenhuma referência explícita encontrada no código do tema |
| Lalamove E-Commerce Connector | Lalamove | Entrega | Integração operacional; nenhuma referência explícita encontrada no código do tema |
| Frenet | Frenet | Frete | Integração operacional; nenhuma referência explícita encontrada no código do tema |
| KARV — KV_001 Oriental | KARV | Experiência autoral | Template `templates/page.kv001-oriental.liquid` presente |
| Photoroom | Photoroom SAS | Tratamento de mídia | Administração; nenhuma referência explícita encontrada no código do tema |
| KARV — Dragon Heritage | KARV | Experiência autoral | App instalado; nenhuma referência explícita pelo handle encontrada no snapshot |
| SMART Discounts | E-TRADE PARTNER | Descontos | Embed ativo e widget em `templates/product.json` |
| Shopify ChatGPT MCP App | Shopify | Integração administrativa | Usado para esta auditoria; sem dependência de renderização identificada |

## Scripts, pixels e analytics

### Encontrado no código

- `{{ content_for_header }}` permanece nos layouts e deve ser preservado;
- assets JavaScript nativos do Dawn;
- integração Shogun por includes/renders próprios;
- Spline Viewer carregado por `https://unpkg.com/@splinetool/viewer@1.12.97/build/spline-viewer.js`;
- Shopify Inbox e SMART Discounts configurados como app embeds/blocos.

### Não encontrado no código dos 367 arquivos

- Google Tag Manager;
- Google Analytics/`gtag`;
- Meta/Facebook Pixel/`fbq`;
- TikTok Pixel/`ttq`.

### Limitação documentada

A conexão administrativa disponível não possui escopo para enumerar `scriptTags`, Web Pixels ou Server Pixels gerenciados fora do código do tema. Portanto, scripts ou pixels injetados dinamicamente pela Shopify e por apps continuam possíveis através de `content_for_header`.

Esta limitação não impede o versionamento do tema, mas exige nova conferência de Customer Events, pixels e app embeds antes da publicação da Fase 7.

## Elementos globais que não podem ser quebrados

- `layout/theme.liquid`, `layout/password.liquid` e `layout/theme.shogun.landing.liquid`;
- `content_for_header` e `content_for_layout`;
- header, announcement bar, footer e grupos globais;
- templates de produto, coleção, carrinho, busca, páginas, clientes, políticas e gift card;
- cart drawer, variant picker, compra, preço, disponibilidade e pesquisa preditiva;
- includes, layouts e templates Shogun;
- embeds do Shopify Inbox e SMART Discounts;
- integração de produto com Spline via `product.metafields.custom.spline_url`;
- integrações comerciais de pagamento, frete e entrega instaladas na loja.

## Checklist da Fase 1

- [x] Exportar/obter uma cópia do tema Shopify atualmente publicado.
- [x] Versionar o tema em estrutura GitHub apropriada para Shopify.
- [x] Mapear `layout/`, `templates/`, `sections/`, `snippets/`, `assets/`, `config/` e `locales/`.
- [x] Mapear apps, scripts, pixels, analytics e integrações existentes, com a limitação de escopo registrada.
- [x] Identificar elementos globais que não podem ser quebrados.
- [x] Não alterar diretamente o tema publicado.

## Decisão para as próximas fases

- O snapshot de produção permanece imutável na branch `audit/shopify-production-2026-09-10`.
- O desenvolvimento KARV continua no tema não publicado `-karv-shopify/main`.
- Alterações devem entrar por branch e Pull Request.
- Nenhuma publicação ocorrerá sem validação e aprovação explícita da KARV.
