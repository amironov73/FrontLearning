### Emmet

Emmet -- технология ускорения набора HTML/XML-страниц. Поддерживается многими IDE (включая Visual Studio и JetBrains) и редакторами (включая Sublime Text).

* **вложенность**: `div>ul>li` означает "создать div, в нём ul, а в нём li".

* **братья/сестры**: `div>span+em` означает "создать div, в нём span и em (сразу за span)".

* **вверх**: `div>span^p` означает "создать div, в нём спан, а после div создать p".

* **умножение**: `ul>li*5` означает "создать ul, а в нём 5 li". Умножений может быть много: `ul*3>li*5` означает "создать 3 ul, а в каждом из них 5 li".

* **группировка**: можно группировать элементы: `div>(header>ul>li*2>a)+footer>p`. Группировка может быть вложенная: `(div>dl>(dt+dd)*3)+footer>p`.

* **идентификатор**: `div#content` разворачивается в `<div id="content"></div>`.

* **класс**: `div.content` разворачивается в `<div class="content"></div>`. Классов может быть несколько: `div.class1.class2`. Класс и идентификатор могут встречаться одновременно.

* **нумерация элементов**: `ul>li.item$*5` разворачивается в:

```html
<ul>
    <li class="item1"></li>
    <li class="item2"></li>
    <li class="item3"></li>
    <li class="item4"></li>
    <li class="item5"></li>
</ul>
```

`$$` превращается в `01, 02, ...`.

* **произвольные атрибуты**: `td[title="Hello world!" colspan=3]`. Можно не задавать значения атрибутов, тогда для них будет подставлена пустая строка: `td[colspan title]`.

* **текст**: `a{Click me}` означает `<a href="">Click me</a>`.

* **подразумеваемые теги**: `.content` разворачивается в `<div class="content"></div>`.

* **Lorem ipsum**: `lorem` или `lipsum` разворачиваются в `Lorem ipsum dolor sit amet...`. Можно так: `p*4>lorem` или даже так: `ul.generic-list>lorem10.item*4`.

