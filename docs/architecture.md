# Especificação Técnica e Arquitetura — Sonora FM

## 1. Visão Geral da Arquitetura
O **Sonora FM** segue o padrão de arquitetura em camadas (ou Web/API desacoplada/Monólito com divisão clara de responsabilidades), separando a interface do usuário, as regras de negócio e a persistência de dados.

* **Frontend:** Interface Web dinâmica responsável pela navegação, formulários de cadastro, exibição dos álbuns, busca e componente interativo de avaliação (1 a 5 estrelas), estilizada com base nos tokens do **Design System (Digital Synth)**.
* **Backend / API:** Camada responsável por autenticação, regras de negócio (cálculo de médias de avaliação, movimentação de itens no backlog) e disponibilização de rotas CRUD.
* **Banco de Dados / Persistência:** Armazenamento relacional dos dados de usuários, artistas, álbuns, músicas, histórico de status e avaliações.

---

## 2. Design System & Tokens Visuais (Digital Synth)

A interface da aplicação adota o tema **Digital Synth**, com um visual dark moderno inspirado em sintetizadores e equipamentos de áudio[cite: 1].

### 2.1. Cores (Color Tokens)
* **Primary (Roxo / Lavanda principal):** `#7E5CEF`[cite: 1]
  * *Uso:* Botões principais, estados ativos, destaques da marca e badges[cite: 1].
* **Secondary (Azul pastel / Periwinkle):** `#A6B1EC`[cite: 1]
  * *Uso:* Elementos secundários, bordas interativas, ícones e estados de hover[cite: 1].
* **Tertiary (Amarelo suave / Cream):** `#FFF7B4`[cite: 1]
  * *Uso:* Avaliações (estrelas de 1 a 5), avisos e elementos de destaque especial[cite: 1].
* **Neutral (Cinza claro):** `#DADADA`[cite: 1]
  * *Uso:* Textos de corpo, rótulos e bordas neutras em superfícies escuras[cite: 1].
* **Background & Surfaces (Tema Dark):**
  * **Dark Canvas:** `#121214` (Fundo principal da aplicação)[cite: 1]
  * **Dark Card / Surface:** `#1E1E22` (Superfície dos cards de álbuns, campos de busca e modais)[cite: 1]

### 2.2. Tipografia (Typography Tokens)
* **Headline / Títulos:** `Outfit`[cite: 1]
  * *Uso:* Títulos de páginas, nomes de álbuns e nomes de artistas[cite: 1].
* **Body / Corpo de Texto:** `JetBrains Mono`[cite: 1]
  * *Uso:* Resenhas/comentários, metadados (duração, ano), estatísticas e detalhes técnicos[cite: 1].
* **Label / Rótulos e Botões:** `Comfortaa`[cite: 1]
  * *Uso:* Botões, tags, labels de formulários e elementos de navegação[cite: 1].

### 2.3. Componentes Visuais
* **Botões:** `Primary`, `Secondary`, `Inverted` e `Outlined`[cite: 1].
* **Campos de Entrada (Inputs/Search):** Fundo escuro arredondado (`#1E1E22`), bordas sutis e ícone de busca em tom neutro[cite: 1].
* **Arredondamento (Border Radius):**
  * Cards: `12px` a `16px`[cite: 1]
  * Botões / Inputs: `8px` a `20px`[cite: 1]

---

## 3. Modelo de Dados (Diagrama ER — Mermaid)

O diagrama abaixo descreve as entidades do sistema e como elas se relacionam para suportar as funcionalidades do backlog e avaliações do Sonora FM.

```mermaid
erDiagram
    USUARIO ||--o{ AVALIACAO : "escreve"
    USUARIO ||--o{ ITEM_BACKLOG : "gerencia"
    ARTISTA ||--o{ ALBUM : "possui"
    ALBUM ||--o{ MUSICA : "contém"
    ALBUM ||--o{ AVALIACAO : "recebe"
    ALBUM ||--o{ ITEM_BACKLOG : "está em"
    MUSICA ||--o{ AVALIACAO : "recebe"

    USUARIO {
        int id PK
        string nome
        string email
        string senha_hash
        string perfil_role "CLIENTE / ADMIN"
        datetime criado_em
    }

    ARTISTA {
        int id PK
        string nome
        string genero
        string foto_url
    }

    ALBUM {
        int id PK
        int artista_id FK
        string titulo
        int ano_lancamento
        string capa_url
    }

    MUSICA {
        int id PK
        int album_id FK
        string titulo
        int duracao_segundos
        int numero_faixa
    }

    AVALIACAO {
        int id PK
        int usuario_id FK
        int album_id FK "Opcional"
        int musica_id FK "Opcional"
        int nota "1 a 5"
        text comentario
        datetime data_avaliacao
    }

    ITEM_BACKLOG {
        int id PK
        int usuario_id FK
        int album_id FK
        string status "QUERO_OUVIR / OUVIDO"
        datetime adicionado_em
        datetime atualizado_em
    }
