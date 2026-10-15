## 1. Acessibilidade (P1/P2)

- [x] 1.1 Foco bicolor: outline petróleo + anel externo branco em `:focus-visible`; override com sálvia-clara em `.page-banner`, `.section-dark` e `.card-dark` (css/base.css, css/estilo.css)
- [x] 1.2 Contraste do `.footer-bottom`: branco 0.6 → 0.72 (css/estilo.css)
- [x] 1.3 `scroll-margin-top: 88px` para âncoras internas sob o header sticky
- [x] 1.4 Menu mobile: focus trap entre toggle e lista enquanto aberto; devolver foco ao toggle no clique-fora (js/menu.js)

## 2. Marca e CTAs (P1/P2)

- [x] 2.1 CTA único nos pares duplicados: jornada.html e encontros-e-pgs.html mantêm um primário por bloco de convite
- [x] 2.2 `btn-gold` em âmbar `#d99b2b` com texto quase-preto, hover/active coerentes (css/estilo.css)
- [x] 2.3 Padronizar destino do rótulo "Quero visitar este domingo" (mesmo verbo = mesmo destino)
- [x] 2.4 Tira `.vitral-strip` como divisor acima do convite final das subpáginas de conteúdo
- [x] 2.5 Gemas nos destaques: números/tags de listas com safira/esmeralda/rubi (âmbar só em fundo/borda com texto escuro), contraste verificado

## 3. Higiene técnica (P3)

- [x] 3.1 Google Fonts: manter apenas wght 400;600;700 nas 9 páginas
- [x] 3.2 Remover código morto: subsistema de dropdown (CSS+JS), `.btn-navy`, `.grid-2`, `.meta-line`, bloco hero fóssil; atualizar comentário obsoleto da linha 1
- [x] 3.3 Excluir assets órfãos (~2,5 MB) após grep provando zero referências por arquivo
- [x] 3.4 Alvos sociais ≥44px via padding transparente
- [x] 3.5 Waze com `&navigate=yes` na página de contato
- [x] 3.6 Estilos inline de espaçamento convertidos em utilitárias
- [x] 3.7 Restaurar docs/conteudo/novo/homepage.md a partir de docs/conteudo/homepage.md

## 4. Verificação

- [x] 4.1 Detector determinístico re-executado sem novos findings (falsos positivos documentados aceitos: Montserrat é spec da marca; travessões são português editorial)
- [x] 4.2 Header/footer byte-idênticos nas 9 páginas (diff automatizado, exceto aria-current)
- [x] 4.3 Contrastes alterados recalculados ≥ alvo AA
- [x] 4.4 Zero referências restantes aos assets removidos e às classes removidas

## 5. Fechamento

- [x] 5.1 Conferência visual do usuário no browser (roteiro de URLs fornecido)
- [x] 5.2 Arquivar change e sincronizar specs marca-nova e site-estatico-vitral
