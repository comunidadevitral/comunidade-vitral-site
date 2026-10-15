## Context

Site estático HTML5 + CSS puro (sem build step), publicado via GitHub Pages no subpath `/comunidadevitral/` a partir da branch `homologacao`. Identidade visual única "Marca Nova" (`css/tokens.css`: verde petróleo `#005f6b`, sálvia, Montserrat; sistema em DESIGN.md). Padrão de página já consolidado nas 7 existentes: `<head>` com metadados completos + 3 folhas de estilo, skip-link, header com nav, `.page-banner` com imagem de fundo, seções alternando `.section` / `.section-alt` / `.section-dark`, footer repetido, `js/menu.js`. Componentes disponíveis em `css/estilo.css` sem necessidade de novos: `.grid`, `.card`, `.card-dark`, `.feature-list`, `.faq`, `.btn-gold`, `.btn-outline`, `.section-label`, `.section-lead`. Ver proposta.md para motivação.

## Goals / Non-Goals

**Goals:**
- Nova página fiel ao conteúdo-fonte aprovado, com linguagem Vitral (mesa aberta, acolhimento, sem emojis, sem tom burocrático).
- Reuso integral do design system Marca Nova — zero CSS novo (ou mínimo, apenas se um ajuste fino for inevitável).
- Integração total ao ecossistema: menu em todas as páginas, divulgação na HOME e na Jornada, sitemap.
- Acessibilidade AA e mobile-first desde o primeiro commit.

**Non-Goals:**
- Não criar formulário de inscrição (participação é via padrinho/WhatsApp).
- Não fabricar datas de edição, números de participantes ou depoimentos.
- Não alterar header além do item de menu, nem footer.
- Não criar novas imagens/assets (reusa `assets/img/cafe-encontros.jpg`).

## Decisions

1. **Arquivo na raiz como `grande-banquete.html`** (o markdown fornecido dizia `/grande-banquete`). Motivo: padrão das 7 páginas existentes e funcionamento garantido no subpath do Pages com caminhos relativos. Alternativa descartada: pasta `grande-banquete/index.html` (desnecessária sem rewrite custom).
2. **Emojis substituídos por componentes tipográficos existentes** (`.feature-list` com `.num`, listas com negrito). Motivo: convenção do projeto proíbe emojis e o site tem zero hoje; ícones SVG novos adicionariam peso e manutenção sem ganho. Alternativa descartada: sprites de ícones.
3. **Banner com `assets/img/cafe-encontros.jpg`**: tema mesa/comunhão alinha à metáfora central ("lugar à mesa") sem novo asset. Alternativa descartada: reusar `capa-home-2.jpg` (diluiria o vínculo exclusivo com a Jornada).
4. **Nav com 8º item após "Jornada"**, refletindo a hierarquia de produto (Banquete como impulso da caminhada). Header é repetido — atualizar as 8 páginas + 404 é custo conhecido e documentado no AGENTS.md.
5. **Divulgação orgânica**: bloco curto na HOME (seção de jornada/experiências) e convite discreto ao final da Jornada, ambos linkando `grande-banquete.html` — sem banners agressivos, coerente com "convida, nunca exige".
6. **Terminologia normalizada**: "os 4 Times de Servidores (Mordomos)" (quem-somos.html), "Pequenos Grupos (PGs)" em "casas e cafés" (encontros_pgs.md), Estações 1–3 idênticas à jornada.html.

## Risks / Trade-offs

- [Menu com 8 itens pode ficar apertado em desktop estreito] → verificar quebra em ~900px; o toggle mobile já cobre abaixo disso.
- [`cafe-encontros.jpg` também usada em encontros-e-pgs] → aceito: contexto e copy distintos; alternativa exigiria asset novo fora de escopo.
- [Divergência futura entre página HTML e markdown-fonte] → markdown criado antes do HTML e referenciado como fonte da verdade no change.
- [Expectativa de datas da próxima edição] → página deliberadamente não promete data; CTA direciona ao WhatsApp para informação atualizada.

## Migration Plan

Sem migração de dados. Deploy = commit + push em `homologacao` (Pages reconstrói). Rollback = revert do commit.

## Open Questions

Nenhuma.
