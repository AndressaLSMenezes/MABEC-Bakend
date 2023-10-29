# MABEC - E-commerce

## Tabela de Conteúdos

- [Visão Geral](#1-visão-geral)
- [Funcionalidades](#2-funcionalidades)
- [Diagrama ER](#3-diagrama-er)
- [Estrutura do banco de dados](#4-estrutura-do-banco-de-dados)
- [Contribuidores](#5-contribuidores)


## 1. Visão Geral

O projeto MABEC é um página web para um e-commerce de produtos eletrônicos como computadores, peças de computadores,
periféricos, notebooks, smartphones, consoles, headsets, etc. 
O usuário pode criar o seu perfil, navegar por uma vitrine de produtos disponíveis e realizar compras.

## 2. Funcionalidades

No escopo do projeto temos as páginas:

Para cliente:
- Vitrine de produtos
- Criação do perfil do usuário
- Perfil
- Login
- Produto
- Carrinho de compras
- Confirmação de pedido

Para administrador(ou vendedor):
- Inserir/excluir/alterar produtos
- Listar produtos
- Visualizar produtos mais vendidos ou por ID
- Listar clientes
- Visualizar cliente por ID
- Visualizar clientes que compraram X produto
- Visão geral (metricas) das vendas

A loja poderá:
- Registrar produtos
- Mostrar vitrine de produtos
- Permitir pesquisas com diferentes filtros
- Registrar pedidos
- Enviar pedidos ao vendedor (ou administrador)
- Armazenar/alterar e mostrar o estado de cada pedido (Em confirmação, confirmado, em andamento, concluido/entregue)
- Emitir nota fiscal


## 3. Diagrama ER

[ Voltar para o topo ](#tabela-de-conteúdos)

Diagrama ER da API definindo bem as relações entre as tabelas do banco de dados.

![DER](diagram.png)


## 4. Estrutura do banco de dados

[ Voltar para o topo ](#tabela-de-conteúdos)

- Customer: 

  - id: Chave Primaria
  - name: Nome do Cliente
  - phone_number: Telefone do cliente
  - email: Email Pessoal
  - password: Senha do cliente

- Address:

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

- Products: 

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

- Products_in_cart:
 
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

- Shopping_Products (Tabela Intermediaria entre Shopping e Product)

  - id: Chave Primaria
  - shopping_id: ID da tabela venda
  - product_id: ID do produto
  - amount: Quantidades

## 5. Contribuidores

<style>
.contributors {
    margin-top: 30px;
    display: flex;
    gap: 15px;
}

.contributors > a {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;

    height: 145px;
    width: 90px;
}

.contributors > a > img{
    height: 80px;
    width:80px;
    border-radius: 50%;
}
.contributors > a > p{
  font-size: 1rem;
  line-height: 1.2rem;
  text-align: center;
}

</style>

<div class="contributors">
<a href="https://github.com/btrz-pm">
<img width="80px" src="https://avatars.githubusercontent.com/u/119023866?v=4">
<p>Beatriz P. Machado</p>
</a>

<a href="https://github.com/Camilafss">
<img width="80px" src="https://avatars.githubusercontent.com/u/149213167?v=4">
<p>Camila Fernanda</p>
</a>

<a href="https://github.com/eltonfelii">
<img width="80px" src="https://avatars.githubusercontent.com/u/62625745?v=4">
<p>Elton Vinicius</p>
</a>

<a href="https://github.com/KarrunaQZ">
<img width="80px" src="https://avatars.githubusercontent.com/u/130697655?v=4">
<p>Mariano Queiroz</p>
</a>

<a href="https://github.com/AndressaLSMenezes">
<img width="80px" src="https://avatars.githubusercontent.com/u/106389968?v=4">
<p>Andressa Lopes</p>
</a>
</div>