# Desafio - React Native

## Instruções

1. Esforço e tempo

Assim que receber o teste nos informe a sua estimativa de tempo para concluir o desafio ou entregar o que conseguir das funcionalidades descritas.

2. Publique seu desafio

Instruções para submeter o desafio:

- Faça um `fork` desse projeto
- Modifique e escreva seu código de acordo com a evolução do projeto
- Faça commits nas alterações que julgar necessárias (commits serão avaliados de acordo com a sua relevância)
- Ao terminar, nos envie o repositório criado.

## Sobre o desafio

- Desenvolvimento de um aplicativo para criação de Tarefas.
- As Tarefas possuem dois atributos: `title` e `priority` que indicam o nome e a prioridade da Tarefa respectivamente.
- Deve-se seguir o layout desenhado neste link do [Figma](https://www.figma.com/file/UKhdZwmWWRFkI1SZ6GrtKX/Desafio-Waterpark?node-id=1821%3A3073).
- Na listagem de Tarefas as cores das prioridades mudam de acordo com seu nível (Alta, Normal, Baixa)

#### É importante desenvolver utilizando os seguintes conceitos
- [`Styled Components`](https://styled-components.com/docs/basics#motivation)
- [`Redux`](https://redux.js.org/introduction/getting-started)

## Funcionalidades

### Login

Você reberá um usuário para acessar a plataforma.

Para realizar o login faça um `POST` no endpoint `https://wtpk-desafio-api.herokuapp.com` enviando no corpo da requisição o seguinte `json`:

```json
{
  "username": "email@dosusuario.com.br",
  "password": "12345678"
}
```

Uma chamada com sucesso deverá retornar um `token` no formato:

```json
{
  "token": "eyJ0eXAiOiJKV1Q.eyJ1c2VyX2lkIjoxLCJ1c2VwuY29tIi9.QHX8R9DHEAMFqaBIs"
}
```

> Esse token será utilizado nas próximas requisições

### Listagem de tarefas

Listar tarefas cadastradas pelo usuário.

Faça um `GET` na rota `https://wtpk-desafio-api.herokuapp.com/api/tasks/`

É necessário passar um `header`, onde `__token__` é o token recebido na request de login.

```json
{
  "Authorization": "JWT __token__"
}
```

Uma chamada com sucesso deverá retornar um `array` contendo as Tarefas no formato:

```json
[
  { "title": "Minha primeira tarefa", "priority": "Baixa" },
  { "title": "Minha segunda tarefa", "priority": "Baixa" }
]
```

### Cadastro de tarefas

Cadastrar novas tarefas para o usuário.

Faça um `POST` na rota `https://wtpk-desafio-api.herokuapp.com/api/tasks/`

É necessário passar um `header`, onde `__token__` é o token recebido na request de login.

```json
{
  "Authorization": "JWT __token__"
}
```

O `body` deve conter os atributos da `task`:

```
{
  "title": "Minha tarefa"
  "priority": "Baixa" // pode ser "Alta", "Baixa" ou "Normal"
}
```

A chamada com sucesso deve retornar um `array` no formato:

```json
{
  "id": 4,
  "title": "Minha tarefa",
  "priority": "Baixa"
}
```
