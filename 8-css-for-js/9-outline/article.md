# Свойство "outline"

Свойство `outline` задаёт дополнительную рамку вокруг элемента, *за пределами его CSS-блока*. Поддерживается во всех браузерах, IE8+.
[cut]
Для примера, рассмотрим его вместе с обычной рамкой `border`:

```html
<!--+ autorun height=60 -->
<div style="border:3px solid blue; *!*outline: 3px solid red*/!*">
 Элемент
</div>
```

<ul>
<li>**В отличие от `border`, рамка `outline` не участвует в блочной модели CSS.** Она не занимает места и не меняет размер элемента. Поэтому его используют, когда хотят добавить рамку без изменения других CSS-параметров.
</li>
<li>Также, в отличие от `border`, рамку `outline` можно задать только со всех сторон: свойств `outline-top`, `outline-left` не существует.</li>
</ul>

Так как `outline` находится за границами элемента -- **`outline`-рамки соседей могут перекрывать друг друга**:

```html
<!--+ height=60 autorun -->
<div style="*!*outline: 3px solid green*/!*">
 Элемент
</div>
<div style="*!*outline: 3px solid red*/!*">
 Элемент
</div>
```

В примере выше верхняя рамка нижнего элемента находится на территории верхнего и наоборот.

Все браузеры, кроме IE9-, также поддерживают свойство `outline-offset`, задающее отступ `outline` от внешней границы элемента:

```html
<!--+ autorun height=60  no-beautify -->
<div style="border:3px solid blue; outline: 3px solid red; outline-offset:5px">
 Везде, кроме IE9-, между рамками будет расстояние 5px
</div>
```

Ещё раз заметим, что основная особенность `outline` -- в том, что при наличии  `outline-offset` или без него -- он не занимает места в блоке.

Поэтому его часто используют для стилей `:hover` и других аналогичных, когда нужно выделить элемент, но чтобы ничего при этом не прыгало.