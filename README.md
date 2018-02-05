# Area-scroll
#### (Анимированный скролинг страницы на jQuery)
***
### Вы можете скачать "Area-scroll page" Zip архивом.
[![download Area-scroll](https://archive.org/download/button-download-animated/button-download-animated.gif)](https://github.com/AndreiKaragayr/module_kai-scroll.git)
![preview Area-scroll](view-min.png "One slide")
***
### Про библиотеку:
1. Area-scroll - это библиотека, которая оживляет страницу, её задача превращать ваши картинки и контент в блоки и анимировать их.
2. Area-scroll уже Adaptive, Вам ненужно делать мобильную версию, библиотекой предусмотрена Adaptive версия.
3. В Area-scroll содержит возможность создания progress-bar, он настраиваемый, это очень удобно если вам есть чем похвастаться перед клиентами. progress-bar может быть во всех блоках.
4. В Area-scroll предусмотрено 4 вида анимации. Один из главных плюсов библиотеки, это то что можно написать свои анимации и легко подключить её. Можно использовать 1 анимацию для всех блоков или на каждом блоке разную.
5. Area-scroll настраиваемая библиотека которая содержит настройки в файле `area_scroll.js` :
  + `offset:` - скролинг появится позже на 100px
  + `transitionTnsf:` -  время скольжения progress-bar
  + `cotorSubtitle:`  -  цвет малого заголовка
  + `colorHeading:` - цвет большого заголовка
  + `colorBar:` - цвет progress-bar
  
#### В Area-scroll входит:
 - папка `css` - стили Area-scroll и стили иконок fontawesome v5
 - папка `js` - библиотеки Area-scroll и jquery v3
 - папка `img` - картинки для демо
 - `demo.html` - презентационная версия библиотеки
 - `sampel.html` - простая структура одного простого блока и одного блока с  progress-bar
***

### Технические зависимости:
  + [jquery](https://jquery.com/)
  + [fontawesome v5 icon-free](https://fontawesome.com/)


### Шаги по установке:
1. Скачать [zip архив](github.com/AndreiKaragayr/module_kai-scroll.git) или клонировать  репозиторий себе на ПК
2. Скачиваем [jquery](https://jquery.com/) - без него магия не случится :)
3. В `index.html` подключаем стили:
  + cтили иконок `<link rel="stylesheet" href="css/fontawesome-all.min.css">`
  + cтили Area-scroll `<link rel="stylesheet" href="css/area_scroll.css">`
4. В `index.html` подключаем JavaScript:
  + библиотека jquery `<script src="js/jquery-3.2.1.min.js"></script>`
  + библиотека slide Overla `<script src="js/area_scroll.js"></script>`
5. В `sample.html` можно посмотреть простую структуру

***
### Как с этим работать:

1. #### Area-scroll содержит свои классы которых нужно придерживаться:
 - `area-scroll` - родительский блок
 - `wr-image` - класс для блока картинки (потомок  area-scroll)
 - `wr-heading` - класс для блока заголовка (потомок  area-scroll)
 - `wr-text` - класс для блока описания  (потомок  area-scroll)
 - `btn-area` - класс для кнопки (потомок  area-scroll)
 - `wr-progress-bar` - класс для одного  wr-progress-bar (потомок  area-scroll). О нем чуть позже.

> Может показаться сложным, но на самом деле все просто, родительский блок с классом  `class="area-scroll"`, в нем должно быть как **минимум 2 блока**, это блок с картинкой и с классом `class="wr-image"` и какой то контект, например блок с текстом и с классом `class="wr-text"`. Все другие классы используются по мере их надобности для ваших задачи. И так что у нас вышло:
```
<div class="area-scroll ">
	<div class="wr-image"><img src="" alt=""></div>
	<div class="wr-text">Тут наш текст</div>
</div>
```
2. #### Progress-bar

Если нужно добавить progress-bar создаем блок div с классом `class="wr-progress-bar"` и с нем пишем название шкалы например _"Я знаю CSS"_. Для того чтобы указать на сколько хорошо вы знаете CSS нужно добавить атребут `data-value` со значеним, например напишем `90`. Для того чтобы указать еденицу измерения нужно добавить атребут `data-unit` со значением, например `%`. И так что у нас вышло:
```
<div class="wr-progress-bar" data-value="90" data-unit="%"> Я знаю CSS </div>
```
Мы сделали Один progress-bar, если нужно несколько, то просто добавляем еще один wr-progress-bar с нужными значениями в атребутах.

```
<div class="wr-progress-bar" data-value="90" data-unit="%"> Я знаю CSS </div>
<div class="wr-progress-bar" data-value="85" data-unit="%"> Я знаю JavaScript </div>
```
****Запоминаем:****
  + `class="wr-progress-bar"` находится внутри  `class="area-scroll"`
  + `data-value:` - это длина шкалы wr-progress-bar ( от 0 - 100 )
  + `data-unit:` - единица измерения (%, попугайчики, чашек кофе в день)

3. #### Animation
Блок с картинкой и контектом сделали и даже progress-bar сделали, но как это оживить? Для этого в Area-scroll есть 4 класса с анимацией:

1) `animation-from-side` _(картинка и текст появляются справа и слева  с эффектом отдачи)_
2) `animation-rotate` _(картинка и текст появляются справа и слева , в момент появления они вращаются на 180® друг к другу)_
3) `animation-door` _(картинка и текст появляются справа и как вертикальные шторки с эффектом отдачи)_
4) `animation-space` _(картинка и текст появляются с вращением по своей оси с резким эффектом появления)_

Анимация применяется к каждому блоку `class="area-scroll"`. Класс с анимацией добавляется рядом с классом `class="area-scroll"`. Например:
```
<div class="area-scroll animation-space">
```
*****В итоге что у нас вышло:*****
```
<div class="area-scroll  animation-space ">
	<div class="wr-image"> Наш <img> </div>
	<div class="wr-text"> Наш текст </div>
	<div class="wr-progress-bar" data-value="90" data-unit="%"> Я знаю CSS </div>
	<div class="wr-progress-bar" data-value="85" data-unit="%"> Я знаю JavaScript </div>
</div>
```
> Вот мы сделали анимированный блок `area-scroll`, мы можем добавить столько блоков сколько нам нужно и все они будут анимированные. Мы молодцы у нас все вышло. ;)
***
Вот и все что нужно для работы данной библиотеки, если что то не получилось посмотрите  `demo.html`

