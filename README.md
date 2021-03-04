# Documentação de API de games teste
Esta api foi desenvolvida referente ao treinamento de desenvolvimento de API
##Endpoints
### GET /games
Esse endpoint é responsável por retornar todos os jogos cadastrados.
####Parametros
Nenhum
####Respostas
##### OK! 200
caso essa resposta aconteca voce receberá a lista de todos os jogos.
Exemplo de resposta :
```
[
    {
        "id": 23,
        "title": "Call of Duty MW",
        "year": 2019,
        "price": 60
    },
    {
        "id": 35,
        "title": "Sea of Thieves",
        "year": 2015,
        "price": 40
    },
    {
        "id": 12,
        "title": "Minecraft",
        "year": 2012,
        "price": 10
    }
]
```
##### Falha na autenticação! 401
Caso isso acontença possívelmente houve uma falha de autenticação da requisição , Motivos : Token invállido, Token Expirado.
Exemplo:
```
{
    "err": "Token Inválido"
}

```


### POST /auth
Esse endpoint é responsável por fazer o processo de login
####Parametros

email : E-mail do Usuário cadastrado no sistema
password : senha do usuário cadastrado.

```
{
    "email": "lenoardobruno@gmail.com",
    "password": "nodejs<3"
}
```

####Respostas
##### OK! 200
caso essa resposta aconteca voce receberá o Token de Acesso para acessar endpoints protegidos

```
{
  "token":       "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJsZW5vYXJkb2JydW5vQGdtYWlsLmNvbSIsImlhdCI6MTYxNDg2MzAyMSwiZXhwIjoxNjE1MDM1ODIxfQ.CMrJ8pZpmjeyMJ1NUHkn8JU5avRZb0WPWOvsRs1t-ro"
}
```

Exemplo de resposta :
##### Falha na autenticação! 401
Caso isso acontença possívelmente houve uma falha de autenticação da requisição , Motivos : senha ou email incorreto.
Exemplo:

```
{err: "Credenciais Inválidas"}
```
