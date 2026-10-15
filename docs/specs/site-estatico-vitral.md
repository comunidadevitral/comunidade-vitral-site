# site-estatico-vitral Specification

## Purpose

O site estático da Comunidade Vitral apresenta o conteúdo institucional da igreja em uma arquitetura de 9 páginas + 404, no design "Marca Nova" (verde petróleo/verde acinzentado, Montserrat), preservando fielmente os textos e dados institucionais, e é publicado via GitHub Pages (subpath `/comunidadevitral/`, branch `homologacao`).

## Requirements

### Requirement: Estrutura de 9 páginas com conteúdo preservado

O site DEVE (MUST) publicar 9 páginas + 404: HOME (`index.html`), Quem Somos (`quem-somos.html`), No Que Cremos (`no-que-cremos.html`), A Jornada & Trilha de Novos (`jornada.html`), O Grande Banquete (`grande-banquete.html`), Encontros & PGs (`encontros-e-pgs.html`), Crianças & Família (`criancas-e-familia.html`), Causas & Cidade (`causas-e-cidade.html`) e Contato (`contato.html`). O conteúdo de cada página DEVE (MUST) seguir a fonte da verdade em `docs/conteudo/novo/*.md` (a Home em `docs/conteudo/homepage.md`). Os dados institucionais DEVEM (MUST) estar corretos e visíveis no rodapé e na página de contato: telefone 17 99619-5302, e-mail contato@comunidadevitral.com.br, endereço "Avenida Sebastião Tavares da Silva, 1191 - Jardim Vista Alegre, São José do Rio Preto - SP - CEP 15061-660", CNPJ 49.075.286/0001-63, PIX financeiro@comunidadevitral.com.br e banco Itaú Ag 8299.

#### Scenario: Visualizar dados de contato na HOME
- **WHEN** o usuário acessa a página inicial
- **THEN** o telefone, e-mail e endereço da igreja são exibidos no rodapé

#### Scenario: Visualizar dados de contribuição na página de contato
- **WHEN** o usuário acessa a página "Contato"
- **THEN** os canais de contato, o endereço e os horários dos Encontros (domingos às 10h, café de acolhida 30 minutos antes) são exibidos

#### Scenario: Acessar a página do Grande Banquete
- **WHEN** o usuário acessa `grande-banquete.html`
- **THEN** a página é exibida no sistema visual Marca Nova, com conteúdo conforme `docs/conteudo/novo/grande_banquete.md`

### Requirement: Página O Grande Banquete

O site DEVE (MUST) apresentar a página `grande-banquete.html` descrevendo a experiência imersiva de 72 horas (de quinta-feira à noite a domingo) inspirada em Lucas 14.15-24, posicionada como complemento da Jornada do Discípulo — sem substituí-la — e com tom de mesa aberta, acolhimento, descanso e renovação espiritual. A página DEVE (MUST) explicar a participação por apadrinhamento (um membro que já viveu a experiência caminha com o convidado), NÃO DEVE (MUST NOT) usar emojis nem tom secreto/burocrático, e DEVE (MUST) direcionar os CTAs ao WhatsApp institucional (`https://wa.me/5517996195302`, nova aba com `rel="noopener"`) e à página `jornada.html`. A página DEVE (MUST) usar terminologia oficial da Vitral ("Trilha de Novos", "Pequenos Grupos (PGs)", "os 4 Times de Servidores (Mordomos)") e citar apenas fatos verificáveis, sem inventar datas, números ou depoimentos.

#### Scenario: Entender o que é o Grande Banquete
- **WHEN** o usuário abre a seção inicial da página
- **THEN** encontra a duração de 72 horas (quinta à noite a domingo), a referência bíblica Lucas 14.15-24 e as raízes históricas (Cursilho, Caminhada para Emaús, desenvolvimento presbiteriano de 1982)

#### Scenario: Compreender o apadrinhamento
- **WHEN** o usuário lê a seção sobre participação
- **THEN** entende que a inscrição acontece por meio de um padrinho/membro da comunidade que caminha com ele, faz a indicação e apoia a família durante o fim de semana

