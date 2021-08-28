### Передача контекста между компонентами

Иногда нам нужно разделять объекты, методы, классы между несколькими компонентами. Один из способов добиться этого - применить пару стандартных методов `setContext`/`getContext`.

`App.svelte`:

```html
<script>
	import { setContext } from 'svelte';
	import Button from './Button.svelte';
	
	setContext('increment', increment);
	
	let count = 0;
	function increment() {
		count += 1;
	}
</script>

{count}
<Button/>
```

`Button.svelte`:

```html
<script>
	import { getContext } from 'svelte';
	
	let increment = getContext('increment');
</script>

<button on:click={increment}>
	Press me
</button>
```

Конечно, можно было бы достичь такого же результата с помощью явной передачи свойства в компонент. Контекст - лишь один из множества способов, какой из них выбрать - решает разработчик.
