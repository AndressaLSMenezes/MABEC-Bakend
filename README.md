# MABEC - Ecomerce

Lorem ipsulum kkkkkkkkkkkkkkkkkkkkk

## Tabela de Conteúdos

- [Visão Geral](#1-visão-geral)
- [Diagrama ER](#2-diagrama-er)
- [Autenticação](#3-autenticação)
- [Endpoints](#4-endpoints)
- [Repositório e Deploy do Front-end](#5-repositório-e-deploy-do-front-end)
- [Futuras Implementações](#6-futuras-implementações)
- [Pré-requisitos](#7-pré-requisitos)



## 1. Visão Geral

Visão geral do projeto, um pouco das tecnologias usadas.

- [NodeJS](https://nodejs.org/en/)
- [Express](https://expressjs.com/pt-br/)
- [TypeScript](https://www.typescriptlang.org/)
- [PostgreSQL](https://www.postgresql.org/)
- [TypeORM](https://typeorm.io/)
- [Yup](https://www.npmjs.com/package/yup)

A URL base da aplicação:
https://contacts-backend-bdwz.onrender.com

---

## 2. Diagrama ER

[ Voltar para o topo ](#tabela-de-conteúdos)

Diagrama ER da API definindo bem as relações entre as tabelas do banco de dados.

![DER](diagram.png)

---


## 4. Autenticação

[ Voltar para o topo ](#tabela-de-conteúdos)

Por enquanto, não foi implementada autenticação.

---

## 5. Endpoints

[ Voltar para o topo ](#tabela-de-conteúdos)

### Índice

- [Customers](#1-customers)
  - [POST - /customers](#11-criação-de-cliente)
  - [GET - /customers](#12-listando-clientes)
  - [GET - /customers/:customer_id](#13-listar-cliente-por-id)
  - [PATCH - /customers/:customer_id](#14-atualizar-cliente-por-id)
  - [DELETE - /customers/:customer_id](#15-delete-cliente-por-id)

---

## 1. **Customers**

[ Voltar para os Endpoints ](#5-endpoints)

O objeto User é definido como:

| Campo       | Tipo   | Descrição                          |
| ----------- | ------ | ---------------------------------- |
| id          | string | Identificador único do cliente     |
| fullName    | string | O nome completo do cliente.        |
| email       | string | O e-mail do cliente.               |
| phoneNumber | string | Número de telefone do cliente      |
| createdAt   | date   | Data que o cliente foi criado.     |
| updatedAt   | date   | Data que o cliente foi atualizado. |
| deletedAt   | date   | Data que o cliente foi excluido.   |

### Endpoints

| Método | Rota                    | Descrição                                                           |
| ------ | ----------------------- | ------------------------------------------------------------------- |
| POST   | /customers              | Criação de um cliente.                                              |
| GET    | /customers/             | Lista todos os clientes                                             |
| GET    | /customers/:customer_id | Lista um cliente usando seu ID como parâmetro                       |
| PATCH  | /customers/:customer_id | Atualizar as informações de um cliente usando seu ID como parâmetro |
| DELETE | /customers/:customer_id | Deletar um cliente usando seu ID como parâmetro                     |


## 6. Repositório e Deploy do Front-end

Projeto frontend ainda não foi implementado.

## 7. Futuras Implementações
 - XXXXXXXXXXXXXXXXXXXXXXXXX
 - XXXXXXXXXXXXXXXXXXXXXXXXX
 - YYYYYYYYYYYYYYYYYYYYYYYYY

---

## 8. Pré-requisitos

Antes de começar, é necessário ter instalado em sua máquina:

- Python >= 3.10.12















### Estrutura do banco de dados

- Cliente: 

  - id: Chave Primaria
  - name: Nome do Cliente
  - phone_number: Telefone do cliente
  - email: Email Pessoal
  - password: Senha do cliente

- Endereço:

  - id: Chave Primaria
  - description: Nome Personalizado do endereço(Ex.: Casa)
  - cep: CEP
  - street: Rua do Cliente
  - number: Numero da casa do cliente
  - city: Cidade
  - state: Estado
  - neighborhood: Bairro.
  - complement: Complemento (Ex.: Apartamento 203)
  - main: Atributo boleano para verificar se é o principal.
  - user_id: Id do usuario.

- Produtos: 

  - id: Chave Primaria
  - name: Nome do produto 
  - description: Descrição do produto
  - sku: Código de barra
  - brand: Marca do Produto
  - package_dimensions: Dimensões do Pacote
  - weight: Peso do Produto
  - price: Preço
  - sale: Preço de promoção. Atributo nulavel. 
  - stock: Qauntidade do Produto Disponivel no estoque.  

- Produtos Adicionados ao carrinho:
 
  - id: Chave Primaria
  - customer_id: Id do comprador
  - product_id: ID do produto
  - amount: Quantidade do produto

- Shopping: 

  - id: Chave Primaria
  - customer_id: ID do Cliente
  - date_time: Data e horario da venda.
  - total_price: Preço total.
  - observation: Observação do cliente. Nulavel.
  - shipping_price: Valor do frete.

- Compras_Produtos (Tabela Intermediaria entre Shopping e Product)

  - id: Chave Primaria
  - shopping_id: ID da tabela venda
  - product_id: ID do produto
  - amount: Quantidades