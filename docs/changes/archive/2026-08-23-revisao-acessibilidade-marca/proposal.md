## Why

Revisão completa do site (dual-agent: design review + auditoria técnica) encontrou 1 violação P1 de acessibilidade (foco invisível nos CTAs sobre fundos escuros, WCAG 2.4.7/1.4.11), uso subutilizado da marca no corpo das páginas e dívida técnica acumulada (código morto, assets órfãos, pesos de fonte ociosos).

## What Changes

- Anel de foco visível em todas as superfícies (bicolor/adaptativo em fundos escuros), contraste do copyright do rodapé corrigido e âncoras internas com offset do header sticky.
- Menu mobile com focus trap completo e devolução de foco em todo caminho de fechamento.
- Gramática de CTA: um botão primário por bloco de convite (pares duplicados com o mesmo destino são unificados); mesmo verbo leva ao mesmo destino em todo o site.
- Botão de destaque (`btn-gold`) passa a usar a gema âmbar da marca, tornando-o genuinamente distinto do primário.
- Tira de 4 gemas (marca inegociável) atua também no corpo das páginas: divisor acima dos convites-finais das subpáginas e cores de gema em números/tags de listas — sem alterar a tira preservada no footer.
- Higiene técnica: remoção de código morto (subsistema de dropdown, classes sem uso), exclusão de assets órfãos (~2,5 MB), corte dos pesos de fonte não utilizados, alvos de toque sociais ≥44px, rota Waze com navegação direta, estilos inline convertidos em utilitárias e restauração de docs/conteudo/novo/homepage.md.
- Registrado fora de escopo: ausência de caminho de contribuição (PIX/Itaú) no site — decisão pendente com a liderança.

## Capabilities

### New Capabilities

(nenhuma)

### Modified Capabilities

- `marca-nova`: a tira de 4 gemas passa a ser exigida também como elemento vivo no corpo das páginas (divisor de convites-finais e destaques), mantendo intacta sua presença no footer; botão de destaque adquire identidade própria na gema âmbar.
- `site-estatico-vitral`: requisitos de acessibilidade elevados (foco visível ≥3:1 em qualquer fundo, gestão completa de foco no drawer mobile, âncoras nunca encobertas pelo header) e requisito de consistência de chamadas para ação (um primário por bloco; verbo igual → destino igual).

## Impact

- CSS: css/base.css, css/estilo.css (foco, contraste, âncoras, botões, divisor, utilitárias, remoção de mortos).
- JS: js/menu.js (focus trap e devolução de foco).
- HTML: as 9 páginas (pesos de fonte no head; corpo de jornada, encontros-e-pgs, contato, grande-banquete e convites-finais das demais).
- Assets: exclusão de arquivos órfãos em assets/img e assets/logos após verificação de zero referências.
- Conteúdo: nenhum texto verbatim alterado; docs/conteudo/novo/homepage.md restaurado a partir de docs/conteudo/homepage.md.
