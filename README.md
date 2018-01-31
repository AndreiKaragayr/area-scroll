# Area_scroll (modul)
## Анимированный скролинг страницы на jQuery.

[This repository](https://github.com/AndreiKaragayr/module_kai-scroll.git)

![One slide](img/overlap-slide-2-1.jpg "One slide")

Фишка слайдера:
1. Различная анимация для скролинга.
  + 4 встроенные анимации
  + можно дописать свои
2. Настраиваемы progress-bar.
  + неограниченное количество progress-bar
  + меняется цвет, счетчики, все анимируется по заданым критериям
3. Настройка модуля.
  + цвета заголовков
  + время скольжения progress-bar
4. Мобильная версия.
***
### Как установить:
Подключить Css:
```
	<link rel="stylesheet" href="css/font-awesome.min.css"> // Модуль использует иконки awesome
	<link rel="stylesheet" href="css/area_scroll.css">  // стили модуля
```
Ваш HTML:
```
<div class="area-scroll animation-space">
	<div class="wr-image"> Ваша Картинка </div>
	<div class="wr-heading"> Ваш Заголовок </div>
	<div class="wr-text"> Ваш текст </div>
</div>
```

Подключить JavaScript:
```
<script src="js/area_scroll.js"></script>
```
#### Монуал:
Прописаны 4 вида анимации:
1. animation-from-side
2. animation-rotate
3. animation-door
4. animation-space
Название выбраной анимации вставляется в Код рядом с area-scroll:
```
<div class="area-scroll animation-from-side">
...
```
Для кнопки нужно прописать свой класс btn-area:

```
...
  <div class="wr-text"> Ваш текст </div>
  <a href="#" class="btn-area">Read more</a>
</div>
```
Так вы получите анимированую кнопку, которую можно дополнять стилями.

