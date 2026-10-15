# Auditoria Técnica — SEO e GEO do Site Comunidade Vitral

- **Data:** 2026-08-30
- **Escopo:** 9 páginas de conteúdo (`index`, `quem-somos`, `no-que-cremos`, `jornada`, `grande-banquete`, `encontros-e-pgs`, `criancas-e-familia`, `causas-e-cidade`, `contato`) + `404.html`
- **Método:** auditoria técnica no código-fonte (HTML) — head, canônicas, dados estruturados, hierarquia de títulos, acessibilidade, assets, configuração de deploy.
- **Status:** auditoria técnica inicial. Recomendações de GEO/marketing ficam para etapa posterior (ainda não há pesquisa de palavras-chave nem verificação no Search Console).

---

## 1. Fundamentos SEO (o que está implementado)

Todas as 9 páginas de conteúdo têm:

- `<html lang="pt-BR">` ✅
- `<meta charset="UTF-8">` e viewport ✅
- `<title>` único por página ✅
- `<meta name="description">` único por página ✅
- `<link rel="canonical">` apontando para a URL completa no GitHub Pages ✅
- Open Graph (`og:type`, `og:title`, `og:description`, `og:url`, `og:image`) ✅
- Twitter Card (`summary_large_image`) ✅
- `favicon.svg` e `og-image.png` presentes em `assets/` ✅
- 1 único H1 por página ✅ e hierarquia H2/H3 estruturada ✅
- Imagens com atributo `alt` (0 imagens sem `alt` em todas as páginas) ✅
- `.nojekyll` presente (desativa o processamento Jekyll do Pages) ✅

A página `404.html` está correta: `<meta name="robots" content="noindex">` ✅ (não deve ser indexada).

`robots.txt` libera tudo e aponta o sitemap ✅:
```
User-agent: *
Allow: /

Sitemap: https://ismaelmmachado.github.io/comunidadevitral/sitemap.xml
```

`sitemap.xml` lista as 9 URLs de conteúdo ✅.

---

## 2. Achados por severidade

### 🔴 Alta

#### A1. Dados estruturados (JSON-LD) apenas na HOME
O `<script type="application/ld+json">` com `@type: Church` + `PostalAddress` existe **somente em `index.html`**. As demais 8 páginas de conteúdo não têm nenhum JSON-LD. Impacto: boa para a Home, mas o restante do site não expõe semântica estruturada (BreadcrumbList, FAQ, Article, Organization) para os buscadores e motores de IA.

#### A2. Divisão de domínios — GitHub Pages vs. domínio institucional
Canônicas, sitemap, robots e Open Graph apontam para `https://ismaelmmachado.github.io/comunidadevitral/…`, mas o domínio institucional é `www.comunidadevitral.com.br` (que **hoje ainda é o site Wix**, conforme referências nos HTML e `docs/conteudo/link-bio.md`). 
- Risco: split de signals / conteúdo duplicado quando o domínio institucional migrar.
- Não há `CNAME` no repositório para custom domain, e o `robots.txt`/`sitemap.xml` apontam só para o subpath do Pages.
- **Atenção:** referências ao domínio `.com.br` aparecem no corpo de todas as páginas (rodapé, endereço docs) — por ora são menções textuais, não contradizem as canônicas, mas precisam ser resolvidas na migração.

### 🟠 Média

#### M1. Variação no comprimento de title/description
- `title`: 32 a 62 caracteres — dentro da faixa saudável (~50-60), ok.
- `description`: 75 a 175 caracteres. **Várias acima do ideal** (~150–160): 
  - `grande-banquete.html` = 175
  - `quem-somos.html` = 163
  - As demais ficam entre 140–159.
  - Impacto: o Google pode truncar trechos longos. Revisar as maiores.

#### M2. Home sem `og:image` de dimensões garantidas (histórico Wix)
`og-image.png` existe (252 KB). Para compartilhamento ideal no WhatsApp/Facebook, imagens OG recomendadas são ~1200×630. Não confirmado o tamanho exato na auditoria; verificar dimensões e peso.

### 🟢 Baixa / Observações

#### B1. 404 tem `<title>` e description (ok), mas sem canônica — correto (página sem canônica + noindex é saudável).
#### B2. Não há `<meta name="robots">` nas páginas de conteúdo — comportamento padrão (index) é o desejado. ✓ sem ação.
#### B3. Não há verificação de propriedade no Google Search Console nem Bing Webmaster Tools registrada no repo.

---

## 3. GEO — otimização para motores de resposta de IA

**Não há estratégia GEO dedicada.** O que existe de base reutilizável:

- JSON-LD estruturado `Church` + `PostalAddress` na Home (ajuda a compreensão semântica por IA/conhecimento).
- Conteúdo textual rico em cada página (verdades da fé, datas, contato, endereço, CNPJ, PIX) — matéria-prima boa para citações por IA.
- Zero dependências de runtime e HTML semântico (H1/H2/H3, lang, alt) → CSS/HTML leve diminui a chance de erro de renderização por crawlers de IA (muitos não executam JS pesado). Este é um ponto forte.

**Oportunidades GEO (a desenvolver):**

1. Ampliar dados estruturados para todas as páginas (Organization no rodapé/global, BreadcrumbList, Article/Page).
2. Conteúdo "respondível": respostas diretas e específicas (ex.: "o que é a Comunidade Vitral", "onde é o culto", "horários", "endereço", "como chegar", "o que crer") — frases autocontidas que os LLMs conseguem citar.
3. Coerência NAP (Nome/Endereço/Telefone) e consistência com o Google Business Profile (perfil no Maps existe: "Vitral - Igreja em Pessoas").
4. Verificação Search Console + envio do sitemap.

---

## 4. Resumo executivo

| Item | Status |
|---|---|
| Lang, charset, viewport | ✅ |
| Title + description por página | ✅ (descrições longas a revisar) |
| Canonical | ✅ no Pages |
| Open Graph / Twitter | ✅ |
| JSON-LD estruturado | ⚠️ só na Home |
| H1 único + hierarquia H2/H3 | ✅ |
| Alt em imagens | ✅ |
| robots.txt + sitemap.xml | ✅ |
| 404 noindex | ✅ |
| .nojekyll | ✅ |
| Domínio institucional / CNAME | ⚠️ pendente migração |
| Search Console verificado | ❌ não registrado |
| Estratégia GEO | ❌ não existe |

---

## 5. Próximos passos sugeridos

1. **Adicionar JSON-LD** (`Organization`, `BreadcrumbList`, e nos tipos de página) ao `<head>` das 8 páginas restantes.
2. **Encurtar** as meta descriptions acima de ~160 caracteres (`grande-banquete`, `quem-somos`).
3. **Verificar dimensões** do `og-image.png` (ideal 1200×630).
4. **Decidir migração de domínio** para `www.comunidadevitral.com.br` (exige `CNAME` no repo + atualizar canônicas, sitemap, robots e OG URLs) — alinhar com o usuário sobre o momento.
5. **Registrar no Search Console** e enviar o sitemap do Pages.
6. **Elaborar camada GEO**: perguntas frequentes respondíveis, dados estruturados completos e consistência NAP com o Google Business Profile.

> Este documento é a auditoria técnica. A construção de um plano de palavras-chave e a estratégia GEO de marketing são etapas separadas, a propor em `openspec/` se desejado.
