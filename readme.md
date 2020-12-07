# Порядок верстки сраницы

Практическая работа курса web-разработчика, Skill Factory

ноябрь 2020

---
### Шрифты

Подклчение шрифтов макета Roboto и еще одного

```<link rel="preconnect" href="https://fonts.gstatic.com"> 
<link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Revalia&family=Roboto&display=swap" rel="stylesheet">
```

Подключение в CSS группы шрифтов через:

```font-family: 'Revalia', cursive;```

```font-family: 'Roboto', sans-serif;```

---
### Структура кода

**Основная структура** построения разметки должна быть такая:

```
<section>
        <div class="container">
            <div class="row">
                <div class="col">
```
и всякий другой контент, но в колонках col
```

           </div>
        </div>
    </section>
```
Эта структура повторяться по мере верстки столько раз, сколько это требуется.

**Колонки** должны являться прямыми потомками row, и row нужен только для того, чтобы включать в себя row, должен быть внутри контейнера. 

***Контейнер*** *оборачивает весь контент и контролирует ширину блока.*

Обратите внимание, что у строк (rows) есть отрицательные правые и левые внешние отступы в -15px. Внутренний отступ контейнера в 15px используется для пресечения срабатывания отрицательных внешних отступов в строке контейнера. Это делается для равномерного выравнивания по граням в шаблоне. *Если вы не поместите строку (row) в контейнер, то она будет выходить за пределы своего контейнера, вызывая нежелательные горизонтальные прокрутки.*

Строк в контейнере может быть несколько. Внутри строк должны располагаться колонки, в строку нельзя сразу ставить контент.

**У .row всегда display: flex;.** Колонки в строке одинаковой высоты. Соответственно, выравнивание можно осуществлять с помощью flex и auto-margin.

Поскольку у нас на странице 12 колонок, то мы можем регулировать ширину, которую займет нужный контент. Например, кнопка может занимать две колонки, а изображение — 4 колонки. Чуть ниже мы это рассмотрим.

Также возможно менять порядок элементов, применяя свойство order.

```<div class="col order-1"> </div>
     <div class="col order-2"> </div>
```

Колонки можно смещать, скажем, нужный контент должен располагаться, начиная с 3 колонки, тогда мы это укажем:

```<div class="col offset-2"></div>
```

Можно сделать вложенность колонок. Для этого нужно добавить новый класс .row и набор колонок .col внутри существующей колонки.

```<div class="container">
        <div class="row">
          <div class="col-sm-9">
            Level 1: .col-sm-9
            <div class="row">
              <div class="col-8 col-sm-6">
                Level 2: .col-8 .col-sm-6
              </div>
              <div class="col-4 col-sm-6">
                Level 2: .col-4 .col-sm-6
              </div>
            </div>
          </div>
        </div>
      </div>
```

[Здесь](https://bootstrap-4.ru/docs/4.5/layout/grid/#auto-layout-columns) написано, как с этим работать, что это все значит, как правильно написать.

### Bootstrap connect

```<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css"
        integrity="sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk" crossorigin="anonymous">
    <link rel="stylesheet" href="bootstrap.js">
```

и добавить в конце секции "тело"

```     <!-- JS, Popper.js, and jQuery -->
<script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js" integrity="sha384-OgVRvuATP1z7JjHLkuOU7Xw704+h835Lr+6QL9UvYjZE3Ipu6Tp75j7Bh/kR0JKI" crossorigin="anonymous"></script>
```
