# hexlet-route

> hexlet.io courses routes and routines

[//]: # (================================================================================================)
## Введение в программирование

[//]: # (------------------------------------------------------------------------------------------------)
### [Первая программа](https://ru.hexlet.io/courses/introduction_to_programming/lessons/hello/theory_unit)

**console.log** используется в _JavaScript_ для вывода чего-нибудь на экран. 
Код для вывода фразы "Hello, World!" выглядит так: 

```javascript
console.log('Hello, World!');
```

[//]: # (-------------------------------------------------------------------------------------------------)
### [Функции и ящики](https://ru.hexlet.io/courses/introduction_to_programming/lessons/functions/theory_unit)

#### Способы записи функций

```javascript
// const <name> = (<argument>) => {
//   return <expressions>;
// };
const identity = (value) => {
  return value;
};
```

Существует несколько других. Например, если у вас функция-однострочник, то можно использовать сокращенный синтаксис:

```javascript
// const <name> = (<argument>) => <expressions>;
const identity = value => value;
```

В коде выше мы опустили фигурные скобки и слово **return**. 
Заодно мы опустили скобки вокруг аргумента — это можно делать только если у функции один аргумент.

Так же можно определять функции используя ключевое слово **function**:

```javascript
// Устаревший синтаксис, предпочтительным является () => {}.
const identity = function(value) {
  return value;
};
```

или

```javascript
// Такую функцию можно использовать до ее определения (в этом же файле).
function identity(value) {
  return value;
}
```

[//]: # (-------------------------------------------------------------------------------------------------)
