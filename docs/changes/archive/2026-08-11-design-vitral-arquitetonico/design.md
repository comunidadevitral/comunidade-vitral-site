# Design — Vitral Arquitetônico (Direção A)

## Context

Motivação e escopo em `proposal.md`. Aprovado pelo usuário: Direção A (Vitral Luminoso), Playfair Display, paleta "vidro sobre pedra".

## Goals / Non-Goals

**Goals**
- Aplicar a nova paleta e componentes via tokens CSS.
- Hero editorial claro com janela de vitral na HOME.
- Manter conteúdo, navegação e URLs intactos.

**Non-Goals**
- Alterar textos, estrutura de navegação ou URLs.
- Adotar Direção B ou Fraunces.

## Decisions

1. **CSS-first**: toda a mudança visual via `tokens.css`, `base.css` e `estilo.css`; mínimo de edição HTML (apenas hero da HOME e banners das subpáginas).
2. **Janela de vitral como SVG externo** (`assets/vitral.svg`) referenciado por `<img>` no hero — reutilizável e leve.
3. **Tira de vitral no footer via CSS** (`::before`) — sem editar os footers de todas as páginas.
4. Paleta mantém tokens CSS existentes substituindo as cores antigas; nenhum nome de classe quebrado.
5. **Contraste AA**: o degradê de CTA usa âmbar profundo (`--ambar-deep #a06a18`)→rubi, garantindo ≥ 4.5:1 com texto branco; `btn-gold` usa `--ambar-deep`.

## Risks / Trade-offs

- [Hero do TEMPLO era escuro com foto] → Subpáginas usam o banner marinho padrão (mantém foto e CTAs).
- [Grande Banquete usava `.hero` de texto] → Ganhou regra de padding/centralização para container sem `hero-inner`.

## Migration Plan

1. Commitar na branch `homologacao`.
2. Usuário troca o GitHub Pages de volta para `homologacao` para visualizar.
