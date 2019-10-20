### Отображение (свойство display)

Свойство display Bootstrap позволяет записать удобно в виде `d-{value}` (для xs) или `d-{breakpoint}-{value}` (для sm, md, lg и xl). Здесь `value` может быть:

* none
* inline
* inline-block
* block
* table
* table-cell
* table-row
* flex
* inline-flex

Примеры:

```html
<div class="d-inline p-2 bg-primary text-white">d-inline</div>
<div class="d-inline p-2 bg-dark text-white">d-inline</div>
<span class="d-block p-2 bg-primary text-white">d-block</span>
<span class="d-block p-2 bg-dark text-white">d-block</span>
```

Можно прятать элементы страницы для определенных разрешений экрана:

```html
<div class="d-none d-sm-block">Этот текст не видно в xs.</div>
<div class="d-block d-sm-none">Этот текст видно только в xs.</div>
```

#### Отображение на бумаге

Аналогично для распечатки:

* d-print-none
* d-print-inline
* d-print-inline-block
* d-print-block
* d-print-table
* d-print-table-row
* d-print-table-cell
* d-print-flex
* d-print-inline-flex