#### Scenario: Acionar o contato pelo WhatsApp
- **WHEN** o usuário clica no botão principal "Quero falar com um padrinho no WhatsApp"
- **THEN** uma nova aba abre `https://wa.me/5517996195302` com `rel="noopener"`

#### Scenario: Seguir para a Jornada do Discípulo
- **WHEN** o usuário clica no botão secundário "Conhecer a Trilha de Novos"
- **THEN** é levado à página `jornada.html`

#### Scenario: Descobrir a página pela Jornada e pela HOME
- **WHEN** o usuário navega na HOME ou na página Jornada
- **THEN** encontra um bloco/convite visível linkando `grande-banquete.html`

### Requirement: Contato e canais institucionais

O site DEVE (MUST) oferecer canais de contato direto: WhatsApp institucional (`https://wa.me/5517996195302`), e-mail `contato@comunidadevitral.com.br` e redes sociais (Instagram `@comunidadevitral`, YouTube, Facebook e Spotify). Links externos DEVEM (MUST) abrir em nova aba com `rel="noopener"`. O contato não usa formulário — apenas links diretos e mapa do Google com o endereço.

#### Scenario: Falar pelo WhatsApp
- **WHEN** o usuário clica em "Falar pelo WhatsApp"
- **THEN** uma nova aba abre em `https://wa.me/5517996195302`

#### Scenario: Abrir o mapa
- **WHEN** o usuário clica em "Abrir no Google Maps" na página de contato
- **THEN** uma nova aba abre o mapa do endereço da igreja

### Requirement: Navegação entre as páginas

O site DEVE (MUST) exibir um cabeçalho fixo com o logotipo e o menu de navegação com as 9 páginas: Home, Quem Somos, No Que Cremos, Jornada, Grande Banquete, Encontros & PGs, Crianças & Família, Causas & Cidade e Contato. Todos os links internos DEVM (MUST) usar caminhos relativos para funcionar no subpath do GitHub Pages. Em telas estreitas (≤760px), o menu DEVE (MUST) abrir como drawer em tela cheia com os links empilhados, alvos de toque de no mínimo 48px de altura, fechamento por tecla Esc, clique fora ou seleção de link, trava da rolagem do fundo enquanto aberto e devolução do foco ao botão Menu ao fechar; o botão toggle DEVE (MUST) manter `aria-expanded` e `aria-controls`.

#### Scenario: Navegar do menu principal
- **WHEN** o usuário clica em "Quem Somos" no menu
- **THEN** a página `quem-somos.html` é aberta

#### Scenario: Abrir o menu no mobile
- **WHEN** o usuário toca no botão de menu em um dispositivo móvel
- **THEN** o drawer é exibido em tela cheia com todos os itens acessíveis e alvos de toque de no mínimo 48px

#### Scenario: Localizar o item do Grande Banquete no menu
- **WHEN** o usuário visualiza o menu em qualquer página
- **THEN** o item "Grande Banquete" aparece imediatamente após "Jornada"

#### Scenario: Fechar o drawer pelo teclado
- **WHEN** o drawer está aberto e o usuário pressiona Esc
- **THEN** o drawer fecha, a rolagem do fundo é restaurada e o foco retorna ao botão Menu

### Requirement: SEO e metadados por página

Cada página DEVE (MUST) ter `<title>`, `<meta name="description">`, URL canônica, Open Graph (og:title, og:description, og:image, og:type, og:url), `twitter:card` e o idioma `lang="pt-BR"`. O site DEVE (MUST) incluir `sitemap.xml` (com as 8 URLs), `robots.txt`, `favicon.svg`, `assets/og-image.png` (1200x630) e, na HOME, o schema.org JSON-LD `Church` com `address`, `telephone` e `email`.

#### Scenario: Inspecionar metadados da HOME
- **WHEN** o usuário inspeciona o `<head>` da página inicial
- **THEN** ele encontra title, description, canônica, Open Graph, `twitter:card` e o JSON-LD `Church` com os dados de contato

#### Scenario: Consultar o sitemap
- **WHEN** um crawler acessa `/sitemap.xml`
- **THEN** as 8 URLs canônicas do site são listadas

### Requirement: Performance de mídia

