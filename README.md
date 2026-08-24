# Carreira em Dólar — página de vendas

Site estático de uma página. Sem build, sem dependências: o `index.html` é
autossuficiente (CSS inline, fontes do Google Fonts).

## Deploy

Vercel, projeto **carreira-em-dolar**. Todo push na `main` publica em produção.

## Estrutura

| Arquivo | O quê |
|---|---|
| `index.html` | A página inteira |
| `og-image.png` | Preview do link (1200×630) — é o que aparece na DM do ManyChat |
| `favicon.svg` | Ícone da aba |
| `vercel.json` | Clean URLs, headers de segurança, cache de assets |

## ⚠️ Antes de publicar em produção

1. **Domínio.** O `<head>` aponta para `https://carreiraemdolar.com.br/` em
   `canonical`, `og:url` e `og:image`. Trocar pelo domínio real assim que
   registrar — OG image quebra com URL relativa, precisa ser absoluta.
2. **Placeholders de imagem.** Os blocos `.ph` são espaços reservados. Para
   trocar, apague a `<div class="ph">` e ponha `<img src="..." alt="..."
   class="ph-img">`. São três: dois prints do GlobeJobbers e a foto do Eduardo.
3. **Pix e boleto.** O FAQ promete os dois. Confirmar que estão habilitados no
   checkout da Hotmart.

## ⚠️ Toda semana que publicar aulas novas

O número de aulas no ar aparece em **4 lugares** no `index.html`. Todos precisam
mudar juntos, senão a página se contradiz:

1. Faixa de status no topo (`.status-band`)
2. Selos e contagem por módulo (`.mod-list` — chips No ar / Em publicação / Em produção)
3. Bloco "Sendo transparente" (`.curriculum-total`)
4. Primeiro item da lista da oferta (`.offer-includes`) e a primeira pergunta do FAQ

Busque por `8 das 59` e `8 aulas` para achar todos.

## Decisões que não devem ser revertidas sem motivo

- **Barra fixa de CTA no mobile sem `backdrop-filter`.** O fundo é sólido de
  propósito: com `backdrop-filter` a barra não renderiza em alguns contextos
  sem composição por GPU. É a peça que mais converte no celular.
- **Contagem honesta de aulas.** Vender "59 aulas" com 8 publicadas gera
  reembolso nos 7 dias do CDC. A transparência aqui é o que justifica o preço
  de Turma Fundadora.
- **Números verificáveis.** "100+ vagas" e não "centenas" — o Market
  Intelligence coleta ~120 vagas por relatório.
