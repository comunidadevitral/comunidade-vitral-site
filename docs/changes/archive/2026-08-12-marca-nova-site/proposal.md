## Why

O site mantém dois mundos visuais divergentes — a HOME no mundo "O Café da Rua" e as subpáginas no "Vitral Arquitetônico". O usuário aprovou como teste em `quem-somos.html` a nova identidade "Marca Nova" (verde petróleo `#005f6b` / verde acinzentado `#94a69a`, tipografia Montserrat) e deseja aplicá-la ao site inteiro como padrão único, eliminando a dupla identidade.

## What Changes

- Nova identidade visual **Marca Nova** adotada como padrão único em 100% do site (HOME, 6 subpáginas e 404), via refatoração de `css/tokens.css` e `css/estilo.css`.
- Tipografia única **Montserrat** em todas as páginas (substitui Bree Serif/Kalam/Archivo na HOME e Playfair Display/Inter nas subpáginas).
- HOME re-tintada para a Marca Nova mantendo a estrutura do hero (convite, linha de informação, CTAs e emblema oficial na moldura).
- Tira de 4 cores (safira/esmeralda/âmbar/rubi) **preservada** no topo do footer como marca inegociável.
- Remoção do overlay `css/marca-nova.css` (teste) após dobrar seu conteúdo no padrão.
- **Conteúdo inalterado** (verbatim): textos, dados institucionais e canais permanecem.
- Feitos `design-cafe-da-rua` e `design-vitral-arquitetonico` deixam de ser o sistema ativo; spec `marca-nova` documenta o novo padrão.

## Capabilities

### New Capabilities
- `marca-nova`: identidade visual única do site inteiro (paleta verde petróleo/acinzentado, Montserrat), preservando conteúdo verbatim, emblema oficial e a tira de 4 cores.

### Modified Capabilities
<!-- Nenhuma — as specs `design-cafe-da-rua` e `design-vitral-arquitetonico` serão arquivadas; a nova capability `marca-nova` as substitui. -->

## Impact

- `css/tokens.css` — paleta Marca Nova como padrão `:root` (petróleo/sálvia/cinzas), Montserrat; tokens café/vitral que ficarem órfãos removidos; gemas preservadas.
- `css/estilo.css` — re-tinta de componentes (header, banner, seções, cards, listas, FAQ, tabela, botões, footer); bloco `body.home` substituído pela Marca Nova; `.site-footer::before` restaura a tira de 4 cores.
- `css/marca-nova.css` — excluído.
- `index.html`, `quem-somos.html`, `jornada.html`, `encontros-e-pgs.html`, `criancas-e-familia.html`, `causas-e-cidade.html`, `contato.html`, `404.html` — fonte Montserrat no `<head>`; `quem-somos.html` perde o link overlay e `class="marca-nova"`.
- `DESIGN.md`, `PRODUCT.md`, `AGENTS.md` — atualização do sistema visual.
- `openspec/specs/` — nova spec `marca-nova`; arquivamento de `design-cafe-da-rua` e `design-vitral-arquitetonico`.