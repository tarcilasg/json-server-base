# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, aqui utilizada para a atividade "S3B11 JSON-Server: fake-API do início ao deploy" do Módulo 3.

## Endpoints

Base dos endpoints: https://json-server-catalogue-movies.herokuapp.com/

### Cadastro

POST /signup

Para cadastrar o usuário na lista de "Users" é necessário preencher a requisição com os campos email, password, name e age.

### Login

POST /login

Para realizar login com um dos usuários cadastrados na lista de "Users", sendo os campos obrigatórios email e password apenas.

### Cadastrar um filme na base

POST /movies

{
"title": "Bambi",
"filmgenre": "animation",
"userId": number
}
A chave "userId" deve ser preenchida com o id do usuário logado. O id retorna como resposta à requisição de login.
Também é necessário enviar a autenticação com token do tipo Bearer.

### Todos os filmes cadastrados na base

GET /movies

### Filtrar filmes cadastrados por gênero na base

GET /movies?filmgenre=genre

É possível filtrar na lista de filmes todos os títulos cadastrados passando como parâmetro o gênero.

### Editar um filme cadastrado na base do usuário logado

PUT /movies/idDoFilme

{
"title": "New Title / Same Title",
"filmgenre": "New Genre / Same Genre"
}
Necessita passar o id do filme na URL, que é possível verificar na lista de filmes cadastrados na base. Também necessita passar as duas chaves (title e filmgenre) para não perder um dos valores após a edição.

### Excluir um filme cadastrado na base do usuário logado

DELETE /movies/idDoFilme

Necessita passar o id do filme na URL, que é possível verificar na lista de filmes cadastrados na base.
Também é necessário passar o token do usuário para autorização da deleção.

### Cadastrar biografia pessoal

POST /bio

{
"bio": "Sua biografia aqui, sobre ser amante de cinema ou motivos para catalogar filmes",
"userId": number
}

A chave "userId" deve ser preenchida com o id do usuário logado. O id é retornado na resposta à requisição de login.
Também é necessário enviar a autenticação com token do tipo Bearer.

### Editar biografia pessoal

PUT /bio

{
"bio": "Sua nova biografia, sobre ser amante de cinema ou motivos para catalogar filmes",
"userId": number
}

A chave "userId" deve ser preenchida com o id do usuário logado. O id é retornado na resposta à requisição de login.
Também é necessário enviar a autenticação com token do tipo Bearer.
