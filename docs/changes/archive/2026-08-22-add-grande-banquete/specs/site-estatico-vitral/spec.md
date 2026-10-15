## RENAMED Requirements

- FROM: `### Requirement: Estrutura de 7 páginas com conteúdo preservado`
- TO: `### Requirement: Estrutura de 8 páginas com conteúdo preservado`

## MODIFIED Requirements

### Requirement: Estrutura de 8 páginas com conteúdo preservado

O site DEVE (MUST) publicar 8 páginas + 404: HOME (`index.html`), Quem Somos (`quem-somos.html`), A Jornada & Trilha de Novos (`jornada.html`), O Grande Banquete (`grande-banquete.html`), Encontros & PGs (`encontros-e-pgs.html`), Crianças & Família (`criancas-e-familia.html`), Causas & Cidade (`causas-e-cidade.html`) e Contato (`contato.html`). O conteúdo de cada página DEVE (MUST) seguir a fonte da verdade em `docs/conteudo/novo/*.md` (a Home em `docs/conteudo/homepage.md`). Os dados institucionais DEVEM (MUST) estar corretos e visíveis no rodapé e na página de contato: telefone 17 99619-5302, e-mail contato@comunidadevitral.com.br, endereço "Avenida Sebastião Tavares da Silva, 1191 - Jardim Vista Alegre, São José do Rio Preto - SP - CEP 15061-660", CNPJ 49.075.286/0001-63, PIX financeiro@comunidadevitral.com.br e banco Itaú Ag 8299.

#### Scenario: Visualizar dados de contato na HOME
- **WHEN** o usuário acessa a página inicial
- **THEN** o telefone, e-mail e endereço da igreja são exibidos no rodapé

#### Scenario: Visualizar dados de contribuição na página de contato
- **WHEN** o usuário acessa a página "Contato"
- **THEN** os canais de contato, o endereço e os horários dos Encontros (domingos às 10h, café de acolhida 30 minutos antes) são exibidos

#### Scenario: Acessar a página do Grande Banquete
- **WHEN** o usuário acessa `grande-banquete.html`
- **THEN** a página é exibida no sistema visual Marca Nova, com conteúdo conforme `docs/conteudo/novo/grande_banquete.md`

### Requirement: Navegação entre as páginas

O site DEVE (MUST) exibir um cabeçalho fixo com o logotipo e o menu de navegação com as 8 páginas: Home, Quem Somos, Jornada, Grande Banquete, Encontros & PGs, Crianças & Família, Causas & Cidade e Contato. Todos os links internos DEVM (MUST) usar caminhos relativos para funcionar no subpath do GitHub Pages. Em telas estreitas (mobile), o menu DEVE (MUST) ser acessível via botão toggle com `aria-expanded` e `aria-controls`, e os itens DEVEM (MUST) ter alvos de toque de no mínimo 44px.

#### Scenario: Navegar do menu principal
- **WHEN** o usuário clica em "Quem Somos" no menu
- **THEN** a página `quem-somos.html` é aberta

#### Scenario: Abrir o menu no mobile
- **WHEN** o usuário toca no botão de menu em um dispositivo móvel
- **THEN** o menu é exibido com todos os itens acessíveis

#### Scenario: Localizar o item do Grande Banquete no menu
- **WHEN** o usuário visualiza o menu em qualquer página
- **THEN** o item "Grande Banquete" aparece imediatamente após "Jornada"

### Requirement: SEO e metadados por página

Cada página DEVE (MUST) ter `<title>`, `<meta name="description">`, URL canônica, Open Graph (og:title, og:description, og:image, og:type, og:url), `twitter:card` e o idioma `lang="pt-BR"`. O site DEVE (MUST) incluir `sitemap.xml` (com as 8 URLs), `robots.txt`, `favicon.svg`, `assets/og-image.png` (1200x630) e, na HOME, o schema.org JSON-LD `Church` com `address`, `telephone` e `email`.

#### Scenario: Inspecionar metadados da HOME
- **WHEN** o usuário inspeciona o `<head>` da página inicial
- **THEN** ele encontra title, description, canônica, Open Graph, `twitter:card` e o JSON-LD `Church` com os dados de contato

#### Scenario: Consultar o sitemap
- **WHEN** um crawler acessa `/sitemap.xml`
- **THEN** as 8 URLs canônicas do site são listadas

## ADDED Requirements

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
