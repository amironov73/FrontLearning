### Layout

#### Одна колонка по центру

```html
<div class="container">
    <div class="row justify-content-center">
        <div class="col-md-6"></div>
    </div>
</div>
```

#### Две колонки

```html
<div class="container">
    <div class="row">
        <div class="col-sm-6"></div>
        <div class="col-sm-6"></div>
    </div>
</div>
```

Можно не задавать ширину колонок:

```html
<div class="container">
    <div class="row">
        <div class="col"></div>
        <div class="col"></div>
    </div>
</div>
```

#### Три колонки

```html
<div class="container">
    <div class="row">
        <div class="col-sm-4"></div>
        <div class="col-sm-4"></div>
        <div class="col-sm-4"></div>
    </div>
</div>
```

Можно задать сдвиг колонки:

```html
<div class="container">
    <div class="row">
        <div class="col-sm-offset-4 col-sm-4"></div>
        <div class="col-sm-4"></div>
    </div>
</div>
```

#### Вложенные колонки

```html
<div class="container">
    <div class="row">
        <div class="col-sm-6">
            <div class="row">
                <-- Вложенный грид состоит из 12 колонок -->
                <div class="col-sm-6"></div>
                <div class="col-sm-6"></div>
            </div>
        </div>
        <div class="col-sm-6"></div>
    </div>
</div>
</div>
```
