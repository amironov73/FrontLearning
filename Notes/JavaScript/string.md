#### Строки в JavaScript

#### Стандартные операции и свойства

```javascript
const hello = 'Hello, World, Goodbye, World!';
console.log (hello.length);               // 28
console.log (hello.indexOf('World'));     // 7
console.log (hello.lastIndexOf('World')); // 23
console.log (hello.includes('World'));    // true
console.log (hello.includes('Word'));     // false
console.log (hello.substring(7, 12));     // World
console.log (hello.substring(23));        // World
console.log (hello.toLowerCase());        // hello, world, goodbye, world
console.log (hello.toUpperCase());        // HELLO, WORLD, GOODBYE, WORLD
console.log (hello.charAt(1));            // e
console.log (hello.charCodeAt(1));        // 101
console.log (' Hello '.trim());           // 'Hello'
console.log (' Hello '.trimStart());      // 'Hello '
console.log (' Hello '.trimEnd());        // ' Hello'
console.log (hello.split(', '));          // [ 'Hello', 'World', 'Goodbye', 'World' ]
console.log (hello.startsWith('Hello'));  // true
console.log (hello.endsWith('World'));    // true
console.log (hello.replace('World', 'Universe')); // Hello, Universe, Goodbye, World
```

#### Интерполяция строк

Для интерполяции используют обратные кавычки.

```javascript
const name = 'World';
const hello = `Hello, ${name}`;
console.log(hello);
```

#### Регулярные выражения

##### Подстановочные символы:

* `\d` соответствует любой цифре от 0 до 9;
* `\D` соответствует любому символу, который не является цифрой;
* `\w` соответствует любой букве, цифре или символу подчеркивания (диапазоны A–Z, a–z, 0–9);
* `\W` соответствует любому символу, который не является буквой, цифрой или символом подчеркивания (то есть не находится в следующих диапазонах A–Z, a–z, 0–9);
* `\s` соответствует пробельному символу (в т. ч. \t);
* `\S` соответствует любому символу, который не является пробелом;
* `.` соответствует любому символу.

Заметим, что метасимвол `\w` применяется только для букв латинского алфавита, кириллические символы для него не подходят.

##### Модификаторы:

* `{n}` соответствует n-ому количеству повторений предыдущего символа;
* `{n,}` соответствует n и более количеству повторений предыдущего символа;
* `{n,m}` соответствует от n до m повторений предыдущего символа;
* `?` соответствует одному вхождению предыдущего символа в подстроку или его отсутствию в подстроке;
* `+` соответствует одному и более повторений предыдущего символа;
* `*` соответствует любому количеству повторений или отсутствию предыдущего символа; 
* `^` соответствует началу строки; 
* `$` соответствует концу строки.
  
```javascript
const hello = 'Hello, World, Goodbye, World';
const expression = /World/;
console.log (expression.test(hello)); // true
console.log (expression.exec(hello)); // [
  //  'World',
  //  index: 7,
  //  input: 'Hello, World, Goodbye, World',
  //  groups: undefined
  // ]
console.log (expression.exec('no such word')); // null
```
  
Нечувствительные к регистру: const expression = /[a-z]/i;. Глобальные (матчат не одно совпадение): const expression = /a-z/g;. Многострочные: const expression = /[a-z]/m;.

Разбиение по регулярке:

```javascript
const hello = 'Hello, World, Goodbye, World';
hello.split(/,\s/).forEach(function (value, index, array) {
console.log(value); });
```

Матчинг:

```javascript
const hello = 'Hello, World, Goodbye, World';
hello.match(/[a-z]+/ig)
.forEach(function (value, index, array) {
console.log(value); });
```

Поиск:

```javascript
const hello = 'Hello, World, Goodbye, World';
console.log (hello.search(/[lo]/)); // 2
```

Замена:

```javascript
const hello = 'Hello, World, Goodbye, World';
console.log (hello.replace(/[A-Z]/g, '?'));
// ?ello, ?orld, ?oodbye, ?orld
```
