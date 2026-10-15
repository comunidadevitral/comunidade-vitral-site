# Design — Identidade "Marca Nova" no site inteiro

## Context

Estado atual e motivação em `proposal.md`. O site tem dois mundos visuais: a HOME no mundo "O Café da Rua" (scoped em `body.home`, frio em `estilo.css`) e as subpáginas/404 no padrão "Vitral Arquitetônico". A identidade "Marca Nova" (verde petróleo/sálvia + Montserrat) foi aprovada e testada em `quem-somos.html` via overlay `body.marca-nova`. Esta rodada eleva a Marca Nova a padrão único, removendo o teste.

## Goals / Non-Goals

**Goals**
- Marca Nova como comportamento padrão em `tokens.css`/`estilo.css`, sem overlay.
- HOME re-tintada mantendo estrutura do hero (convite, info, CTAs, emblema na moldura) e conteúdo verbatim.
- Tira de 4 cores preservada no topo do footer (marca inegociável).
- Montserrat em todas as páginas; documentação (DESIGN/PRODUCT/AGENTS) e specs openspec atualizadas; specs antigas arquivadas.

**Non-Goals**
- Alterar conteúdo, navegação, URLs ou dados institucionais.
- Adicionar build step, dependências de runtime ou componentes novos.
- Manter o overlay `marca-nova.css` ou a dupla identidade.

## Decisions

1. **Paleta Marca Nova como `:root` padrão.** As variáveis petróleo/sálvia/cinza passam a ser o valor default em `css/tokens.css`; as gemas (`--safira/esmeralda/ambar/rubi`) são preservadas para a tira do footer. *Alternativa rejeitada:* manter `tokens.css` antigo + overlay — deixaria código morto e dupla fonte de verdade.
2. **Re-tinta direta em `estilo.css`.** Os seletores que hoje são `body.marca-nova ...` tornam-se o comportamento padrão; o bloco `body.home` (café) é substituído por overrides da Marca Nova ou removido quando o padrão já cobre. *Alternativa rejeitada:* manter `body.home` café e sobrepor — manteria o híbrido.
3. **HOME hero re-tintado, estrutura preservada.** `.chalk-line` deixa de ser "lousa de giz" e vira faixa verde petróleo com texto branco; `.hero-glass` (moldura do emblema) usa base clara `--sage-claro` e borda petróleo; H1 Montserrat quase-preto.
4. **Tira de 4 cores no footer.** `body.marca-nova .site-footer::before` (gradiente petróleo) é revertido para a tira de 4 cores (`linear-gradient` safira→esmeralda→âmbar→rubi); o fundo do footer usa `--grad-banner`.
5. **Montserrat única.** `--font-serif` e `--font-sans` = Montserrat; todos os `<head>` carregam apenas `family=Montserrat:wght@400;500;600;700;800`. Fontes antigas (Bree/Kalam/Archivo, Playfair/Inter) removidas destes `head`.
6. **Remoção do overlay.** `css/marca-nova.css` é excluído; `quem-somos.html` perde o `<link>` e `class="marca-nova"`.

## Risks / Trade-offs

- [Re-tinta direta pode perder algum ajuste fino do teste `quem-somos`] → Dobrar o CSS do overlay fielmente no padrão e conferir no detector + browser (desktop/mobile).
- [Hero da HOME perde o tom "fachada de café"] → Deliberado e aprovado (re-tinta); manter estrutura e emblema conserva a identidade da marca.
- [Token órfão de café/vitral restante pode conflitar] → Limpar tokens não referenciados em `tokens.css` ao final; conferir por grep.
- [Contraste sobre `--grad-banner` (branco/petróleo) no mobile] → Validar pares críticos (AA ≥ 4.5:1) na verificação.

## Migration Plan

1. Implementar na branch `homologacao`.
2. Verificar com o detector mecânico (`node /root/.opencode/skills/impeccable/scripts/detect.mjs --json <página>`) nas 8 páginas.
3. Conferência visual no browser (desktop + 320px: HOME, subpágina com tabela, subpágina com seção escura, 404).
4. Atualizar DESIGN.md, PRODUCT.md, AGENTS.md; sync da spec e arquivamento do change.

## Open Questions

Nenhuma — decisões de escopo e de marca resolvidas com o usuário antes do plano.