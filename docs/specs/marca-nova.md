# marca-nova Specification

## Purpose

O site adota a identidade visual única "Marca Nova" (verde petróleo/acinzentado, tipografia Montserrat) em todas as páginas, substituindo os mundos "O Café da Rua" e "Vitral Arquitetônico", preservando conteúdo verbatim, o emblema oficial e a tira de 4 cores.

## Requirements

### Requirement: Paleta Marca Nova aplicada a todo o site

O site DEVE (MUST) usar a paleta Marca Nova como padrão em todas as páginas (HOME, subpáginas e 404): verde petróleo `#005f6b`, verde petróleo profundo `#00434d`, verde acinzentado `#94a69a`, cinza-sálvia claro `#e9ede9`, quase-preto `#1f2421`, cinza secundário `#5b6b63` e borda `#d7ded9`. A tipografia DEVE (MUST) ser **Montserrat** para títulos e corpo.

#### Scenario: Verificar a paleta nos tokens
- **WHEN** o usuário inspeciona `css/tokens.css`
- **THEN** encontra as variáveis da paleta Marca Nova (petróleo, sálvia, cinzas) e Montserrat como fonte padrão

#### Scenario: Acessar uma página
- **WHEN** o usuário abre qualquer página do site
- **THEN** ela usa a paleta Marca Nova e tipografia Montserrat

### Requirement: HOME re-tintada mantendo a estrutura do hero

A HOME DEVE (MUST) manter a estrutura do hero (convite, linha de informação, CTAs e o emblema oficial `assets/logos/logo-ipi-comunidade-vitral.png` na moldura) re-tintada para a Marca Nova: título em Montserrat quase-preto, linha de informação como faixa verde petróleo com texto branco, subtítulo e meta em cinza secundário.

#### Scenario: Abrir a HOME
- **WHEN** o usuário acessa `index.html`
- **THEN** o hero exibe o convite, a linha de informação em faixa petróleo, os CTAs e o emblema oficial na moldura, todos na paleta Marca Nova

### Requirement: Tira de 4 cores preservada no footer

O footer DEVE (MUST) exibir no topo a tira de 4 cores (safira `#2f5f92`, esmeralda `#3f6f5a`, âmbar `#d99b2b`, rubi `#b3493a`) como marca inegociável, sobre o fundo gradiente petróleo. Além do footer, a tira DEVE (MUST) atuar como elemento vivo no corpo das páginas: como divisor acima do bloco de convite final de cada subpágina de conteúdo, e as cores das gemas DEVEM (MUST) identificar destaques do corpo (números/tags de listas e o botão de destaque). O botão de destaque DEVE (MUST) usar a gema âmbar `#d99b2b` com texto quase-preto `#1f2421`, mantendo-o visualmente distinto do botão primário petróleo. A composição da tira em si NÃO DEVE (MUST NOT) ser alterada.

#### Scenario: Conferir o rodapé
- **WHEN** o usuário inspeciona o topo do footer de qualquer página
- **THEN** a tira de 4 cores está presente

#### Scenario: Chegar ao convite final de uma subpágina
- **WHEN** o usuário percorre qualquer subpágina de conteúdo até o bloco de convite final
- **THEN** encontra a tira de 4 gemas como divisor imediatamente acima desse bloco

#### Scenario: Identificar o botão de destaque
- **WHEN** um convite exibe o botão de destaque
- **THEN** ele é reconhecivelmente distinto do botão primário (fundo âmbar com texto escuro, versus fundo petróleo com texto branco)

### Requirement: Overlay marca-nova removido

O overlay `css/marca-nova.css` e a classe `marca-nova` no `<body>` DEVEM (MUST) ser removidos do código, com o conteúdo incorporado ao padrão único.

#### Scenario: Inspecionar o código
- **WHEN** o usuário inspeciona `quem-somos.html` e `css/estilo.css`
- **THEN** não há referência ao arquivo `marca-nova.css` nem à classe `marca-nova`

### Requirement: Conteúdo verbatim inalterado

O conteúdo de todas as páginas DEVE (MUST) permanecer fiel à fonte da verdade (`docs/conteudo/novo/*.md` e `docs/conteudo/homepage.md`): textos, H2, dados institucionais (telefone 17 99619-5302, e-mail contato@comunidadevitral.com.br, endereço, CNPJ 49.075.286/0001-63, PIX, Itaú) e canais (WhatsApp `https://wa.me/5517996195302`).

#### Scenario: Conferir dados de contato
- **WHEN** o usuário inspeciona o rodapé das páginas
- **THEN** telefone, e-mail e endereço estão presentes e corretos

### Requirement: Acessibilidade e responsividade mantidas

O site DEVE (MUST) manter WCAG 2.1 AA na Marca Nova: contraste ≥ 4.5:1 nos pares críticos (texto branco sobre petróleo, quase-preto sobre branco), navegação por teclado com foco visível, imagens com `alt` e sem rolagem horizontal de 320px a desktops.

#### Scenario: Navegar por teclado
- **WHEN** o usuário usa Tab no site
- **THEN** o foco é visível e o link "Pular para o conteúdo" aparece

#### Scenario: Verificar contraste do CTA
- **WHEN** um CTA primário é renderizado
- **THEN** texto branco sobre verde petróleo mantém contraste ≥ 4.5:1