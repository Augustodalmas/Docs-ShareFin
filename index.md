---
title: Documentação ShareFin
---

# **GET** `/account`
#### Query Params

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| name    | string | não | Nome da conta |
| coin   | string   | não | Moeda utilizada na conta |
| ative | bool   | não | Status de atividade |
| share | bool   | não | Status de compartilhamento |

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body
None

### Example
api/v1/account

#### Response `200`

```json
{
    "count": 3,
    "result": [
        {
            "id": 40,
            "user_id": 1,
            "name": "C9 Bank",
            "coin": "BRL",
            "color": "#fff",
            "ative": true,
            "created_at": "2025-12-27T18:52:59.4",
            "update_at": "2026-01-17T10:47:42.678",
            "share": true
        },
    ]
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento."
}
```

# **POST** `/account`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| user    | int | sim | Id do usuário |
| name   | string   | sim | Nome da conta bancária | 
| coin | string   | sim | Moeda utilizada na conta |
| color | string   | não | Cor da conta bancária |
| ative | bool   | não | Status de atividade |
| share | bool   | não | Status de compartilhamento |
| shareCode | string   | não | Código de compartilhamento |

### Example

api/v1/account

### Example Body
```json
{
    "user": 1,
    "name": "C6",
    "coin": "BRL",
    "color": "#fff",
    "ative": true,
    "share": false,
    "shareCode": ""
}
```

#### Response `201`
```json
{
    "result": "Conta criada com sucesso!"
}
```

#### Response `403`
```json
{
    "erro": "Erro ao inserir dados."
}
```

#### Response `422`
```json
{
    "erro": "{{campo }} é obrigatório."
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento, tente novamente mais tarde."
}
```

# **UPDATE** `/account/:id`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| name   | string   | não | Nome da conta bancária | 
| coin | string   | não | Moeda utilizada na conta |
| color | string   | não | Cor da conta bancária |
| ative | bool   | não | Status de atividade |
| share | bool   | não | Status de compartilhamento |

### Example

api/v1/account/40

### Example Body
```json
{
    "name": "C9 Bank"
}
```

#### Response `200`
```json
{
    "result": "Conta atualizada com sucesso!"
}
```

#### Response `403`
```json
{
    "erro": "Erro ao atualizar dados."
}
```

#### Response `404`
```json
{
    "erro": "Conta não encontrada ou acesso negado."
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento, tente novamente mais tarde."
}
```

# **DELETE** `/account/:id`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body
None

### Example

api/v1/account/40

#### Response `200`
```json
{
    "result": "Conta excluida com sucesso!"
}
```

#### Response `403`
```json
{
    "erro": "Erro ao excluir contas."
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento, tente novamente mais tarde."
}
```

# **GET** `/category`
#### Query Params

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| name   | string   | não | Nome da categoria |
| type   | string   | não | Tipo da transação |

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body
None

### Example

api/v1/category

#### Response `200`
```json
{
    "count": 15,
    "result": [
        {
            "id": 28,
            "user_id": 1,
            "name": "Internet",
            "type": "1",
            "color": "#ff00ea",
            "initial_value": 0,
            "icon": null
        },
    ]
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento."
}
```

# **POST** `/category`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| name   | string   | sim | Nome da categoria | 
| type | string   | sim | Tipo da categoria |
| initial_value | Float   | não | Valor inicial da categoria |
| color | string   | não | Cor da categoria |
| icon    | string | não | Icone da categoria |

### Example

api/v1/category

### Example Body
```json
{
    "name": "Faculdade",
    "type": "0",
    "color": "#fff",
    "initial_value": "10",
    "user_id": 2
}
```

#### Response `201`
```json
{
    "result": "Categoria criada com sucesso!"
}
```

#### Response `403`
```json
{
    "erro": "Erro ao inserir dados."
}
```

#### Response `422`
```json
{
    "erro": "{{campo }} é obrigatório."
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento."
}
```


