### Svelte API

Компоненты помещаются в файлы `.svelte` следующего формата

```html
<script>
    // здесь JavaScript
</script>

<style>
    /* здесь CSS */
</style>

<!-- Здесь HTML-разметка -->
```

Все три секции опциональные, но что-нибудь присутствовать должно, иначе непонятно, зачем всё это затеяно.

Традиционно главный компонент помещают в `App.svelte`.

### Секция `script`

Содержит следующие элементы:

* опциональный **импорт компонентов**, использующихся в данном компоненте:

```html
<script>
    import Widget from './Widget.svelte';
    
</script>

<div>
    <Widget/>
</div>
```

* **экспорт переменных**, в терминологии Svelt именющихся `property` (`prop` для краткости):

```html
<script>
    export let foo;
    
    // значения, присвоенные пропертям, 
    // доступно сразу без приседаний
    console.log({ foo });
</script>
```

Пропертям можно присваивать значения по умолчанию:

```html
<script>
    export let bar = 'default value';
    export const thisIs = 'readonly'; // неизменяемая проперть
</script>
```

Также можно экспортировать классы и функции. Они автоматически становятся неизменяемыми (`const` в терминологии JavaScript).

Если очень необходимо, можно применять хитрый `export`, позволяющий экспортировать идентификаторы, совпадающие с зарезервированными словами:

```html
<script>
    let className;
    
    export { className as class };
</script>
```

* **реактивные операторы**, помещаемые специальной меткой `$`:

```html
<script>
    export let title;
    
    $: document.title = title;
    $: {
        console.log('Допускается несколько строк');
        console.log('Новый заголовок:', title);
    }
    
</script>
```

Можно заводить переменные в реактивном операторе:

```html
<script>
    export let title;
    
    $: uppercase = title.toUpperCase(); // Svelte неявно добавит `let`
</script>
```

* **отслеживание присваивания переменных**:

Все присваивания внутри функций/методов секции `script` (и во "встроенных" скриптах-обработчиках событий) проверяются компилятором и при необходимости становятся "реактивными" (т. е. приводят к рендерингу соответствующих компонентов).

```html
<script>
    let count = 0;
    
    function handleClick() {
        // все элементы HTML, в которых встречается `count`,
        // будут перерисованы
        count = count + 1;
    }
</script>
```

К сожалению, это не работает с методами вроде `.push` и `.splice`, поэтому приходится прибегать к лишнему присваиванию:

```html
<script>
    let array = [0, 1];
    
    function handleClick() {
        array.push(2);
        array = array; // присваивание, триггерящее рендеринг
        
        // можно сделать так, чтобы не дразнить линтер:
        array = [...array, 2];
    }
</script>
```

#### store

`store` - это объект, предоставляющий реактивный доступ с помощью следующего простого контракта:

```typescript
store = {
    subscribe: (subscription: (value: any) => void) => (() => void),
    set?: (value: any) => void
};
```

Функцию для создания обертки, реализующей данный контракт, можно позаимствовать из модуля `svelte/store`:

```html
<script>
    import { writable } from 'svelte/store';
    
    const unsubscribe = count.subscribe(value => {
       console.log(value); // выводит 0 
    });
    
    const count = writable(0);
    console.log($count); // выводит 0
    
    count.set(1);
    console.log($count); // выводит 1
    
    $count = 2;
    console.log($count); // выводит 2
    
    count.update(n => n + 1);
    
    unsubscribe(); // отписались
</script>
```

Обратите внимание: во-первых, к значению, хранящемуся во `writable` можно обращаться с помощью префикса `$` (Svelte автоматически превратит в обращение к значению).

Существует также аналогичная функция для создания оберток "только для чтения":

```html
<script>
    import { readable } from 'svelte/store';
    
    const time = readable(null, set => {
        set(new Date());
        
        const interval = setInterval(() => {
            set(new Date());
        }, 1000);
        
        return () => clearInterval(interval);
    });
</script>
```

### Однократное исполнение `script`

```html
<script context="module">
    // код будет выполнен один раз в момент инициализации модуля компонента
    // и не будет повторяться для каждого создаваемого экземпляра компонента
</script>
```

Пример:

```html
<script context="module">
    let totalComponents = 0;
    
    export function alertTotal() {
        alert(totalComponents);
    }
</script>

<script>
    totalcomponents += 1;
    console.log('Total:', totalcomponents)
</script>
```

### Секция `style`

Главное свойство секции `style` -- все стили, не помеченные особым образом, будут применяться только внутри текущего компонента (на другие компоненты они распространяться не будут, т. к. Svelte по умолчанию дописывает к стилю уникальный суффикс).

Чтобы стиль стал глобальным, его необходимо пометить префиксом `:global`:

```html
<style>
    p {
        /* стиль параграфа только внутри данного компонента */
        color: burlywood;
    }
    
    :global(body) {
        /* глобальный стиль */
        margin: 0;
    }
    
    div :global(strong) {
        color: goldenrod;
    }
    
    p:global(.red) {
        color: red;
    }
</style>
```
