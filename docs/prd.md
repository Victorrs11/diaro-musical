# Product Requirements Document (PRD) — Sonora FM

## 1. Identificação
* **Nome do Estudante:** João Victor Ribeiro da Fonseca
* **Nome do Projeto:** Sonora FM
* **Tema do Projeto:** Backlog e Avaliação de Músicas e Álbuns

---

## 2. Descrição e Propósito
O **Sonora FM** é uma plataforma web focada em atuar como um *backlog* pessoal e comunitário de música. 

### O Problema
Entusiastas de música frequentemente se esquecem de álbuns ou faixas que pretendiam ouvir, têm dificuldade em organizar as suas recomendações e não possuem um espaço simples e dedicado para catalogar impressões, notas e histórico do que já escutaram.

### A Solução
O Sonora FM resolve esse problema oferecendo uma plataforma onde os utilizadores podem pesquisar e cadastrar álbuns e músicas, marcá-los como "Quero Ouvir" ou "Ouvido", e atribuir notas de 1 a 5 estrelas acompanhadas de análises/resenhas.

---

## 3. Público-Alvo e Atores do Sistema

### Público-Alvo
* **Melômanos e Ouvintes Assíduos:** Pessoas que escutam música diariamente e gostam de acompanhar lançamentos, manter coleções e organizar o que já ouviram.
* **Criticos Amadores e Descobridores de Música:** Utilizadores que gostam de escrever opiniões sobre álbuns e descobrir novas recomendações com base nas avaliações da comunidade.

### Atores do Sistema
* **Visitante:** Utilizador não autenticado que navega pela plataforma para explorar o catálogo e ver avaliações públicas.
* **Utilizador Autenticado (Melômano):** Utilizador registado que gere o seu próprio backlog, cadastra álbuns/músicas e publica avaliações.
* **Administrador:** Responsável pela moderação de conteúdo (remoção de análises inadequadas) e manutenção do catálogo do sistema.

---

## 4. Escopo do Sistema
O escopo da versão inicial (MVP) contempla:
* Gestão de conta e perfis de utilizador.
* Catálogo de artistas, álbuns e faixas.
* Sistema de *Backlog* ("Quero Ouvir" vs. "Ouvido").
* Sistema de avaliação de 1 a 5 estrelas com comentários/resenhas.

---

## 5. Histórias de Utilizador (User Stories)

### 5.1. Autenticação e Perfil
* **HU01:** Como **Visitante**, quero **criar uma conta com nome, e-mail e palavra-passe**, para que **eu possa aceder a funcionalidades exclusivas como criar a minha coleção e avaliar obras**.
* **HU02:** Como **Utilizador Autenticado**, quero **efetuar login e logout com segurança**, para que **os meus dados e preferências fiquem salvos**.
* **HU03:** Como **Utilizador Autenticado**, quero **visualizar o meu perfil com o total de álbuns ouvidos e média das minhas notas**, para que **eu possa acompanhar o meu histórico musical**.

### 5.2. Gestão de Catálogo (Álbuns e Músicas)
* **HU04:** Como **Utilizador Autenticado**, quero **cadastrar um novo álbum informando título, artista, ano de lançamento e capa**, para que **ele fique disponível para mim e para a comunidade**.
* **HU05:** Como **Utilizador Autenticado**, quero **cadastrar faixas vinculadas a um álbum**, para que **seja possível visualizar a lista de faixas completa**.
* **HU06:** Como **Visitante/Utilizador Autenticado**, quero **pesquisar álbuns e músicas por título ou artista**, para que **eu encontre rapidamente a obra que desejo consultar ou avaliar**.

### 5.3. Backlog e Avaliação
* **HU07:** Como **Utilizador Autenticado**, quero **avaliar um álbum ou música com uma nota de 1 a 5 estrelas**, para que **eu registre a minha opinião sobre a obra**.
* **HU08:** Como **Utilizador Autenticado**, quero **escrever um comentário opcional ao avaliar uma obra**, para que **eu possa detalhar a minha experiência sonora**.
* **HU09:** Como **Utilizador Autenticado**, quero **adicionar um álbum à minha lista de "Quero Ouvir" (Backlog)**, para que **eu me lembre de o escutar no futuro**.
* **HU10:** Como **Utilizador Autenticado**, quero **marcar um álbum como "Ouvido"**, para que **ele seja movido da lista de pendências para o meu histórico**.


---

## 6. Regras de Negócio (RN)

* **RN01 — Unicidade de Avaliação:** Um utilizador só pode submeter **uma única avaliação (nota/comentário)** por álbum ou música. Caso avalie novamente, a avaliação anterior deve ser atualizada.
* **RN02 — Escala de Avaliação:** A nota de avaliação deve ser estritamente um valor inteiro entre **1 e 5 estrelas**.
* **RN03 — Transição de Status no Backlog:** Ao avaliar um álbum que está marcado como "Quero Ouvir", o sistema deve alterar automaticamente o status desse item para "Ouvido".
* **RN04 — Unicidade de E-mail:** Não é permitido o cadastro de mais de uma conta com o mesmo endereço de e-mail.
* **RN05 — Proteção de Dados:** A palavra-passe do utilizador deve ser armazenada de forma encriptada (hash) na base de dados.
* **RN06 — Permissão de Edição e Remoção de Conteúdo:** * Um utilizador só pode editar ou eliminar as **suas próprias** avaliações e itens de backlog.
  * Um utilizador só pode editar ou eliminar as **suas próprias** avaliações e itens de backlog.

