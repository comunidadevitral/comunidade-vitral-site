## 1. Mídia (WebP + lazy + dimensões)

- [x] 1.1 Converter as 15 imagens de `assets/img/` para `.webp` q80 mantendo dimensões
- [x] 1.2 Trocar referências `src` para `.webp` em todos os HTMLs
- [x] 1.3 Adicionar `width`/`height` explícitos e `loading="lazy"` nas imagens fora da primeira dobra (banners/hero eager)

## 2. Bloco Onde e Quando na HOME

- [x] 2.1 Adicionar card prático (horário, endereço, botões Maps e Waze) na seção "A mesa está posta…" do `index.html`

## 3. Menu drawer mobile

- [x] 3.1 CSS do drawer fullscreen @≤760px com alvos ≥48px
- [x] 3.2 JS: Esc fecha, clique-fora fecha, link fecha, scroll-lock e foco devolvido ao botão

## 4. Microinterações e limpeza

- [x] 4.1 Estados `:active` em `.btn`, cards e links do nav (respeitando reduced-motion)
- [x] 4.2 Remover token `--grad-marca` de `css/tokens.css`

## 5. Verificação e entrega

- [x] 5.1 Detector impeccable nos HTMLs editados; links/assets íntegros; contraste AA no drawer
- [x] 5.2 Comparativo de peso das imagens antes/depois (<2 MB)
- [x] 5.3 `openspec validate --specs`; atualizar checkboxes deste tasks.md
