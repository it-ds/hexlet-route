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
### [Условия и принятия решений](https://ru.hexlet.io/courses/introduction_to_programming/lessons/boolean/theory_unit)

```javascript
const abs = (num) => {
  if (num > 0) {
    return num;
  } else if (num < 0) {
    return -num;
  } else {
    return 0;
  } 
}
```

Другой вариант той же функции `abs`:

```javascript
const abs = (num) => {
  if (num === 0 || num > 0) {
    return num;
  } else {
    return -num;
  } 
}
```

**Тренарный оператор** условия (ternary operator):

```javascript
condition ? expression : expression
```

#### finalGrade.js

Реализуйте функцию `finalGrade`, которая вычисляет итоговую оценку студента на основе двух параметров: оценки за экзамен и количества законченных проектов.

Функция принимает два аргумента:

*exam* — оценка за экзамен, число от 0 до 100;
*projects* — количество проектов, число от 0 и выше.
Функция возвращает: число (итоговую оценку).

Есть четыре возможных итоговых оценки:

100, если оценка за экзамен выше 90 или есть больше 10 проектов
90, если оценка за экзамен выше 75 и есть как минимум 5 проектов
75, если оценка за экзамен выше 50 и есть как минимум 2 проекта
0 в любом другом случае
Вот как должна работать ваша функция:

```
пример вызова         // что должна вернуть функция при таком вызове
finalGrade(100, 12);  // 100
finalGrade(99, 0);    // 100
finalGrade(10, 15);   // 100
finalGrade(85, 5);    // 90
finalGrade(55, 3);    // 75
finalGrade(55, 0);    // 0
finalGrade(20, 2);    // 0
```

#### РЕШЕНИЕ finalGrade.js

```javascript
// BEGIN (write your solution here)
const finalGrade = (exam, projects) => {
  if (exam > 90 || projects >10) { return 100;}
  else if (exam > 75 && projects > 4 ) { return 90;}
  else if (exam > 50 && projects > 1 ) { return 75;}
  else { return 0;}
}
console.log(finalGrade(100, 12));
// END

export default finalGrade;
```


[//]: # (------------------------------------------------------------------------------------------------)
### [Ошибки](https://ru.hexlet.io/courses/introduction_to_programming/lessons/errors/theory_unit)

```javascript
const fahrToCelsius = (fahr) => {
  return (fahr - 32) * 5/9;
}
console.log(fahrToCelsius(50));
```


[//]: # (------------------------------------------------------------------------------------------------)
### [Рекурсия](https://ru.hexlet.io/courses/introduction_to_programming/lessons/recursion/theory_unit)

Функция, вычисляющая факториал:

```javascript
const factorial = (n) => {
  if (n === 1) {
    return 1;
  }
  else {
    return n * factorial(n-1);
  }
}

const answer = factorial(3);
```
**Требования рекурсии**

1. *Простой базовый случай* или *терминальный сценарий*.
2. Правило *двигаться по рекурсии*, углубляться.

Функция, вычисляющая сумму числового ряда:

```javascript
const sequenceSum = (begin, end) => {
  if (begin > end) {
    return NaN;
  } else if (begin === end) {
    return begin;
  }
  return begin + sequenceSum(begin + 1, end);
};

const answer = sequenceSum(2,6);
```


[//]: # (------------------------------------------------------------------------------------------------)
### [Итеративный процесс](https://ru.hexlet.io/courses/introduction_to_programming/lessons/iterative/theory_unit)

Суть итеративного процесса — вычисление с фиксированным количеством состояний.

```javascript
const factorial = (n) => {
  const iter = (counter, acc) => {
    if (counter === 1) {
      return acc;
    }
    return iter(counter - 1, counter * acc);
  };

  return iter(n, 1);
};
```

**Итеративный процесс** в целом:

1. Определить начальное состояние.
2. Проверить терминальный случай.
3. Определить новое состояние.
4. Повторить шаг 2.

- **Рекурсия** — это когда что-то содержит себя в своём описании.
- **Рекурсивный процесс** — это процесс обработки данных с отложенными вычислениями.
- **Итеративный процесс** — это процесс вычисления, когда состояние может быть описано фиксированным количеством значений.

