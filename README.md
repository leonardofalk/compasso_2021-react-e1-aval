# Avaliação

Esse é o template inicial para o projeto final que compreende o módulo 2 do programa de bolsas em ReactJS. O objetivo desse template é poupar tempo com um exemplo estático de HTML e CSS, porém sem nenhuma funcionalidade que é necessária para finalizar o projeto. Seu trabalho aqui é adicionar interatividade ao projeto refatorando o código estático disponível nesse template.

O objetivo é ter um aplicativo que mostre quais livros eu já li, estou lendo ou quero ler em estantes, preenchidas pelos dados consumidos da API e usando React para montar a tela dinamicamente conforme os dados são modificados.

## Começar

Você pode começar executando `yarn/npm install` no terminal e depois `yarn/npm start` para começar o servidor de desenvolvimento, isso vai abrir seu browser automaticamente com hot reload habilitado.

## Exemplo da Aplicação Final

 - https://compasso-reads.netlify.app

## Servidor Backend

Para simplificar o processo de desenvolvimento, um backend já foi criado para esse app. O arquivo [`api.js`](./src/api.js) contém os métodos necessários para fazer as operações necessárias no backend:

* [`getBook`](#getBook)
* [`getMyBooks`](#getMyBooks)
* [`searchBooks`](#searchBooks)
* [`updateBook`](#updateBook)

### `getBook`

> Pesquisa e retorna os dados de um dos meus livros.

```jsx
getBook(BOOK_ID).then(function(data) {
  const book = data.book

  // ...
})
```

### `getMyBooks`

> Pesquisa e retorna todos os meus livros.

```jsx
getMyBooks().then(function(data) {
  const books = data.books

  // ...
})
```

### `searchBooks`

> Pesquisa e retorna todos os livros de um determinado assunto, que podem ou não estar nos meus livros.
> O termo pesquisado deve ser um dos listados nas [palavras-chave](./PALAVRAS_CHAVE.md), outros termos podem não funcionar.

```jsx
searchBooks(PALAVRA_CHAVE).then(function(data) {
  const books = data.books

  // ...
})
```

### `updateBook`

> Atualiza um livro para que ele pertença à uma determinada estante. Retorna todas as categorias da estante e os id's de livros pertencentes a cada estante. Pode ser usado para remover um livro de uma estante, basta passar como argumento qualquer estante diferente das 3 existentes.

```jsx
updateBook(BOOK, ESTANTE).then(function(data) {
  const estouLendoIDs = data.currentlyReading
  const queroLerIDs = data.wantToRead
  const lidosIDs = data.read

  // ...
})
```