# **UPDATE** `/category/:id`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| name   | string   | sim | Nome da categoria | 
| type | string   | sim | Tipo da categoria |
| initial_value | Float   | não | Valor inicial da categoria |
| color | string   | não | Cor da categoria |
| icon    | string | não | Icone da categoria |

### Example

api/v1/category/40

### Example Body
```json
{
    "name": "Cursos Udemy"
}
```

#### Response `200`
```json
{
    "result": "Categoria atualizada com sucesso!"
}
```

#### Response `403`
```json
{
    "erro": "Erro ao atualizar dados."
}
```

#### Response `404`
```json
{
    "erro": "Categoria não encontrada ou acesso negado."
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento."
}
```

# **DELETE** `/category/:id`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body
None

### Example

api/v1/category/40

#### Response `200`
```json
{
    "result": "Categoria excluida com sucesso!, todas as transações com essa categoria foram apagadas."
}
```

#### Response `403`
```json
{
    "erro": "Erro ao excluir categoria."
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento."
}
```

# **GET** `/dashboard`
#### Query Params

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| date_transaction_low   | datetime (YYYY-MM-DD)   | não | Data inicial do filtro de transação |
| date_transaction_high   | datetime (YYYY-MM-DD)   | não | Data final do filtro de transação |
| account   | string   | não | Conta da transação |

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body
None

### Example

api/v1/dashboard

#### Response `200`
```json
{
    "total": 135.54000000000042,
    "expenses": -3981.81,
    "revenues": 4117.35,
    "count": 45,
    "categories": [
        {
            "categorie": "Assinaturas",
            "revenues": 0,
            "expenses": -19.9,
            "total": -19.9
        },
        {
            "categorie": "Spotfiry",
            "revenues": 0,
            "expenses": -21.9,
            "total": -21.9
        },
        {
            "categorie": "Saúde",
            "revenues": 0,
            "expenses": -182.8,
            "total": -182.8
        },
        {
            "categorie": "Internet",
            "revenues": 0,
            "expenses": -131.35,
            "total": -131.35
        },
        {
            "categorie": "Presentes",
            "revenues": 0,
            "expenses": -819.94,
            "total": -819.94
        },
        {
            "categorie": "Transporte",
            "revenues": 0,
            "expenses": -958.4000000000001,
            "total": -958.4000000000001
        },
        {
            "categorie": "Educação",
            "revenues": 0,
            "expenses": -706.71,
            "total": -706.71
        },
        {
            "categorie": "Vale alimentação",
            "revenues": 265.98,
            "expenses": 0,
            "total": 265.98
        },
        {
            "categorie": "Almoço",
            "revenues": 0,
            "expenses": -242.20999999999998,
            "total": -242.20999999999998
        },
        {
            "categorie": "Volei",
            "revenues": 0,
            "expenses": -270,
            "total": -270
        },
        {
            "categorie": "Salario",
            "revenues": 3655.8399999999997,
            "expenses": 0,
            "total": 3655.8399999999997
        },
        {
            "categorie": "Reembolso Marcopolo",
            "revenues": 195.52999999999997,
            "expenses": 0,
            "total": 195.52999999999997
        },
        {
            "categorie": "ViagemSP",
            "revenues": 0,
            "expenses": -572.29,
            "total": -572.29
        },
        {
            "categorie": "Compras Mercado",
            "revenues": 0,
            "expenses": -32.31,
            "total": -32.31
        },
        {
            "categorie": "Janta",
            "revenues": 0,
            "expenses": -24,
            "total": -24
        }
    ],
    "last6": [
        {
            "month": "ago. de 25",
            "expenses": 0,
            "revenues": 0
        },
        {
            "month": "set. de 25",
            "expenses": 0,
            "revenues": 0
        },
        {
            "month": "out. de 25",
            "expenses": 0,
            "revenues": 555
        },
        {
            "month": "nov. de 25",
            "expenses": 0,
            "revenues": 0
        },
        {
            "month": "dez. de 25",
            "expenses": -2282.92,
            "revenues": 3486.77
        },
        {
            "month": "jan. de 26",
            "expenses": -619.1800000000001,
            "revenues": 75.58
        }
    ],
    "range": {}
}
```

