## Why

O site (v2, mundo "Vitral Arquitetônico") tem identidade coesa, mas a linguagem visual ainda é genérica de site institucional (cards em grade, eyebrow pill, banners marinho). O conteúdo do site fala de **mesa e hospitalidade** ("puxe uma cadeira", café, pertencimento). Aprovamos o novo mundo visual **"O Café da Rua"**: a linguagem das fachadas pintadas à mão e das lousas de café do interior paulista, que carrega o conceito do conteúdo de forma direta.

## What Changes

- Novo mundo visual "O Café da Rua" aplicado à **HOME** nesta rodada: fachada de café com **letreiro pintado à mão** (convite) + **lousa de giz** (informação prática) + a **janela de vitral** (marca) como vidro pintado da vitrine.
- Tipografia: **Bree Serif** (letreiro), **Kalam** (lousa), **Archivo** (corpo).
- Cor Committed quente: fundos de pedra lavada/creme e marrom-café; as 4 gemas do vitral como tintas pintadas; âmbar profundo nos CTAs (AA).
- Remoção do padrão eyebrow/kicker acima de heading; H2 alinhados à fonte da verdade (`docs/conteudo/homepage.md`).
- **Conteúdo inalterado** (verbatim): textos, dados institucionais e canais permanecem.
- **Marca preservada**: janela de vitral (`assets/vitral.svg`) e tira de 4 cores continuam.
- Escopo desta rodada: apenas a HOME; header/footer estilizados via `body.home`; subpáginas permanecem no mundo anterior (extensão futura).

## Capabilities

### New Capabilities
- `design-cafe-da-rua`: mundo visual "O Café da Rua" (letreiro pintado + lousa de giz), aplicado à HOME do site estático.

### Modified Capabilities
<!-- Nenhuma; nova capability visual. -->

## Impact

- `css/tokens.css` — novos tokens café (aditivos; tokens atuais preservados para as subpáginas).
- `css/estilo.css` — estilos `body.home` (hero-fachada, lousa, cartões de mesa, passaporte, quadro da história, botões/inputs).
- `index.html` — fontes Bree Serif/Kalam/Archivo no `<head>`, `body.home`, seções no mundo café, conteúdo verbatim.
- `docs/conteudo/homepage.md` — referência para H2 e textos (sem alteração do arquivo).
- Subpáginas e 404: intactas.
