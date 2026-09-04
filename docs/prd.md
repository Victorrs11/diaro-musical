# Product Requirements Document (PRD) — Sonora FM

## 1. Identificação
* **Nome do Estudante:** João Victor Ribeiro da Fonseca
* **Nome do Projeto:** Sonora FM
* **Tema do Projeto:** Backlog e Avaliação de Músicas e Álbums

---

## 2. Descrição e Propósito
O **Sonora FM** é um sistema web focado em atuar como um *backlog* pessoal e comunitário de música. 

### O Problema
Entusiastas de música frequentemente se esquecem dos álbuns ou faixas que já ouviram, têm dificuldade em organizar suas recomendações ou não possuem um espaço simples para catalogar suas impressões e notas sobre suas obras musicais favoritas (ou esquecíveis).

### A Solução
O Sonora FM resolve esse problema oferecendo uma plataforma onde usuários podem cadastrar álbuns e músicas, marcá-los como ouvidos ou "para ouvir", e atribuir notas de 1 a 5 estrelas acompanhadas de breves resenhas.

---

## 3. Atores do Sistema
* **Visitante:** Usuário não autenticado que navega pela plataforma para conhecer o catálogo e ver avaliações públicas.
* **Usuário Autenticado (Melômano):** Usuário registrado que pode gerenciar seu próprio backlog, cadastrar músicas/álbuns e emitir avaliações.
* **Administrador:** Responsável pela moderação de conteúdo (remoção de conteúdos inadequados) e gestão da base de dados do sistema.

---

## 4. Histórias de Usuário (Escopo)

### 4.1. Autenticação e Perfil
* **HU01:** Como **Visitante**, eu quero **me cadastrar na plataforma fornecendo nome, e-mail e senha**, para que **eu possa criar meu perfil e salvar minhas avaliações**.
* **HU02:** Como **Usuário Autenticado**, eu quero **fazer login e logout da minha conta**, para que **eu possa acessar meu acervo com segurança**.
* **HU03:** Como **Usuário Autenticado**, eu quero **visualizar meu perfil com o resumo de álbuns ouvidos e média de notas**, para que **eu possa acompanhar minhas estatísticas musicais**.

### 4.2. Gestão de Catálogo (Álbuns e Músicas)
* **HU04:** Como **Usuário Autenticado**, eu quero **cadastrar um novo álbum informando título, artista, ano de lançamento e capa**, para que **ele fique disponível para avaliação no sistema**.
* **HU05:** Como **Usuário Autenticado**, eu quero **cadastrar uma nova música vinculada a um álbum ou artista**, para que **eu possa avaliar faixas individuais**.
* **HU06:** Como **Visitante/Usuário Autenticado**, eu quero **buscar álbuns ou músicas por nome ou artista**, para que **eu encontre rapidamente o que desejo avaliar ou consultar**.

### 4.3. Backlog e Avaliação
* **HU07:** Como **Usuário Autenticado**, eu quero **avaliar um álbum ou música com uma nota de 1 a 5 estrelas**, para que **eu possa registrar minha opinião sobre a obra**.
* **HU08:** Como **Usuário Autenticado**, eu quero **escrever um comentário/resenha opcional ao avaliar uma obra**, para que **eu possa detalhar o que achei da experiência sonora**.
* **HU09:** Como **Usuário Autenticado**, eu quero **adicionar um álbum à minha lista de "Quero Ouvir" (Backlog)**, para que **eu lembre de escutá-lo no futuro**.
* **HU10:** Como **Usuário Autenticado**, eu quero **marcar um álbum como "Ouvido"**, para que **ele saia da lista de pendências e vá para o meu histórico**.

### 4.4. Administração e Moderação
* **HU11:** Como **Administrador**, eu quero **editar ou excluir cadastros de álbuns/músicas duplicados ou incorretos**, para que **o catálogo se mantenha organizado**.
* **HU12:** Como **Administrador**, eu quero **remover comentários e avaliações ofensivas**, para que **a plataforma continue sendo um ambiente saudável**.