#### Response `500`
```json
{
    "erro": "Erro ao processar transações no banco de dados."
}
```

# **GET** `/feedback`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body
None

### Example

api/v1/feedback

#### Response `200`
```json
{
    "count": 6,
    "result": [
        {
            "id": 1,
            "user_id": 1,
            "tittle": "BUG",
            "description": "tela de categorias nao abre!",
            "created_at": "2025-11-23T18:46:03.023"
        },
    ]
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento."
}
```

# **POST** `/feedback`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| tittle    | string | sim | Titulo do feedback |
| description   | string   | sim | Descrição do feedback | 


### Example

api/v1/feedback

### Example Body
```json
{
    "tittle": "BUG",
    "description": "tela de categorias nao abre!"
}
```

#### Response `201`
```json
{
    "result": "Feedback enviado com sucesso!"
}
```

#### Response `403`
```json
{
    "erro": "Erro ao inserir dados."
}
```

#### Response `500`
```json
{
    "erro": "Erro ao enviar Feedback."
}
```

# **GET** `/transactions`
#### Query Params

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| account    | string | não | Nome da conta |
| category   | string   | não | Nome da categoria |
| user | string   | não | Nome do usuário |
| name | string   | não | Nome da transação |
| type | string   | não | Tipo da transação ("1" receita, "2" despesa) |
| date_transaction_low | datetime (YYYY-MM-DD)   | não | Data inicial do filtro de transação |
| date_transaction_high | datetime (YYYY-MM-DD)   | não | Data final do filtro de transação |

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body
None

### Example

api/v1/transactions

#### Response `200`
```json
{
    "count": 45,
    "result": [
        {
            "id": 123,
            "value": 75.58,
            "name": "Cafes gourmet",
            "date_transaction": "2026-01-08T00:00:00",
            "account": "Caixa",
            "category": "Vale alimentação",
            "user": "Augusto Dalmas"
        },
    ]
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento."
}
```

# **GET** `/transactions/share`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body
None

### Example

api/v1/transactions/share

#### Response `200`
```json
[
    {
        "id": 126,
        "value": -123,
        "name": "Livro MongoDB",
        "date_transaction": "2026-01-17T00:00:00",
        "account": "COMPART",
        "category": "Faculdade",
        "user": "Augusto Rodolpho Dalmás"
    },
]
```

#### Response `500`
```json
{
    "erro": "Erro de processamento."
}
```

# **GET** `/transaction/:id`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body
None

### Example

api/v1/transaction/123

#### Response `200`
```json
{
    "id": 123,
    "value": 75.58,
    "name": "Cafes gourmet",
    "date_transaction": "2026-01-08T00:00:00",
    "account": "Caixa",
    "account_id": 19,
    "category": "Vale alimentação",
    "category_id": 31,
    "user": "Augusto Dalmas"
}
```

#### Response `404`
```json
{
    "erro": "Transação não encontrada ou acesso negado."
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento."
}
```

# **POST** `/transactions`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| account    | Int | não | ID da conta |
| category   | Int   | não | ID da categoria |
| user | Int   | não | ID do usuário |
| value | float   | sim | Valor da transação |
| name | string   | não | Nome da transação |
| date_transaction | datetime (YYYY-MM-DD)   | não | Data da transação |

### Example

api/v1/transactions

### Example Body
```json
{
    "user": 1,
    "account": 40,
    "category": 28,
    "value": 666,
    "date_transaction": "2026-01-17",
    "name": "item aleatorio"
}
```

#### Response `201`
```json
{
    "result": "Transação criada com sucesso!",
    "id": 127
}
```

