# Auditoria Shopify — Fase 1

Data da auditoria: 2026-09-10  
Repositório: `KARV-LP/-karv-shopify`  
Branch-base auditada: `main`  
Commit-base: `8e3e4accd8c2399716efb4ba664861a0d8083a2c`

## Objetivo

Verificar se o repositório contém uma cópia completa e auditável do tema Shopify usado em `k-arv.com`, sem alterar o tema publicado.

## Resultado

**Fase 1 ainda não pode ser declarada concluída.**

O repositório contém uma base funcional de homepage criada para a KARV, mas não contém uma cópia integral comprovada do tema publicado. A estrutura atual não atende ao critério de entrada definido em `docs/SHOPIFY-IMPORT.md`.

Nenhuma alteração foi feita na loja ou no tema em produção durante esta auditoria.

## Estrutura encontrada

| Diretório/arquivo | Estado | Observação |
|---|---|---|
| `assets/` | Presente | CSS, JavaScript e placeholders KARV |
| `config/` | Presente | `settings_schema.json` e `settings_data.json` mínimos |
| `layout/` | Presente | Apenas `theme.liquid` |
| `sections/` | Presente | Header, footer e seis seções da homepage KARV |
| `templates/` | Presente | Apenas `index.json` |
| `snippets/` | Ausente | Obrigatório para validar uma importação integral |
| `locales/` | Ausente | Obrigatório para validar uma importação integral |
| Templates de produto, coleção, carrinho, páginas, busca e políticas | Ausentes | Recursos nativos não podem ser validados pelo código atual |

## Branches verificadas

Foram verificadas:

- `main`;
- `feat/karv-homepage-redesign`;
- todas as branches `agent/*` existentes.

Nenhuma delas contém `snippets/` ou `locales/`, e nenhuma apresenta uma estrutura completa do tema publicado.

## Elementos globais identificados

- `layout/theme.liquid`: estrutura HTML global, canonical, `content_for_header`, CSS e JavaScript do tema;
- `sections/header-group.json` e `sections/karv-header.liquid`: header, menu e acesso ao carrinho;
- `sections/footer-group.json` e `sections/karv-footer.liquid`: rodapé e contato;
- `templates/index.json`: composição exclusiva da homepage;
- `assets/karv-base.css`: sistema visual;
- `assets/karv-theme.js`: interação do menu.

Esses elementos devem ser preservados como referência do redesign, mas não substituem a auditoria da cópia real do tema publicado.

## Apps, scripts, pixels e analytics

Na base atual:

- não foram encontrados pixels explícitos;
- não foram encontradas tags explícitas de Google Analytics/GA4;
- não foram encontrados blocos ou embeds explícitos de apps;
- não foram encontrados scripts externos explícitos além dos assets do próprio tema;
- `{{ content_for_header }}` permanece presente e pode receber scripts administrados pela Shopify ou por apps em tempo de execução.

Conclusão: a ausência desses itens no código atual **não comprova** que a loja publicada não os utilize. A confirmação depende da cópia real do tema e da inspeção da configuração da loja/apps.

## Estado dos itens da Fase 1

- [ ] Exportar/obter uma cópia do tema Shopify atualmente publicado.
- [x] Versionar o trabalho existente em repositório Shopify dedicado.
- [ ] Mapear integralmente `layout/`, `templates/`, `sections/`, `snippets/`, `assets/`, `config/` e `locales/`.
- [ ] Mapear apps, scripts, pixels, analytics e integrações da loja publicada.
- [x] Identificar os elementos globais presentes na base atual.
- [x] Preservar produção: nenhuma alteração foi feita no tema publicado nesta auditoria.

## Único caminho para concluir a Fase 1

1. Duplicar o tema atualmente publicado no admin Shopify.
2. Conectar ou exportar essa cópia não publicada.
3. Importar o código real em branch dedicada, sem sobrescrever `main` diretamente.
4. Confirmar os sete diretórios padrão e os templates comerciais.
5. Reexecutar a auditoria de integrações e elementos globais.
6. Atualizar este documento com o commit da importação e marcar a Fase 1 como concluída.

## Regra de segurança

Não criar `snippets/`, `locales/` ou templates fictícios apenas para satisfazer a estrutura. A Fase 1 será concluída somente com a cópia real e auditada do tema Shopify.
