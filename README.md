# 🎵 Sonora FM - Backlog de Músicas e Álbuns

## 👤 Identificação / Autor
* **Nome:** João Victor ribeiro da Fonseca

---

## 📝 Descrição do Projeto
O **Sonora FM** é uma aplicação web responsiva projetada para amantes de música gerenciarem e avaliarem o seu histórico de escuta (backlog). A plataforma permite catalogar faixas e álbuns favoritos, atribuir pontuações em estrelas, guardar preferências localmente e explorar novas tendências musicais consumindo dados em tempo real através da API pública do Last.fm.

---

## 🎨 Design System e Protótipo
* **Protótipo no Stich AI:** https://stitch.withgoogle.com/projects/6264040318396843630
* **Design System (Tokens):** [Link para a documentação de Design Tokens no /docs/architecture.md ou Figma]
* **Framework CSS:** Bootstrap

---

## 🛠️ Tecnologias e Dependências
* **Estruturação:** HTML5 Semântico
* **Estilização:** Bootstrap
* **Lógica / DOM:** JavaScript Vanilla (ES6+)
* **Bibliotecas JS:** jQuery (com plugin de máscara/interatividade)
* **API Pública:** API REST do Last.fm (`chart.gettoptracks`, `track.search`, `tag.gettoptracks`)
* **API Fake / Persistência:** JSON Server & Web Storage (`localStorage`)

---

## 🚀 Link para o Site em Produção
* **GitHub Pages:** [https://seu-usuario.github.io/sonora-fm/](https://seu-usuario.github.io/sonora-fm/)

---


| Dashboard / Player | Library / Backlog | Discovery / Busca |
| :---: | :---: | :---: |
| ![Dashboard](docs/images/dashboard.png) | ![Library](docs/images/library.png) | ![Discovery](docs/images/discovery.png) |

---

## ⚙️ Instruções de Execução

### Pré-requisitos
* Node.js instalado (para execução da API Fake via JSON Server)
* Navegador web moderno

### Passos para rodar localmente
1. **Clonar o repositório:**
   ```bash
   git clone [https://github.com/seu-usuario/sonora-fm.git](https://github.com/seu-usuario/sonora-fm.git)
   cd sonora-fm

#### RA1 - Utilizar Frameworks CSS para estilização de elementos HTML e criação de layouts responsivos.

- [ ] ID 01 - Prototipa interfaces adaptáveis para no mínimo os tamanhos de tela mobile e desktop, usando ferramentas de design tradicionais (Figma, Quant UX ou Sketch) ou IA (Stitch).
- [ ] ID 02 - Implementa layout responsivo com Framework CSS (Bootstrap, Materialize, Tailwind + DaisyUI) usando Flexbox ou Grid do próprio framework.
- [ ] ID 03 - Implementa layout responsivo com CSS puro, usando Flexbox ou Grid Layout.
- [ ] ID 04 - Utiliza componentes prontos de um Framework CSS (ex.: card, button) e componentes JavaScript do framework (ex.: modal, carousel).
- [ ] ID 05 - Cria layout fluido usando unidades relativas (vw, vh, %, em, rem) no lugar de unidades fixas (px).
- [ ] ID 06 - Aplica um Design System consistente (cores, tipografia, padrões de componentes) em toda a aplicação.
- [ ] ID 07 - Utiliza Sass (SCSS) com ou sem framework, aplicando variáveis, mixins e funções para modularizar o código.
- [ ] ID 08 - Aplica tipografia responsiva (media queries mobile first) ou tipografia fluida (função clamp() + unidades relativas).
- [ ] ID 09 - Aplica técnicas de responsividade de imagens usando CSS (object-fit, containers com unidades relativas).
- [ ] ID 10 - Otimiza imagens usando formatos modernos (WebP) e carregamento adaptativo (srcset, picture, ou parâmetros do Cloudinary).

#### RA2 - Realizar tratamento de formulários e aplicar validações customizadas no lado cliente.

- [ ] ID 11 - Implementa validação HTML nativa (campos obrigatórios, tipos, limites de caracteres) com mensagens de erro/sucesso no lado cliente.
- [ ] ID 12 - Aplica expressões regulares (REGEX) para validações customizadas (e-mail, telefone, datas, etc.)
- [ ] ID 13 - Utiliza elementos de seleção em formulários (checkbox, radio, select) para coleta de dados.
- [ ] ID 14 - Implementa leitura e escrita no Web Storage (localStorage/sessionStorage) para persistir dados localmente.

#### RA3 - Aplicar ferramentas para otimização do processo de desenvolvimento web.

- [ ] ID 15 - Configura ambiente com Node.js e NPM para gerenciamento de pacotes e dependências.
- [ ] ID 16 - Utiliza boas práticas de versionamento no Git/GitHub (branch main ou branches específicos, uso de .gitignore).
- [ ] ID 17 - Mantém um README.md padronizado, conforme template da disciplina, com checklist preenchido.
- [ ] ID 18 - Organiza arquivos do projeto de forma modular, seguindo padrão de exemplo fornecido.
- [ ] ID 19 - Configura linters e formatadores (ESLint, Prettier) para manter qualidade e padronização do código.

#### RA4 - Aplicar bibliotecas de funções e componentes em JavaScript para aprimorar a interatividade de páginas web.

- [ ] ID 20 - Utiliza jQuery para manipulação do DOM e interatividade (eventos, animações, manipulação de elementos)
- [ ] ID 21 - Integra e configura um plugin jQuery relevante (ex.: jQuery Mask Plugin).

#### RA5 - Efetuar requisições assíncronas para uma API fake e APIs públicas, permitindo a obtenção e manipulação de dados dinamicamente.

- [ ] ID 22 - Realiza requisições assíncronas para uma API fake (ex.: JSON Server) para persistir dados de um formulário.
- [ ] ID 23 - Realiza requisições assíncronas para uma API fake para exibir dados na página.
- [ ] ID 24 - Realiza requisições assíncronas para APIs públicas reais (OpenWeather, ViaCEP etc.), exibindo os dados e tratando erros.
