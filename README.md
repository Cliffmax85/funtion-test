Imagine you have this array:

```js
[
   { title: 'war of the worlds', author: 'wells', genre: 'scifi' }, 
   { title: 'pride and prejudice', author: 'austen', genre: 'classic' }, 
   { title: 'sula', author: 'morrison', genre: 'classic' },
   { title: 'the road', author: 'mccarthy', genre: 'scifi' } 
]
```

## .map

This method is a kind of `for` loop takes a callback as an argument.

That callback tells the method how to make a new function out of the old function.

Whatever you return from the callback will be the transformed item in a new array.

We can get an array just the titles as strings like so:

```js
books.map(book => {
   return book.title
})
```

This can be abbreviated, using implicit returns, like so:
```js
books.map(book => book.title)
```

We can make an array of `{ writer, work }` objects (that is, changing the names of keys), like so:

```js
books.map(book => {
     return { 
        writer: book.author,
        work: book.title
     }
})
```

This can be abbreviated, using implicit returns, like so:

```js
books.map(book => ({ 
        writer: book.author,
        work: book.title
     }))
```

## .filter

In the callback, for each item, if you return true, that item will be included in the new array. If you return false, it will be excluded.

We can get an array of just classic books as objects like so:

```js
books.filter(book => {
   if (book.genre === 'classic') { 
      return true
    }
})
```

This can be abbreviated, using implicit returns, like so:

```js
books.filter(book => book.genre === 'classic')
```

## .filter then .map

Array methods can be chained together.

We can get an array of just scifi titles as strings like so:

```js
books
  .filter(book => book.genre === 'classic')
  .map(book => book.title)
```

