# Importação do tema Shopify — KARV

## Objetivo
Trazer uma cópia do tema atualmente usado em `k-arv.com` para este repositório sem alterar o tema publicado.

## Regra
- Produção permanece intacta.
- O tema importado deve entrar primeiro em branch de trabalho.
- `main` continua sendo a referência estável.
- Nenhuma alteração visual deve ser implementada antes da auditoria da cópia real do tema.

## Branch de trabalho
`feat/karv-homepage-redesign`

## Estrutura esperada do tema
```text
assets/
config/
layout/
locales/
sections/
snippets/
templates/
```

## Processo recomendado
1. Duplicar o tema atualmente publicado dentro da Shopify.
2. Conectar a cópia não publicada ao repositório `KARV-LP/-karv-shopify`.
3. Usar a branch `feat/karv-homepage-redesign` para a sincronização inicial.
4. Confirmar que os diretórios padrão do tema foram recebidos no GitHub.
5. Auditar integrações, apps, scripts, pixels, analytics e customizações existentes.
6. Só depois iniciar o redesign da homepage.

## Validação de entrada
A importação está concluída quando o repositório contém o código real do tema e, no mínimo, os diretórios `layout`, `templates`, `sections`, `snippets`, `assets`, `config` e `locales`.

## Pós-importação
- mapear `theme.liquid`;
- mapear `index.json`/template da homepage;
- identificar sections globais;
- identificar dependências de apps;
- identificar scripts e tracking;
- definir componentes preservados, substituídos e novos;
- preparar primeira proposta do novo `k-arv.com`.