O site DEVE (MUST) servir fotografias no formato WebP mantendo as dimensões originais dos arquivos mestre preservados no repositório. As imagens abaixo da primeira dobra DEVEM (MUST) usar `loading="lazy"`; as imagens de conteúdo DEVEM (MUST) declarar `width` e `height` explícitos para evitar deslocamento de layout (CLS). O conjunto de imagens convertidas DEVE (MUST) somar menos de 2 MB.

#### Scenario: Carregar uma página por conexão móvel
- **WHEN** um visitante abre qualquer página em rede 3G/4G
- **THEN** as imagens são servidas em WebP, carregam sob demanda conforme a rolagem e a página não apresenta salto de layout durante o carregamento

### Requirement: Localização prática na HOME

A HOME DEVE (MUST) apresentar, na seção de convite, um bloco prático "onde e quando" com o horário dos Encontros (domingos às 10h), o endereço da comunidade e botões diretos de rota — "Traçar rota no Google Maps" (`google.com/maps`) e "Abrir no Waze" (`waze.com/ul`) — abrindo em nova aba com `rel="noopener"`.

#### Scenario: Traçar rota até o Encontro
- **WHEN** o visitante clica em "Traçar rota no Google Maps" ou "Abrir no Waze"
- **THEN** uma nova aba abre o aplicativo correspondente apontando para Avenida Sebastião Tavares da Silva, 1191, São José do Rio Preto - SP

### Requirement: Acessibilidade e responsividade

O site DEVE (MUST) ser mobile-first e acessível (WCAG 2.1 AA): navegação por teclado com foco visível em QUALQUER superfície (o indicador de foco DEVE (MUST) ter contraste mínimo de 3:1 contra o fundo sobre o qual aparece, inclusive gradientes e seções escuras), contraste mínimo 4.5:1 para texto corrente, `prefers-reduced-motion` respeitado, skip-link para o conteúdo principal, imagens com atributo `alt` e alvos de toque de no mínimo 44px (incluídos os ícones de redes sociais). Ao abrir o menu mobile, o foco do teclado DEVE (MUST) ficar contido entre o botão de menu e os itens do menu, e todo caminho de fechamento DEVE (MUST) devolver o foco ao botão de menu. Âncoras internas acessadas por link ou teclado NÃO DEVE (MUST NOT) ficar encobertas pelo header fixo. O layout DEVE (MUST) se adaptar de telas de 320px a desktops, sem rolagem horizontal.

#### Scenario: Navegar por teclado
- **WHEN** o usuário usa Tab no site
- **THEN** o foco é visível e um link "Pular para o conteúdo" aparece

#### Scenario: Focar um CTA sobre superfície escura
- **WHEN** o usuário navega por teclado até um botão dentro de banner, seção escura ou card escuro
- **THEN** o indicador de foco é claramente distinguível do fundo (contraste ≥ 3:1)

#### Scenario: Circular no menu mobile aberto
- **WHEN** o menu mobile está aberto e o usuário pressiona Tab repetidamente
- **THEN** o foco circula apenas entre o botão de menu e os itens do menu

#### Scenario: Fechar o drawer pelo teclado
- **WHEN** o usuário fecha o menu mobile (Escape ou clique fora)
- **THEN** o foco retorna ao botão de menu

#### Scenario: Seguir uma âncora interna
- **WHEN** o usuário ativa um link que aponta para uma âncora na mesma página
- **THEN** o destino fica totalmente visível, não escondido sob o header fixo

#### Scenario: Visualizar em telas pequenas
- **WHEN** o site é aberto em uma tela de 320px de largura
- **THEN** não há rolagem horizontal e o conteúdo permanece legível

### Requirement: Gramática de chamada para ação

Cada bloco de convite DEVE (MUST) apresentar no máximo um botão primário, sem pares de botões lado a lado apontando para o mesmo destino. O mesmo rótulo de ação DEVE (MUST) levar sempre ao mesmo destino em todas as páginas do site.

#### Scenario: Ler um bloco de convite
- **WHEN** o usuário examina o bloco de convite final de qualquer página
- **THEN** existe um único botão primário e nenhum par de botões com destino idêntico

#### Scenario: Comparar o mesmo rótulo entre páginas
- **WHEN** o mesmo rótulo de botão aparece em páginas diferentes
- **THEN** ele leva ao mesmo destino em todas elas
