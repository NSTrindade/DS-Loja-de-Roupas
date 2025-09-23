# Projeto LojaderoupasTEIP

![Java](https://img.shields.io/badge/Java-17+-blue?style=for-the-badge&logo=java)
![Swing](https://img.shields.io/badge/Swing-UI-orange?style=for-the-badge)
![MySQL](https://img.shields.io/badge/MySQL-DB-blue?style=for-the-badge&logo=mysql)
![GitHub](https://img.shields.io/badge/GitHub-Repo-black?style=for-the-badge&logo=github)

Aplicação de Desktop para Gestão de Loja de Roupas, desenvolvida em Java com a biblioteca Swing para a interface gráfica e um design moderno utilizando o Look and Feel FlatLaf.

## 🚀 Sobre o Projeto

Este projeto é um sistema de gestão de desktop (PDV - Ponto de Venda) para uma loja de roupas fictícia. O objetivo é criar uma aplicação que não seja apenas funcional para gerenciar clientes, produtos, estoque e pedidos, mas que também ofereça uma experiência de usuário (UX) agradável e uma interface (UI) moderna e intuitiva, fugindo do visual padrão e datado das aplicações Swing.

## 📸 Screenshots

*(Adicione aqui os prints das telas principais da sua aplicação quando estiverem prontas)*

---

## ✨ Funcionalidades

### ✅ Implementadas
- [x] Estrutura da aplicação com navegação lateral e `CardLayout`.
- [x] Conexão com banco de dados MySQL.
- [x] Implementação do Look and Feel FlatLaf para um design moderno.
- [x] **Clientes:** Funcionalidade de cadastro.
- [x] **Produtos:** Funcionalidade de cadastro com seleção de categorias e coleções.

### 📋 Planejadas
- [ ] CRUD Completo (Listar, Editar, Excluir) para todas as entidades.
- [ ] Validação de dados nos formulários.
- [ ] Gerenciamento de SKUs (variações de produtos por cor/tamanho).
- [ ] Módulo de criação de Pedidos/Vendas.
- [ ] Geração de Relatórios simples.
- [ ] Sistema de autenticação de usuários (Login).

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Java 17+
* **Interface Gráfica:** Java Swing
* **IDE:** Apache NetBeans
* **Banco de Dados:** MySQL
* **Driver de Conexão:** MySQL Connector/J
* **Design (Look and Feel):** [FlatLaf](https://www.formdev.com/flatlaf/)

---

## ⚙️ Como Executar o Projeto

**Pré-requisitos:**
* JDK 17 ou superior instalado.
* Apache NetBeans IDE.
* Servidor MySQL em execução.

**Passos:**
1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/SEU_USUARIO/LojaderoupasTEIP.git](https://github.com/SEU_USUARIO/LojaderoupasTEIP.git)
    ```
2.  **Abra o projeto** no Apache NetBeans.
3.  **Configure o banco de dados:**
    * Crie um banco de dados no MySQL com o nome `lojaderoupasTEIP`.
    * Execute o script SQL completo (fornecido no início do projeto) para criar todas as tabelas.
4.  **Configure a conexão:**
    * Abra o arquivo `src/br/com/lojaderoupasteip/connection/ConnectionFactory.java`.
    * Altere as constantes `USER` e `PASS` com seu usuário e senha do MySQL.
5.  **Adicione as bibliotecas (JARs):**
    * Certifique-se de que os arquivos `flatlaf.jar` e `mysql-connector-j.jar` estão na pasta de bibliotecas do projeto.
6.  **Execute a aplicação:**
    * Clique com o botão direito no arquivo `src/br/com/lojaderoupasteip/main/Main.java` e selecione "Executar Arquivo".

---

## 🗺️ Roadmap de Desenvolvimento

Este é o plano de desenvolvimento do projeto, dividido em fases e tarefas.

### 🎯 Fase 1: Estruturação do Repositório e Documentação (CONCLUÍDA)
- #### Tarefa 1: Criar o Repositório no GitHub.
- #### Tarefa 2: Criar um arquivo `.gitignore`.
- #### Tarefa 3: Escrever este `README.md`.
- #### Tarefa 4: Enviar o Código Inicial para o GitHub.

### 🎯 Fase 2: Completando as Funcionalidades CRUD

O objetivo é tornar os cadastros totalmente funcionais (Listar, Editar, Excluir).

- #### 📌 Tarefa 5: Implementar a Listagem de Clientes.
  1.  **DAO:** Criar o método `read()` no `ClienteDAO` que retorna uma `List<Cliente>`.
  2.  **View:** Adicionar uma `JTable` ao `TelaClientePainel`.
  3.  **Lógica:** Criar um método `readJTable()` no painel para buscar os dados do DAO e popular a tabela.

- #### 📌 Tarefa 6: Implementar a Atualização de Clientes.
  1.  **View:** Adicionar um botão "Editar" que preenche o formulário com os dados da linha selecionada na tabela.
  2.  **DAO:** Criar o método `update(Cliente c)` no `ClienteDAO`.
  3.  **Lógica:** Modificar o botão "Salvar" para chamar `update()` se um cliente existente estiver sendo editado.

- #### 📌 Tarefa 7: Implementar a Exclusão de Clientes.
  1.  **View:** Adicionar um botão "Excluir".
  2.  **DAO:** Criar o método `delete(int id)` no `ClienteDAO`.
  3.  **Lógica:** Ao clicar, pedir confirmação (`JOptionPane`) e, se confirmado, chamar `dao.delete()` e atualizar a tabela.

- #### 📌 Tarefa 8: Replicar o CRUD Completo para Produtos.
  * Seguir os mesmos passos da Tarefa 5, 6 e 7 para a entidade `Produto`.

### 🎯 Fase 3: Melhoria da Experiência do Usuário (UX) e Validação

- #### 📌 Tarefa 9: Implementar Validação de Formulários.
    * Verificar se campos obrigatórios não estão vazios antes de salvar.
    * Implementar validações básicas para formatos de CPF e Email.

- #### 📌 Tarefa 10: Melhorar o Feedback Visual.
    * Adicionar um botão "Novo/Limpar" para limpar os formulários.
    * Implementar um indicador visual (ex: cor de fundo) no menu lateral para mostrar qual tela está ativa.

### 🎯 Fase 4: Implementação das Regras de Negócio Principais

- #### 📌 Tarefa 11: CRUD Completo para Entidades de Apoio.
    * Implementar a interface completa (Model-DAO-View com CRUD) para **Categorias**, **Coleções** e **Fornecedores**.

- #### 📌 Tarefa 12: Gerenciamento de SKUs.
    * Na tela de Produtos, criar uma interface para adicionar/editar/remover variações (SKUs) de um produto selecionado (Tamanho, Cor, Preço, Estoque).

- #### 📌 Tarefa 13: Tela de Vendas (Pedidos).
    * Criar a `TelaPedidoPainel` para selecionar cliente, adicionar produtos (SKUs) a um "carrinho" e finalizar a venda, salvando os dados nas tabelas `Pedidos` e `Itens_Pedido` de forma transacional.

## 🗂️ Como Usar Este Roadmap no GitHub

A melhor forma de organizar o trabalho é usar as ferramentas do próprio GitHub:
1.  **Crie uma "Issue" para cada "Tarefa"** listada acima. Isso permite acompanhar o progresso de cada funcionalidade individualmente.
2.  **Use o "Projects" do GitHub** para criar um quadro Kanban (To Do, In Progress, Done) e arraste as Issues entre as colunas para visualizar o andamento do projeto.
