---
title: Documentação ShareFin
---

# **GET** `/account`
#### Query Params

| Parâmetro | Tipo | Obrigatório | Descrição |
| --- | --- | --- | --- |
| nome    | string | não | Nome da conta |
| moeda   | string   | não | Moeda utilizada na conta |
| ativa | bool   | não | Status de atividade |
| share | bool   | não | Status de compartilhamento |

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body
None

### Example
```api/v1/account```

#### Response `200`

```json
{
    "count": 4,
    "result": [
        {
            "id": 40,
            "usuario_id": 1,
            "nome": "C6",
            "moeda": "BRL",
            "cor": "#fff",
            "ativa": true,
            "created_at": "2025-12-27T18:52:59.4",
            "update_at": "2025-12-27T18:52:59.4",
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
| nome   | string   | sim | Nome da conta bancária | 
| moeda | string   | sim | Moeda utilizada na conta |
| cor | string   | não | Cor da conta bancária |
| ativa | bool   | não | Status de atividade |
| share | bool   | não | Status de compartilhamento |
| shareCode | string   | não | Código de compartilhamento |

### Example
```api/v1/account```

### Example Body
```json
{
    "user": 1,
    "nome": "C6",
    "moeda": "BRL",
    "cor": "#fff",
    "ativa": true,
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
| nome   | string   | não | Nome da conta bancária | 
| moeda | string   | não | Moeda utilizada na conta |
| cor | string   | não | Cor da conta bancária |
| ativa | bool   | não | Status de atividade |
| share | bool   | não | Status de compartilhamento |

### Example
```api/v1/account/40```

### Example Body
```json
{
    "nome": "C9 Bank"
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
```api/v1/account/40```

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
| nome   | string   | não | Nome da categoria |
| tipo   | string   | não | Tipo da transação |

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body
None

### Example
```api/v1/category```

#### Response `200`
```json
{
    "count": 16,
    "result": [
        {
            "id": 28,
            "usuario_id": 1,
            "nome": "Internet",
            "tipo": "1",
            "cor": "#ff00ea",
            "valor_inicial": 0,
            "icone": null
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
| nome   | string   | sim | Nome da categoria | 
| tipo | string   | sim | Tipo da categoria |
| valor_inicial | Float   | não | Valor inicial da categoria |
| cor | string   | não | Cor da categoria |
| icone    | string | não | Icone da categoria |

### Example
```api/v1/category```

### Example Body
```json
{
    "nome": "Faculdade",
    "tipo": "0",
    "cor": "#fff",
    "valor_inicial": "10",
    "usuario_id": 2
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
| nome   | string   | sim | Nome da categoria | 
| tipo | string   | sim | Tipo da categoria |
| valor_inicial | Float   | não | Valor inicial da categoria |
| cor | string   | não | Cor da categoria |
| icone    | string | não | Icone da categoria |

### Example
```api/v1/category/40```

### Example Body
```json
{
    "nome": "Cursos Udemy"
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
```api/v1/category/40```

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
| data_transacao_low   | datetime (YYYY-MM-DD)   | não | Data inicial do filtro de transação |
| data_transacao_high   | datetime (YYYY-MM-DD)   | não | Data final do filtro de transação |
| conta   | string   | não | Conta da transação |

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body
None

### Example
```api/v1/dashboard```

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
```api/v1/feedback```

#### Response `200`
```json
{
    "count": 5,
    "result": [
        {
            "id": 1,
            "usuario_id": 1,
            "titulo": "BUG",
            "descricao": "tela de categorias nao abre!",
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
| titulo    | string | sim | Titulo do feedback |
| descricao   | string   | sim | Descrição do feedback | 


### Example
```api/v1/feedback```

### Example Body
```json
{
    "titulo": "BUG",
    "descricao": "tela de categorias nao abre!"
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
| conta    | string | não | Nome da conta |
| categoria   | string   | não | Nome da categoria |
| usuario | string   | não | Nome do usuário |
| obs | string   | não | Nome da transação |
| tipo | string   | não | Tipo da transação ("1" receita, "2" despesa) |
| data_transacao_low | datetime (YYYY-MM-DD)   | não | Data inicial do filtro de transação |
| data_transacao_high | datetime (YYYY-MM-DD)   | não | Data final do filtro de transação |

### Headers
Authorization : Bearer {{ Token_jwt }}

### Request Body
None

### Example
```api/v1/transactions```

#### Response `200`
```json
{
    "count": 45,
    "result": [
        {
            "id": 123,
            "valor": 75.58,
            "obs": "Cafes gourmet",
            "data_transacao": "2026-01-08T00:00:00",
            "conta": "Caixa",
            "categoria": "Vale alimentação",
            "usuario": "Augusto Dalmas"
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
```api/v1/transactions/share```

#### Response `200`
```json
[
    {
        "id": 126,
        "valor": -123,
        "obs": "Livro MongoDB",
        "data_transacao": "2026-01-17T00:00:00",
        "conta": "COMPART",
        "categoria": "Faculdade",
        "usuario": "Augusto Rodolpho Dalmás"
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
```api/v1/transaction/123```

#### Response `200`
```json
{
    "id": 123,
    "valor": 75.58,
    "obs": "Cafes gourmet",
    "data_transacao": "2026-01-08T00:00:00",
    "conta": "Caixa",
    "conta_id": 19,
    "categoria": "Vale alimentação",
    "categoria_id": 31,
    "usuario": "Augusto Dalmas"
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
| conta    | Int | não | ID da conta |
| categoria   | Int   | não | ID da categoria |
| usuario | Int   | não | ID do usuário |
| valor | float   | sim | Valor da transação |
| obs | string   | não | Nome da transação |
| data_transacao_low | datetime (YYYY-MM-DD)   | não | Data da transação |

### Example
```api/v1/transactions```

### Example Body
```json
{
    "user": 1,
    "conta": 40,
    "categoria": 28,
    "valor": 666,
    "data_transacao": "2026-01-17",
    "obs": "item aleatorio"
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
```api/v1/transactions/import/csv```

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
| conta    | Int | não | ID da conta |
| categoria   | Int   | não | ID da categoria |
| usuario | Int   | não | ID do usuário |
| valor | float   | sim | Valor da transação |
| obs | string   | não | Nome da transação |
| data_transacao | datetime (YYYY-MM-DD)   | não | Data da transação |

### Example
```api/v1/transactions/40```

### Example Body
```json
{
    "conta_id": 2,
    "valor": 555,
    "obs": "Chocolate",
    "data_transacao": "2025-10-11T03:00:00"
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
```api/v1/transactions/40```

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
```api/v1/transaction/123```

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
| nome   | string   | sim | Nome do usuário | 
| email   | string   | sim | Email do usuário | 
| senha   | string   | sim | Senha do usuário | 

### Example
```api/v1/account```

### Example Body
```json
{
    "nome": "Augusto Rodolhpo",
    "email": "augustorodolpho@gmail.com",
    "senha": "XXXXXXXX"
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
| senha   | string   | sim | Senha do usuário | 

### Example
```api/v1/account```

### Example Body
```json
{
    "email": "augusto.dalmas@gmail.com",
    "senha": "XXXXXXXX"
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
