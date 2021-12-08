### Взаимодействие с пользователем

#### alert

Как правило, показывает небольшое окно с сообщением.

```javascript
alert("Hello");
```

#### prompt

Показывает окно, в которое пользователь должен ввести ответ

```javascript
result = prompt(title, [defaultValue]);
```

Если пользователь нажмет `Esc`, будет возвращено `null`.

#### confirm

Модальное окно с вопросом и кнопками "OK" и "Отмена".

```javascript
result = confirm(question);
```

