# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Capstones do Q2.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.
Exemplo de requisição:

{ <br/>
"email": "kenzo2021@bol.com", <br/>
"password": "123456", <br/>
"name": "Kenzo2021", <br/>
"age": 20 <br/>
}

### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users", passando como campos o email e a senha no corpo da requisição. <br/>
Exemplo de requisição:

{ <br/>
"email": "kenzo2021@bol.com", <br/>
"password": "123456" <br/>
}

### Users

GET /users

A requisição GET /users pode ser usada para listar todos os usuários cadastrados na API. Esse endpoint não precisa de nenhuma autorização especial.
