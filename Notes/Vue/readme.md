### Vue.js

#### Шаблон: самая база

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/vue/1.0.26/vue.min.js">
    </script>
    <script>
        var myModel = {
            name: "Алексей",
            age: 45
        };
    </script>
    <title>Изучаем Vue.js</title>
</head>
<body>
<div id="my_view">
    {{ name | uppercase  }} is {{ age }} years old.
</div>
<script>
    var myViewModel = new Vue({
        el: '#my_view',
        data: myModel
    });
</script>
</body>
</html>
```

#### Вывод в цикле

```html
<script>
var myModel = {
    name: "Ashley",
    age: 24,
    friends: [
        { name: "Bob", age: 21 },
        { name: "Jane", age: 20 },
        { name: "Anna", age: 29 }
    ]
};
</script>

<div id="my_view">
    <ul>
        <li v-for="friend in friends | orderBy 'age'"> {{ friend.name }} </li>
    </ul>
</div>

<script>
    var myViewModel = new Vue({
        el: '#my_view',
        data: myModel
    });
</script>
```