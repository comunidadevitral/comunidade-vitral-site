# Comunidade Vitral — Site Estático

> Novo site estático da **Comunidade Vitral** (Igreja Presbiteriana Independente Vitral), em substituição ao site em Wix. Todo o site — HOME, subpáginas e 404 — usa a identidade **"Marca Nova"** (verde petróleo/verde acinzentado e Montserrat), com o emblema oficial da marca no hero e a tira de 4 cores no rodapé.

---

## 📋 Sumário

- [Visão geral](#visão-geral)
- [Tecnologias](#tecnologias)
- [Estrutura do projeto](#estrutura-do-projeto)
- [Como rodar localmente](#como-rodar-localmente)
- [Como contribuir](#como-contribuir)
- [Licença](#licença)
- [Contato](#contato)

---

## 🎯 Visão geral

Este repositório contém o código-fonte do site oficial da Comunidade Vitral, um projeto **estático** (HTML5 + CSS puro, sem build step) publicado via **GitHub Pages** (branch `homologacao`).  
A identidade visual "Marca Nova" é aplicada uniformemente em todas as páginas, garantindo consistência e acessibilidade (WCAG 2.1 AA).

**URL pública**: https://comunidadevitral.com.br  
**Versão atual**: v3.0.1  
**Branch de trabalho**: `homologacao`  
**Branch de produção**: `main` (atualizada via push de `homologacao`)

---

## 🛠️ Tecnologias

- **HTML5** – estrutura semântica
- **CSS puro** – variáveis de design em `css/tokens.css` (paleta Marca Nova)
- **JavaScript mínimo** – `js/menu.js` (menu mobile)
- **Fonte**: Montserrat (via Google Fonts)
- **Imagens**: formato WebP, com `loading="lazy"` onde apropriado
- **Meta tags**: SEO, Open Graph, Twitter Cards, schema.org
- **Hospedagem**: GitHub Pages (branch `homologacao`)

---

## 📁 Estrutura do projeto

```
.
├── 404.html
├── index.html
├── quem-somos.html
├── no-que-cremos.html
├── jornada.html
├── grande-banquete.html
├── encontros-e-pgs.html
├── criancas-e-familia.html
├── causas-e-cidade.html
├── contato.html
├── assets/
│   ├── img/          # fotografias (WebP)
│   └── logos/        # logotipos e ícones
├── css/
│   ├── tokens.css    # design tokens (Marca Nova)
│   ├── base.css      # reset e utilitários
│   └── estilo.css    # estilos específicos
├── js/
│   └── menu.js       # toggle do menu mobile
├── docs/
│   ├── conteudo/                 # fonte da verdade do conteúdo
│   │   ├── homepage.md           # conteúdo da HOME
│   │   └── novo/                 # demais páginas (markdown)
│   ├── agents/                   # configurações de habilidades de agente (Matt Pocock)
│   ├── specs/                    # especificações spec-driven
│   │   ├── config.yaml
│   │   ├── marca-nova.md
│   │   └── site-estatico-vitral.md
│   └── changes/                  # histórico de mudanças (archive)
│       └── archive/              # diretórios de changes por data
├── docs_old/                     # material histórico/referência (não usado em produção)
└── .scratch/                     # issue tracker local (markdown)
```

---

## ▶️ Como rodar localmente

Como o site é totalmente estático, basta abrir qualquer arquivo HTML diretamente no navegador:

```bash
# exemplo
open index.html   # macOS
xdg-open index.html # Linux
start index.html  # Windows
```

Não é necessário instalar dependências ou rodar um servidor de desenvolvimento. (Se desejar, pode usar `python3 -m http.server` ou qualquer servidor estático simples.)

---

## 🤝 Como contribuir

1. **Fork** este repositório.
2. Crie uma **branch** a partir de `homologacao` para sua feature ou correção:
   ```bash
   git checkout -b minha-feature homologacao
   ```
3. Faça suas alterações, respeitando as convenções do projeto:
   - Mantenha o conteúdo em `docs/conteudo/novo/` (markdown) – fonte da verdade.
   - Atualize apenas os arquivos HTML/CSS/JS necessários; lembre-se de que o header e footer são duplicados em todas as páginas.
   - Não use build step ou dependências de runtime.
4. Commit com mensagem clara no padrão:
   ```
   tipo(scope): descrição
   ```
   Exemplo: `docs(conteudo): atualiza texto da página Sobre`.
5. Push para sua fork e abra um **Pull Request** para a branch `homologacao` deste repositório.
6. Após revisão e aprovação, o maintainer fará o merge e fará o push para `main` (produção) quando apropriado.

> **Nota**: a branch `main` é usada apenas para deploys explícitos. O workflow padrão é: desenvolver em `homologacao`, testar, então `push origin homologacao:main` para publicar.

---

## 📄 Licença

Este projeto está licenciado sob a [Licença MIT](LICENSE) – veja o arquivo `LICENSE` para mais detalhes.

---

## 📞 Contato

- **E-mail**: contato@comunidadevitral.com.br
- **WhatsApp**: https://wa.me/5517996195302
- **Endereço**: Avenida Sebastião Tavares da Silva, 1191 - Jardim Vista Alegre, São José do Rio Preto - SP - CEP 15061-660
- **Redes sociais**:
  - Instagram: @comunidadevitral
  - YouTube: Canal Comunidade Vitral
  - Facebook: Comunidade Vitral
  - Spotify: show/1prjsrcxPho9otrP1VUWT4

---

*Atualizado em: $(date '+%Y-%m-%d')*