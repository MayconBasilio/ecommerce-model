# 🛒 Modelo Conceitual - Sistema de E-commerce

Este repositório contém o **modelo conceitual de banco de dados** para um sistema de e-commerce, desenvolvido como parte de um desafio de projeto. O foco principal está em representar corretamente os relacionamentos entre **clientes (PJ e PF)**, **formas de pagamento**, **pedidos**, **entregas** e **itens de pedido**.

## 🎯 Objetivo do Projeto

Refinar o modelo apresentado inicialmente, atendendo aos seguintes requisitos adicionais:

- **Cliente PJ e PF**: Uma conta pode ser Pessoa Física (PF) ou Pessoa Jurídica (PJ), mas **não ambas simultaneamente**.
- **Pagamento**: Um cliente pode cadastrar **mais de uma forma de pagamento**.
- **Entrega**: Cada pedido possui **status de entrega** e um **código de rastreamento**.

## 🧩 Modelo Conceitual

![Modelo Conceitual](./diagramas/modelo_conceitual.png)

### Entidades e Atributos

- **Cliente**
  - `id_cliente` (PK)
  - `tipo` (Enum: PF ou PJ)

- **Pessoa Física (PF)**
  - `id_cliente` (PK, FK)
  - `nome`
  - `cpf`
  - `data_nascimento`

- **Pessoa Jurídica (PJ)**
  - `id_cliente` (PK, FK)
  - `razao_social`
  - `cnpj`
  - `nome_fantasia`

- **Forma de Pagamento**
  - `id_pagamento` (PK)
  - `id_cliente` (FK)
  - `tipo` (Ex: Cartão, Pix, Boleto)

- **Pedido**
  - `id_pedido` (PK)
  - `id_cliente` (FK)
  - `data_pedido`
  - `status_entrega` (Ex: Em preparo, Enviado, Entregue)
  - `codigo_rastreio`

- **Item do Pedido**
  - `id_item` (PK)
  - `id_pedido` (FK)
  - `id_produto` (FK)
  - `quantidade`
  - `preco_unitario`

- **Produto**
  - `id_produto` (PK)
  - `nome`
  - `descricao`
  - `preco`

## 🗂️ Estrutura do Repositório

📦 ecommerce-model
┣ 📂 diagramas/
┃ ┗ 📄 modelo_conceitual.png
┣ 📄 README.md
┗ 📄 modelo_conceitual.mwb

## 💡 Tecnologias e Ferramentas

- MySQL Workbench para modelagem
- Markdown para documentação
- GitHub para versionamento

## 🚀 Como Usar

1. Clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/ecommerce-model.git
2. Abra o arquivo .mwb no MySQL Workbench.

3. Visualize o diagrama em /diagramas/modelo_conceitual.png.

## 📬 Contato
Caso tenha dúvidas ou sugestões, sinta-se à vontade para abrir uma issue ou entrar em contato!

Este projeto foi desenvolvido como parte de um desafio de modelagem de dados e tem fins educativos e demonstrativos para portfólio.
