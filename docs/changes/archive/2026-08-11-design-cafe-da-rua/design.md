# Design — Mundo Visual "O Café da Rua" (HOME)

## Context

Motivação e escopo em `proposal.md`. Direção sorteada por `concept-seed` (mode persuade) e escolhida pelo usuário: "Letreiros de Café do Interior". Surface brief: `.impeccable/surfaces/index-html.md`.

## Goals / Non-Goals

**Goals**
- Home no mundo "O Café da Rua": fachada de café com letreiro pintado, lousa de giz, janela de vitral como vidro pintado.
- Clareza do convite no 1º viewport (letreiro + linha de lousa "Domingos às 10h · café quentinho te espera").
- Conteúdo verbatim preservado; H2 alinhados a `docs/conteudo/homepage.md`.
- Acessibilidade WCAG 2.1 AA e performance mantidas; ban de eyebrow/kicker acima de heading.

**Non-Goals**
- Alterar subpáginas ou 404 (permanecem no mundo "Vitral Arquitetônico" até rodada futura).
- Alterar conteúdo, navegação, URLs ou dados institucionais.
- Mudar o markup do header/footer (estilo scoped em `body.home`).

## Decisions

1. **CSS aditivo e scoped**: novos tokens café em `tokens.css` (sem sobrescrever os atuais); estilos novos sob `body.home` em `estilo.css` — subpáginas intactas.
2. **Tipografia do mundo**: letreiro pintado à mão = **Bree Serif** (display); lousa = **Kalam** (escrita a giz); corpo = **Archivo** (grotesca brasileira, Omnibus-Type). Fontes via Google Fonts no `<head>` da Home.
3. **Cor Committed quente**: fundos pedra lavada `#f7f3ea` / creme `#f5efe2` / marrom-café `#4a3528` (e `#3a2b1f` para o "entardecer"); as 4 gemas (safira/esmeralda/âmbar/rubi) como tintas pintadas em doses; âmbar profundo `#a06a18` nos CTAs (AA). Cena: café do interior à luz do dia.
4. **Marca preservada**: `assets/vitral.svg` entra no hero como o vidro pintado da vitrine (moldura de janela); a tira de 4 cores permanece como divisor/porta.
5. **Sem eyebrow**: os rótulos de seção atuais são absorvidos nos H2/leads (fonte da verdade), sem kicker acima de heading.
6. **Componentes do mundo**: mesas (cards quentes com filete pintado), lousa (painel marrom com giz), passaporte (lista numerada com carimbo), quadro da história (seção escura café ao entardecer). Sem sombras duras, sem gradiente de texto, sem vidro/blur decorativo.

## Risks / Trade-offs

- [Header/footer compartilhados] → Estilizados via `body.home`; markup inalterado (regra AGENTS de repetição mantida); subpáginas seguem no mundo anterior.
- [Café escuro pode reduzir "clareza"] → Marrom-café usado em painéis com giz/creme de alto contraste (AA); fundos gerais claros.
- [Bree Serif pode soar genérica de "artesanato"] → Usada em display pesado e composições de letreiro; o corpo Archivo dá o contraponto quieto.

## Migration Plan

1. Implementar na branch `homologacao`.
2. Validar contraste, detector e conteúdo verbatim.
3. Extensão do mundo às subpáginas em rodada futura.
