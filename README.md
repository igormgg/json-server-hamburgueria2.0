## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

Além disso, também existem mais 8 endpoints, 1 para listar os usuários cadastrados, 3 para cadastrar produtos, visualizar produtos cadastrados, e deletar produtos, e mais 4 para cadastrar produtos no carrinho, visualizar produtos cadastrados no carrinho, editar dados dos produtos no carrinho, e deletar produtos cadastrados no carrinho.

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

### Products

POST /products <br/>
GET /products <br/>
DEL /products/:idDoProduto:

A requisição POST /products pode ser usada para cadastrar produtos novos. Apenas o usuário dono da requisição pode cadastrar um novo produto, tendo que informar o Bearer Token no cabeçalho da requisição (Authorization: Bearer {token}), e passar no corpo da requisição os dados do novo produto a ser cadastrado (os novos dados podem ser escolhidos à vontade pelo usuário), junto com a userId do usuário criador, como, por exemplo:

{ <br/>
"userId": "1", <br/>
"product": "Hambúrguer", <br/>
"category": "Sanduíches", <br/>
"price": 14.00 <br/>
}

Já a requisição GET /products pode ser usada pra listar todos os produtos já cadastrados. Esse endpoint não precisa de autorização alguma para ser acessado.

Por sua vez, a requisição DEL /products/:idDoProduto: pode ser usada para deletar um produto cadastrado. Qualquer usuário logado pode deletar um produto, bastando apenas que informe o Bearer Token no cabeçalho da requisição (Authorization: Bearer {token}), e passe o id do produto na url da requisição.

### Cart

POST /cart <br/>
GET /cart <br/>
DEL /cart

A requisição POST /cart pode ser usada para cadastrar novos produtos no carrinho. Qualquer usuário logado pode cadastrar uma novo produto no carrinho, bastando apenas que informe o Bearer Token no cabeçalho da requisição (Authorization: Bearer {token}), e passe no corpo da requisição os dados do novo produto a ser cadastrado no carrinho (os novos dados podem ser escolhidos à vontade pelo usuário), como, por exemplo:

{ <br/>
"product": "Fanta Guaraná", <br/>
"category": "Bebidas", <br/>
"price": 5.00 <br/>
}

Já a requisição GET /cart pode ser usada pra listar todos os produtos já cadastrados no carrinho. Qualquer usuário logado pode listar os produtos cadastrados no carrinho, bastando apenas que informe o Bearer Token no cabeçalho da requisição (Authorization: Bearer {token}).

por sua vez, a requisição PATCH /cart/:idDoProduto: pode ser usada para editar um dado do produto. Qualquer usuário logado pode editar um dado de um produto no carrinho, bastando apenas que informe o Bearer Token no cabeçalho da requisição (Authorization: Bearer {token}), e passe no corpo da requisição os novos dados do produto a serem editados, como, por exemplo:

{ <br/>
"price": 6.00
}

Por último, a requisição DEL /cart/:idDoProduto: pode ser usada para deletar um produto cadastrado no carrinho. Qualquer usuário logado pode deletar um produto do carrinho, bastando apenas que informe o Bearer Token no cabeçalho da requisição (Authorization: Bearer {token}), e passe o id do produto na url da requisição.
