## MODIFIED Requirements

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

## ADDED Requirements

### Requirement: Gramática de chamada para ação

Cada bloco de convite DEVE (MUST) apresentar no máximo um botão primário, sem pares de botões lado a lado apontando para o mesmo destino. O mesmo rótulo de ação DEVE (MUST) levar sempre ao mesmo destino em todas as páginas do site.

#### Scenario: Ler um bloco de convite
- **WHEN** o usuário examina o bloco de convite final de qualquer página
- **THEN** existe um único botão primário e nenhum par de botões com destino idêntico

#### Scenario: Comparar o mesmo rótulo entre páginas
- **WHEN** o mesmo rótulo de botão aparece em páginas diferentes
- **THEN** ele leva ao mesmo destino em todas elas
