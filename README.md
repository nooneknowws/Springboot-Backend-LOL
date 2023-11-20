## PASSO A PASSO DA INSTALAÇÃO DO BANCO DE DADOS

 1. Baixar o postgresql - [Link](https://www.enterprisedb.com/postgresql-tutorial-resources-training-1?uuid=9d2a0585-9a16-457e-8ce2-1545f5f9a3e0&campaignId=Product_Trial_PostgreSQL_16)
 2. Baixar o postman para os testes - [Link](https://www.postman.com/downloads/)
 3. Baixar o Eclipse IDE - [Link](https://www.eclipse.org/downloads/)
 4. Baixar o Spring Tools - [Link](https://spring.io/tools)
 5. Configurar o servidor do postgres na porta 5432 com o usuario postgres e a senha postgres - [Imagem](https://prnt.sc/Kz8kytRP2sfg)
 6. Criar a database chamada backend-db -- CASE SENSITIVE.
 7. Criar as tabelas de acordo com os SQLs abaixo 

## SQL DAS TABELAS PARA O BANCO DE DADOS

### num precisa mais, agora é automático

caso tu n queira que as tabelas sejam resetadas toda vez q o spring liga dnv só trocar o código no application.properties de:
```java 

spring.jpa.hibernate.ddl-auto=create
```
pra: 
```java 

spring.jpa.hibernate.ddl-auto=update
```


## Comandos para teste no Postman

#### INSERIR NA TABELA de FUNCIONARIOS
POST em http://localhost:8081/funcionarios com um Raw JSON  - [Imagem](https://prnt.sc/NFAmlMJYx8Ny)
#### LISTAR OQ ESTÁ NA TABELA de FUNCIONARIOS
GET em http://localhost:8081/funcionarios
#### LISTAR OQ ESTÁ NA TABELA de FUNCIONARIOS por ID
GET em http://localhost:8081/funcionarios/{id} -> substituir ID pelo ID desejado dur
#### ALTERAR OQ ESTÁ NA TABELA por ID
PUT em http://localhost:8081/funcionarios/{id} -> com um Raw JSON doq vc qr alterar dentro da tabela - [Imagem](https://prnt.sc/J4tOn0RW0C_Q)
#### DELETAR OQ ESTÁ NA TABELA por ID
DELETE em http://localhost:8081/funcionarios/{id}
#### JSON de exemplo:

```json
{
    "email": "admin@admin.com",
    "nome": "admin",
    "datadenasc": null,
    "senha": "admin",
    "endereco": {
        "cep":"1"
    },
    "perfil": "ADMIN"
}
```
#### JSON de exemplo pra inserção de pedidos:

lembrando que o id do usuario e da roupa devem estar previamente cadastrados no banco de dados,
na hora de fazer um post de criação do pedido, lembrar de cadastrar o statuspedido como 1 > aberto.

```json
{
  "datadopedido":"2023-05-03",
  "statuspedido": "7",
  "usuario": {
    "id": 1
  },
  "itens": [
      {
      "roupa": {
        "id": 1
      },
      "quantidade": 10
    },
    {
      "roupa": {
        "id": 2
      },
      "quantidade": 1
    },
    {
      "roupa": {
        "id": 3
      },
      "quantidade": 5
    }
    ]
}
```