#### Response `403`
```json
{
    "erro": "A conta qual está referenciado a transação está desativada."
}
```

#### Response `422`
```json
{
    "erro": "O valor é obrigatório."
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento, tente novamente mais tarde."
}
```

# **POST** `/transactions/import/csv`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| file    | File | sim | Arquivo CSV |

### Example

api/v1/transactions/import/csv

### Example Body
Nubank_2026_01_01.csv

#### Response `200`
```json
[
    {
        "date": "2026-01-14",
        "title": "Tim*54984096156",
        "amount": "34.00"
    },
]
```

#### Response `404`
```json
{
    "erro": "Arquivo não enviado."
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento, tente novamente mais tarde."
}
```

# **UPDATE** `/transactions/:id`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| account    | Int | não | ID da conta |
| category   | Int   | não | ID da categoria |
| user | Int   | não | ID do usuário |
| value | float   | sim | Valor da transação |
| name | string   | não | Nome da transação |
| date_transaction | datetime (YYYY-MM-DD)   | não | Data da transação |

### Example

api/v1/transactions/40

### Example Body
```json
{
    "account_id": 2,
    "value": 555,
    "name": "Chocolate",
    "date_transaction": "2025-10-11T03:00:00"
}
```

#### Response `200`
```json
{
    "result": "Transação atualizada com sucesso!"
}
```

#### Response `403`
```json
{
    "erro": "Erro ao excluir transação."
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento, tente novamente mais tarde."
}
```

# **DELETE** `/transactions/:id`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body
None

### Example

api/v1/transactions/40

#### Response `200`
```json
{
    "result": "Transação excluida com sucesso!"
}
```

#### Response `403`
```json
{
    "erro": "Erro ao excluir transação."
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento, tente novamente mais tarde."
}
```

# **GET** `/usuario/confirmar-email`
#### Query Params

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| token   | string   | sim | Token de confirmação de Email | 

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body
None

### Example

api/v1/usuario/confirmar-email

#### Response `200`
```json
{
    "message": "E-mail confirmado com sucesso!"
}
```

#### Response `500`
```json
{
    "erro": "Erro ao confirmar e-mail"
}
```

# **POST** `/usuario`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| name   | string   | sim | Nome do usuário | 
| email   | string   | sim | Email do usuário | 
| password   | string   | sim | Senha do usuário | 

### Example

api/v1/usuario

### Example Body
```json
{
    "name": "Augusto Rodolhpo",
    "email": "augustorodolpho@gmail.com",
    "password": "XXXXXXXX"
}
```

#### Response `201`
```json
{
    "result": "Usuário criado com sucesso! Verifique seu e-mail para ativar a conta."
}
```

#### Response `403`
```json
{
    "erro": "Erro ao inserir dados."
}
```

#### Response `422`
```json
{
    "erro": "{{campo }} é obrigatório."
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento, tente novamente mais tarde."
}
```

# **POST** `/usuario/login`
#### Query Params
None

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| email   | string   | sim | Email do usuário | 
| password   | string   | sim | Senha do usuário | 

### Example

api/v1/usuario/login

### Example Body
```json
{
    "email": "augusto.dalmas@gmail.com",
    "password": "XXXXXXXX"
}
```

#### Response `201`
```json
{
    "message": "Logado com sucesso",
    "token": "JWT_TOKEN",
    "user": {
        "id": 1,
        "email": "augusto.dalmas@gmail.com",
        "is_admin": true
    }
}
```

#### Response `401`
```json
{
    "erro": "A senha está incorreta."
}
```

#### Response `403`
```json
{
    "erro": "Você precisa confirmar seu email antes de realizar o login."
}
```

#### Response `404`
```json
{
    "erro": "Usuário não encontrado."
}
```

#### Response `422`
```json
{
    "erro": "{{campo }} é obrigatório."
}
```

#### Response `500`
```json
{
    "erro": "Erro de processamento, tente novamente mais tarde."
}
```
