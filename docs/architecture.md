# Especificação Técnica e Arquitetura — Sonora FM

## 1. Visão Geral da Arquitetura
O **Sonora FM** segue o padrão de arquitetura em camadas (ou Web/API desacoplada/Monólito com divisão clara de responsabilidades), separando a interface do usuário, as regras de negócio e a persistência de dados.

* **Frontend:** Interface Web responsável pela navegação, formulários de cadastro, exibição dos álbuns, busca e componente interativo de avaliação (1 a 5 estrelas).
* **Backend / API:** Camada responsável por autenticação, regras de negócio (cálculo de médias de avaliação, movimentação de itens no backlog) e disponibilização de rotas CRUD.
* **Banco de Dados / Persistência:** Armazenamento relacional dos dados de usuários, artistas, álbuns, músicas, histórico de status e avaliações.

---

## 2. Modelo de Dados (Diagrama ER — Mermaid)

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
