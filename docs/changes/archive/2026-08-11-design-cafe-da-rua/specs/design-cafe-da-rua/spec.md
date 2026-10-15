# design-cafe-da-rua Specification

## Purpose

O site adota o mundo visual "O Café da Rua" na HOME: fachada de café com letreiro pintado à mão e lousa de giz, mantendo o conteúdo verbatim e a marca do vitral.

## ADDED Requirements

### Requirement: Mundo "Letreiros de Café do Interior"

A HOME DEVE (MUST) aplicar o mundo visual do café do interior paulista: fundos de pedra lavada e creme, marrom-café em painéis e rodapé, letreiro pintado à mão (Bree Serif) para convites, lousa de giz (Kalam) para informação prática e Archivo para o corpo. As quatro gemas do vitral (safira, esmeralda, âmbar, rubi) DEVEM (MUST) aparecer como tintas pintadas em doses, e o âmbar profundo `#a06a18` DEVE (MUST) ser usado nos CTAs com contraste AA.

#### Scenario: Verificar a paleta na HOME
- **WHEN** o usuário inspeciona os tokens usados pela HOME
- **THEN** encontra os fundos café/creme, o marrom-café e as gemas como acentos

#### Scenario: Renderizar um CTA
- **WHEN** um CTA primário é renderizado
- **THEN** usa o marrom-café/âmbar profundo com texto claro e contraste ≥ 4.5:1

### Requirement: Primeiro viewport com clareza do convite

O 1º viewport da HOME DEVE (MUST) apresentar a fachada do café: um letreiro pintado à mão com o convite ("Cansado de fingir? Puxe uma cadeira e respire fundo."), uma linha de lousa com a informação prática ("Domingos às 10h · café quentinho te espera."), a janela de vitral como vidro pintado da vitrine e o CTA primário visível. A HOME DEVE (MUST) evitar o padrão eyebrow/kicker acima de heading.

#### Scenario: Abrir a HOME
- **WHEN** o usuário acessa a página inicial
- **THEN** em segundos ele lê o convite pintado, a linha de lousa com horário/café e vê o CTA para visitar

### Requirement: Marca do vitral preservada

A janela de vitral (`assets/vitral.svg`) e a tira de 4 cores DEVEM (MUST) permanecer como identidade: a janela no hero como o vidro pintado da vitrine e a tira como divisor/porta.

#### Scenario: Conferir a janela de vitral
- **WHEN** o usuário vê o hero da HOME
- **THEN** a janela de vitral é exibida na moldura da vitrine

### Requirement: Conteúdo verbatim inalterado

O conteúdo da HOME DEVE (MUST) permanecer inalterado e fiel à fonte da verdade (`docs/conteudo/homepage.md`): textos, H2, dados institucionais (telefone 17 99619-5302, e-mail contato@comunidadevitral.com.br, endereço, CNPJ, PIX, Itaú), canais (WhatsApp `https://wa.me/5517996195302`) e horários (domingos às 10h, café 30 min antes).

#### Scenario: Conferir dados de contato
- **WHEN** o usuário inspeciona o rodapé da HOME
- **THEN** telefone, e-mail e endereço estão presentes e corretos

### Requirement: Acessibilidade e responsividade da HOME

A HOME DEVE (MUST) manter WCAG 2.1 AA: contraste ≥ 4.5:1 (giz sobre lousa, creme sobre café), navegação por teclado com foco visível, `prefers-reduced-motion` respeitado, imagens com `alt` e sem rolagem horizontal de 320px a desktops.

#### Scenario: Navegar por teclado
- **WHEN** o usuário usa Tab na HOME
- **THEN** o foco é visível e o link "Pular para o conteúdo" aparece

### Requirement: Escopo da rodada (só a HOME)

Esta rodada DEVE (MUST) aplicar o mundo "O Café da Rua" apenas à HOME (header/footer estilizados via `body.home`, markup inalterado). As subpáginas e a 404 DEVEM (MUST) permanecer no mundo anterior até a rodada de extensão.

#### Scenario: Abrir uma subpágina
- **WHEN** o usuário navega para `quem-somos.html`
- **THEN** a subpágina mantém o mundo visual anterior, sem regressão de conteúdo ou acessibilidade
