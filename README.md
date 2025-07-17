# 🛒 Refinando um Projeto Conceitual de Banco de Dados – E-COMMERCE

> Um projeto simples e direto sobre como criar e estruturar um banco de dados para um sistema de e-commerce, com foco nos relacionamentos entre clientes (PF ou PJ), formas de pagamento e entregas.

---

## 💡 Objetivo

Esse projeto foi criado com a intenção de simular um sistema básico de e-commerce, modelando os dados de forma clara, organizada e realista. A ideia aqui é apresentar como seria o desenho conceitual e relacional de um banco de dados voltado para:

- **Clientes PF e PJ** (não pode ser os dois ao mesmo tempo)
- **Formas de Pagamento múltiplas**
- **Status de Entrega + Código de Rastreio**

Tudo feito com um toque mais humano e prático — como se fosse alguém do time explicando pra você enquanto monta o projeto junto!

---

## 🧠 Modelagem Conceitual

### Entidades principais:

- `Cliente`  
  Um cliente pode ser **Pessoa Física (PF)** ou **Pessoa Jurídica (PJ)**, mas nunca os dois ao mesmo tempo.

- `Pagamento`  
  Um cliente pode ter várias formas de pagamento cadastradas.

- `Pedido`  
  Representa uma compra feita por um cliente.

- `Entrega`  
  Cada pedido possui uma entrega com status e código de rastreio.

---

## 🛠️ Modelo Relacional (DER)

```plaintext
Cliente
├── id_cliente (PK)
├── tipo ('PF' ou 'PJ')
├── nome_razao
├── cpf_cnpj
└── email

Pagamento
├── id_pagamento (PK)
├── id_cliente (FK)
├── tipo_pagamento (Cartão, Boleto, Pix...)
├── dados

Pedido
├── id_pedido (PK)
├── id_cliente (FK)
├── data
├── total

Entrega
├── id_entrega (PK)
├── id_pedido (FK)
├── status
├── codigo_rastreamento
