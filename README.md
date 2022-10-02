# Drag-Drop
_______________
## Это пример, показывающий реализацию простого метода Drag&Drop с использованием JavaScript, HTML, CSS

### Основная задача: Реализация движения объектов на сайте с использованием JS. При перемещении, объект должен оставаться в определенном контейнере. Добавление стилизации.


```html
//Данный код, показывает HTML структуру проекта 
<body>
    <div>
      <div class="row">
        <div class="col-header start">Начать</div>
        <div class="col-header progress">В процессе</div>
        <div class="col-header done">Готовы</div>
      </div>

      <div class="row">
        <div class="placeholder">
          <div class="item" draggable="true">Перетащи меня</div>
        </div>
        <div class="placeholder"></div>
        <div class="placeholder"></div>
      </div>
    </div>
    <script src="/app.js"></script>
  </body>
```

```js
//Тут к каждому контейнеру мы добовляем слушателя при определенных ситуациях 
for (const placeholder of placeholders) {
  placeholder.addEventListener("dragover", dragover);
  placeholder.addEventListener("dragenter", dragenter);
  placeholder.addEventListener("dragleave", dragleave);
  placeholder.addEventListener("drop", drop);
}

```

```js
// В данном блоке представленны методы, использующиеся при различных событиях

// Начать движение объекта
function dragstart(event) {
  event.target.classList.add("hold");
  setTimeout(() => event.target.classList.add("hide"), 0);
}

// Завершить движение обхекта
function dragend(event) {
  event.target.className = "item";
}

function dragover(event) {
  event.preventDefault();
}

// Зафиксировать объект
function dragenter(event) {
  event.target.classList.add("hovered");
}

// Отпустить объект
function dragleave(event) {
  event.target.classList.remove("hovered");
}

// Отпустить объект
function drop(event) {
  event.target.append(item);
  event.target.classList.remove("hovered");
}

```


## Результат работы сайта:
### Запуск проекта
![resualt-1](https://sun9-33.userapi.com/impg/AmSPK4gewBNWV6ZBTK12QzcCbH6VaBt-DQqQYQ/kzg3b1ufn1E.jpg?size=657x238&quality=96&sign=a1c8b1ab13c2c16a4907624680b2b967&type=album)
### Захват объекта
![resualt-2](https://sun9-42.userapi.com/impg/dL03DEQvCEwrIpkq8_dPJ0zjTSKaZMToSfjv9Q/sdJjmUSeV-I.jpg?size=620x248&quality=96&sign=95d2aaea5345a60823c32dce00aee751&type=album)
### Реализация Drag&Drop
![resualt-3](https://sun9-77.userapi.com/impg/zpWRWkElq-MFoiZnMBD0ygwsr5SB7ABfbbRSCg/vYZk64zft2U.jpg?size=614x227&quality=96&sign=b589734bd12ecd5ded90f16dcab15f23&type=album)
