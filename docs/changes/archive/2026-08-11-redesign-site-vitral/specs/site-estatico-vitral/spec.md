# site-estatico-vitral Specification

## Purpose

O site estático da Comunidade Vitral apresenta o conteúdo institucional da igreja em uma arquitetura de 7 páginas + 404, no design "Vitral Arquitetônico", preservando fielmente os textos e dados institucionais, e é publicado via GitHub Pages (subpath `/comunidadevitral/`, branch `homologacao`).

## MODIFIED Requirements

### Requirement: Navegação entre as páginas

O site DEVE (MUST) exibir um cabeçalho fixo com o logotipo e o menu de navegação com as 7 páginas: Home, Quem Somos, Jornada, Encontros & PGs, Crianças & Família, Causas & Cidade e Contato. Todos os links internos DEVM (MUST) usar caminhos relativos para funcionar no subpath do GitHub Pages. Em telas estreitas (mobile), o menu DEVE (MUST) ser acessível via botão toggle com `aria-expanded` e `aria-controls`, e os itens DEVEM (MUST) ter alvos de toque de no mínimo 44px.

#### Scenario: Navegar do menu principal
- **WHEN** o usuário clica em "Quem Somos" no menu
- **THEN** a página `quem-somos.html` é aberta

#### Scenario: Abrir o menu no mobile
- **WHEN** o usuário toca no botão de menu em um dispositivo móvel
- **THEN** o menu é exibido com todos os itens acessíveis

### Requirement: SEO e metadados por página

Cada página DEVE (MUST) ter `<title>`, `<meta name="description">`, URL canônica, Open Graph (og:title, og:description, og:image, og:type, og:url), `twitter:card` e o idioma `lang="pt-BR"`. O site DEVE (MUST) incluir `sitemap.xml` (com as 7 URLs), `robots.txt`, `favicon.svg`, `assets/og-image.png` (1200x630) e, na HOME, o schema.org JSON-LD `Church` com `address`, `telephone` e `email`.

#### Scenario: Inspecionar metadados da HOME
- **WHEN** o usuário inspeciona o `<head>` da página inicial
- **THEN** ele encontra title, description, canônica, Open Graph, `twitter:card` e o JSON-LD `Church` com os dados de contato

#### Scenario: Consultar o sitemap
- **WHEN** um crawler acessa `/sitemap.xml`
- **THEN** as 7 URLs canônicas do site são listadas

### Requirement: Acessibilidade e responsividade

O site DEVE (MUST) ser mobile-first e acessível (WCAG 2.1 AA): navegação por teclado com foco visível, contraste mínimo 4.5:1, `prefers-reduced-motion` respeitado, skip-link para o conteúdo principal, imagens com atributo `alt` e alvos de toque de no mínimo 44px. O layout DEVE (MUST) se adaptar de telas de 320px a desktops, sem rolagem horizontal.

#### Scenario: Navegar por teclado
- **WHEN** o usuário usa Tab no site
- **THEN** o foco é visível e um link "Pular para o conteúdo" aparece

#### Scenario: Visualizar em telas pequenas
- **WHEN** o site é aberto em uma tela de 320px de largura
- **THEN** não há rolagem horizontal e o conteúdo permanece legível

## ADDED Requirements

### Requirement: Estrutura de 7 páginas com conteúdo preservado

O site DEVE (MUST) publicar 7 páginas + 404: HOME (`index.html`), Quem Somos (`quem-somos.html`), A Jornada & Trilha de Novos (`jornada.html`), Encontros & PGs (`encontros-e-pgs.html`), Crianças & Família (`criancas-e-familia.html`), Causas & Cidade (`causas-e-cidade.html`) e Contato (`contato.html`). O conteúdo de cada página DEVE (MUST) seguir a fonte da verdade em `docs/conteudo/novo/*.md` (a Home em `docs/conteudo/homepage.md`). Os dados institucionais DEVEM (MUST) estar corretos e visíveis no rodapé e na página de contato: telefone 17 99619-5302, e-mail contato@comunidadevitral.com.br, endereço "Avenida Sebastião Tavares da Silva, 1191 - Jardim Vista Alegre, São José do Rio Preto - SP - CEP 15061-660", CNPJ 49.075.286/0001-63, PIX financeiro@comunidadevitral.com.br e banco Itaú Ag 8299.

#### Scenario: Visualizar dados de contato na HOME
- **WHEN** o usuário acessa a página inicial
- **THEN** o telefone, e-mail e endereço da igreja são exibidos no rodapé

#### Scenario: Visualizar dados de contribuição na página de contato
- **WHEN** o usuário acessa a página "Contato"
- **THEN** os canais de contato, o endereço e os horários dos Encontros (domingos às 10h, café de acolhida 30 minutos antes) são exibidos

### Requirement: Contato e canais institucionais

O site DEVE (MUST) oferecer canais de contato direto: WhatsApp institucional (`https://wa.me/5517996195302`), e-mail `contato@comunidadevitral.com.br` e redes sociais (Instagram `@comunidadevitral`, YouTube, Facebook e Spotify). Links externos DEVEM (MUST) abrir em nova aba com `rel="noopener"`. O contato não usa formulário — apenas links diretos e mapa do Google com o endereço.

#### Scenario: Falar pelo WhatsApp
- **WHEN** o usuário clica em "Falar pelo WhatsApp"
- **THEN** uma nova aba abre em `https://wa.me/5517996195302`

#### Scenario: Abrir o mapa
- **WHEN** o usuário clica em "Abrir no Google Maps" na página de contato
- **THEN** uma nova aba abre o mapa do endereço da igreja

## REMOVED Requirements

### Requirement: Preservar o conteúdo institucional das 10 páginas

### Requirement: Redirecionar para serviços externos

### Requirement: Design Vitral contemporâneo
