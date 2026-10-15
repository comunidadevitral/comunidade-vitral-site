# Comunidade Vitral — Proposta de Design System

## Conceito
- **Tom:** acolhedor, simples, contemporâneo, sem exagero.
- **Referência visual:** minimalismo moderno com personalidade.
- **Foco:** clareza, legibilidade e conversão suave (Visite-nos / Encontros).

## Identidade
- **Nome:** Comunidade Vitral
- **Tagline:** Uma comunidade simples, missional e acolhedora
- **Valores:** Simplicidade, missão, acolhimento
- **Símbolo:** vidro/translucidez

## Paleta
- Fundo: `#f5f5f7`
- Superfície: `#ffffff`
- Texto principal: `#1d1d1f`
- Texto secundário: `#6e6e73`
- Acento primário: `#ec4899`
- Acento secundário: `#f472b6`
- Borda: `#d2d2d7`
- Sombra: `rgba(0,0,0,0.04)`

## Tipografia
- Família base: `-apple-system, BlinkMacSystemFont, SF Pro Text, Segoe UI, Roboto, sans-serif`
- Título H1: `clamp(32px, 4.4vw, 52px) / 700 / -0.5px`
- Título H2: `clamp(24px, 3vw, 30px) / 700 / -0.2px`
- Corpo: `16-20px / 400-500 / 1.5`
- Labels: `12px / 700 / uppercase + tracking`

## Layout
- Container: `max-width: 980px`
- Espaçamento: `clamp(18px, 3vw, 32px)`
- Grid de cards: `repeat(3, 1fr)` no desktop, `1fr` no mobile
- Grid de info: `repeat(2, 1fr)` no desktop, `1fr` no mobile

## Componentes
- **Header:** sticky, blur, borda inferior
- **Hero:** título + subtítulo + CTAs, gradiente suave
- **Cards:** superfície branca, borda, sombra leve, hover com elevação
- **Listas:** grid de itens com fundo branco e borda
- **Botões:** primário rosa, secundário branco/cinza, raio 999px
- **Labels:** uppercase, compacto, cor de acento

## Interações
- Hover em cards: elevação leve
- Hover em botões: translateY(-1px)
- Foco visível: outline rosa
- Respeito a `prefers-reduced-motion`

## Responsividade
- Mobile-first
- Breakpoint principal: `760px`
- Menu mobile: toggle com overlay/flutuante

## Conversão
- CTAs claros no hero
- Seção "Visite-nos" como fechamento forte
- Contato com telefone e e-mail visíveis

## Acessibilidade
- Contraste mínimo 4.5:1
- Estados de foco visíveis
- Sem animações intrusivas
