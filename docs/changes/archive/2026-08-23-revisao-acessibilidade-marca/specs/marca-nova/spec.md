## MODIFIED Requirements

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
