## MODIFIED Requirements

### Requirement: Navegação entre as páginas

O site DEVE (MUST) exibir um cabeçalho fixo com o logotipo e o menu de navegação com as 8 páginas: Home, Quem Somos, Jornada, Grande Banquete, Encontros & PGs, Crianças & Família, Causas & Cidade e Contato. Todos os links internos DEVM (MUST) usar caminhos relativos para funcionar no subpath do GitHub Pages. Em telas estreitas (≤760px), o menu DEVE (MUST) abrir como drawer em tela cheia com os links empilhados, alvos de toque de no mínimo 48px de altura, fechamento por tecla Esc, clique fora ou seleção de link, trava da rolagem do fundo enquanto aberto e devolução do foco ao botão Menu ao fechar; o botão toggle DEVE (MUST) manter `aria-expanded` e `aria-controls`.

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

## ADDED Requirements

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
