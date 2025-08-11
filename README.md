# Projeto de Banco de Dados — Universidade

## 📌 Descrição
Este projeto apresenta um **modelo conceitual de banco de dados** refinado, com base no desafio proposto, para contemplar:  
- Clientes Pessoa Física (PF) e Pessoa Jurídica (PJ)  
- Cadastro de múltiplas formas de pagamento por cliente  
- Entregas com status e código de rastreio  

O modelo foi criado visando simular um sistema de vendas online com gestão de clientes, pedidos e logística.

---

## 🗂 Modelo Conceitual

**Entidades e atributos principais:**

- **Cliente**  
  - id_cliente (PK)  
  - nome  
  - email  
  - telefone  
  - tipo_cliente (`PF` ou `PJ`)  

- **Pessoa_Fisica** (1:1 com Cliente, se tipo = PF)  
  - id_cliente (PK, FK)  
  - cpf  

- **Pessoa_Juridica** (1:1 com Cliente, se tipo = PJ)  
  - id_cliente (PK, FK)  
  - cnpj  
  - razao_social  

- **Pagamento**  
  - id_pagamento (PK)  
  - id_cliente (FK)  
  - tipo_pagamento (cartão, pix, boleto...)  
  - dados_pagamento  

- **Entrega**  
  - id_entrega (PK)  
  - id_pedido (FK)  
  - status_entrega (pendente, em trânsito, entregue...)  
  - codigo_rastreio  

- **Pedido**  
  - id_pedido (PK)  
  - id_cliente (FK)  
  - data_pedido  
  - valor_total  

Relacionamentos:  
- Cliente 1:N Pagamento  
- Cliente 1:N Pedido  
- Pedido 1:1 Entrega  
- Cliente 1:1 Pessoa_Fisica ou Pessoa_Juridica  

---

## 🖼 Diagrama Conceitual
* banco.png

---

## 📜 Script SQL (DDL)
Veja o arquivo `script.sql` neste repositório.
