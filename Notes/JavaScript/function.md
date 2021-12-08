### Функции

#### Синтаксис `new Function`

Функцию можно создать динамически:

```javascript
let func = new Function([arg1, arg2, ...argN], functionBody);
```

Пример:

```javascript
let sum = new Function('a', 'b', 'return a + b');

alert( sum(1, 2) ); // 3
```

