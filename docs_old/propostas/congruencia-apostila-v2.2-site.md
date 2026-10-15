# Análise de Congruência — Apostila "Quem Somos" v2.2 × Site

**Data:** 2026-08-23 · **Fonte:** `trilha_de_novos/docs/apostilas/docx/VITRAL — Quem Somos e Como Caminhamos Juntos • v2.2.docx` × conteúdo publicado (`docs/conteudo/novo/*.md` + HTML)

## Veredito

Tom e voz: **altamente congruentes** — mesma casa escrevendo. Conteúdo: 4 conceitos estruturantes da apostila ausentes do site + 2 nuances factuais/terminológicas.

## Congruências confirmadas

| Elemento | Status |
|---|---|
| Propósito verbatim ("cansados de fingir… lugar à mesa") | idêntico |
| Valores Simples/Missional/Acolhedor com os mesmos slogans | idêntico |
| Jornada do Discípulo: 3 estações, perguntas centrais, 9/17/8 passos | idêntico |
| Títulos dos 9 passos da Trilha (= docx por extenso) | idêntico |
| Cordão de Três Dobras (home, encontros, crianças) | idêntico |
| PGs: 4–12 pessoas, semanais, casas/cafés | idêntico |
| História/IPIB: Pr. Evandro 2014, salão 2016, IPI Vitral 2022, 500+ igrejas | idêntico |
| Filtro da vida real ("O Chão") | congruente em espírito |
| C.A.F.É./G.A.P.I.S. prometidos na página Jornada | entregues pelo docx do Passo 4 |

## Incongruências e backlog

| # | Sev | Achado | Estado |
|---|---|---|---|
| 1 | P1 | Missão "ACOLHER · FORMAR · ENRAIZAR · ENVIAR" ausente do site (ciclo central da apostila §5) | pendente — exige ok de conteúdo |
| 2 | P2 | Visão 2036 + "não a maior igreja, a que melhor cuida das pessoas" ausentes (§6) | pendente — exige ok de conteúdo |
| 3 | P2 | Imagem "videira e treliça" ausente (Parte 2) | pendente — exige ok de conteúdo |
| 4 | P2 | Foco do biênio 2026–2027 "Um Lugar no Vitral" (Ef 4:16) ausente (§16) | pendente — exige ok de conteúdo |
| 5 | P3 | ~~Tensão terminológica "Mordomo"~~ → **RESOLVIDO**: "(Mordomos)" removido dos 4 Times de Servidores (commit cb4baef) | concluído |
| 6 | P3 | Linha histórica: site comprime autonomia (apostila: fim de 2019) com jurídico out/2022 numa linha só de 2022 | pendente — ajuste fino factual |
| 7 | P3 | Apelido do G.A.P.I.S.: site "Oração de Bolso" × Passo 4 "oração que cabe no trânsito"/"frase de bolso" | pendente — cosmético |

## Forma/tom

- Apostila usa emojis estruturantes (🟢🟡🔵 das estações); o site não usa emojis (convenção do repo). As cores das estações casam com as gemas da marca — oportunidade de traduzir visualmente.
- Nenhum conflito de voz: segunda pessoa direta, anti-jargão, "ritmo não corrida", café/mesa/vitral presentes nos dois lados.

## Decisão registrada

Itens 1–4 mexem em conteúdo institucional verbatim — dependem de aprovação da liderança antes de entrar no site. Ao implementar, criar change OpenSpec com delta em `site-estatico-vitral` (ou nova capability de conteúdo).
