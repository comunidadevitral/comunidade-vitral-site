## Context

Site estático (HTML5 + CSS puro, sem build step) com 9 páginas que repetem header/footer manualmente. Revisão dual-agent (design review + auditoria técnica com detector) produziu os issues priorizados; ver proposal.md. Tokens em `css/tokens.css`; estilos em `css/base.css` + `css/estilo.css`; JS mínimo em `js/menu.js`. Sem framework de teste: verificação por scripts de inspeção (grep/diff), recálculo de contraste e detector determinístico.

## Goals / Non-Goals

**Goals:**
- WCAG 2.1 AA objetivo: foco ≥3:1 em qualquer fundo, contraste do rodapé, âncoras visíveis, foco contido no drawer.
- Marca Nova atuante no corpo (gemas vivas) sem alterar a tira nem conteúdo verbatim.
- Reduzir dívida: zero código morto, zero assets órfãos, payload de fontes mínimo.

**Non-Goals:**
- Criar caminho de contribuição (PIX/Itaú) — decidido fora de escopo nesta change.
- Introduzir build step, includes server-side ou refatorar a repetição header/footer.
- Trocar fotografia/imagens do site ou reordenar o menu.

## Decisions

1. **Foco bicolor em vez de trocar cor por contexto**: `outline` petróleo + anel externo branco via `box-shadow`, e override para `--sage-lighter` nos contextos escuros (`.page-banner`, `.section-dark`, `.card-dark`). Alternativa descartada: cor única clara global — perde contraste no fundo claro (7,37:1 hoje).
2. **Contraste do rodapé por alpha, não por token novo**: `rgba(255,255,255,0.72)` (~5,3:1). Alternativa descartada: `--sage-lighter` — muda o tom visual do copyright.
3. **Âncoras via `scroll-margin-top: 88px`** (header sticky de 72px + folga) aplicado a `[id]`. Alternativa descartada: JS de scroll manual — complexidade desnecessária sem build.
4. **Focus trap por loop de Tab no menu.js**: interceptação de Tab alternando entre toggle e lista; devolução de foco também no clique-fora. Mantém o arquivo único e sem dependências.
5. **CTA único por bloco**: nos pares duplicados (jornada, encontros-e-pgs) mantém-se o botão primário com rótulo de ação mais claro e remove-se o redundante — ambos já apontavam para o mesmo wa.me institucional, logo nenhuma capacidade é perdida.
6. **`btn-gold` âmbar `#d99b2b` com texto `--off-black`**: contraste ~8:1; injeta gema no corpo. Alternativa descartada: texto branco sobre âmbar (2,2:1 — falha AA).
7. **Gemas nos destaques respeitando AA**: safira/esmeralda/rubi podem tingir texto grande/números; âmbar só em fundos/bordas com texto escuro (âmbar como texto falha mesmo em texto grande, 2,27:1 < 3:1).
8. **Divisor de convite final**: `::before` na classe `.section-dark` (presente apenas no convite final de cada subpágina), replicando o padrão já usado pelo footer; a classe `.vitral-strip` morta é removida em vez de reativada. Footer mantém sua tira própria inalterada.
9. **Limpeza guiada por referência cruzada**: cada asset/classe só é removido após grep provando zero referências; git preserva histórico.
10. **Fontes**: manter apenas `wght@400;600;700` (usados de fato) na URL do Google Fonts nas 9 páginas.

## Risks / Trade-offs

- [Edição em 9 páginas pode dessincronizar header/footer] → diff automatizado das seções ao final da change.
- [Remoção de assets pode quebrar referência não catalogada] → grep por nome de arquivo antes de cada exclusão; rollback trivial via git.
- [Divisor novo altera ritmo visual aceito pelas páginas] → elemento discreto (6px), mesma linguagem já presente no footer; conferência visual do usuário como gate final.
- [Focus trap mal implementado pode prender teclado] → trap ativo somente com `.open`; Escape e clique-fora sempre liberam; testado manualmente por roteiro.

## Migration Plan

Sem migração de dados/deploy: push em `homologacao` publica direto (GitHub Pages). Rollback = revert do commit.

## Open Questions

(nenhuma)
