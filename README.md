# Яндекс.Практикум

# Задачи:
- Изучить основы иерархии HTML элементов и тегов. Начать знакомство с Веб-разработкой в целом.
- Изучить основы CSS cnbkkbpfwbb элементов.
- Изучить flexbox позиционирование элементов. Изучить позиционирование элементов в целом.
- Усовить методологию БЭМ для корректного наименования классов, с целью последующего переиспользования элементов.
- Изучить методологию БЭМ для корректного размещения файловой структуры сайта: блоков, страниц, и др.
- Ознакомиться с методами использования HTML-элементов: видео, iframe, embed, API.
- Изучить основы анимации элементов с помощью свойств CSS.

# Цели:
- Апробация полученных теоретических и практических навыков на примере реального ТЗ.

# Проект: "Научиться учиться"

`!NB!` Текущий проект выполнен без кроссбраузерной адаптации.

> Каждый "шаг" в написании кода фиксировался в комитах.

## HTML
### Структура проекта представлена следующим образом:
1. header
2. content, который содержит секции:
- description
- techniques
- video
- oakley
- feynman
- digits
- kaufman
- resources
3. footer


## CSS
### СЕКЦИЯ PAGE
```css
/*были заданы следующие параметры страницы*/
.page {
    min-width: 1100px;
    max-width: 1600px;
    margin: 0 auto;
    font-family: "Helvetica Neue", Arial, sans-serif;
  }
```
## СЕКЦИЯ HEADER
```css
/*Использовалось flex позиционирование элементов*/
header {
    display: flex;
}
/*Для анимации элемента __square-pic были использованы свойства keyframes*/
@keyframes rotation {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }
  
.rotation {
    animation: rotation 20s linear infinite 0s;
}

/*Блок logo был стиллизован с учетом правил БЭМ для его последующего переиспользованиея в блоке footer*/
.logo {
    width: 228px;
    height: 32px;
}

/*Элемент header - __main-illustration спозиционирован абсолютно, для этих целей использовалось свойство z-index */
.header__main-illustration {
    position: absolute;
    z-index: 1;
    width: 765px;
    height: 608px;
    bottom: 0;
    right: 0;
}

/*Элемент header - __link анимирован при наведении на него указателя мыши*/
.header__link {
    text-decoration: none;
    color: #2f80ed;
    transition: 0.2s;
  }

.header__link:hover {
    opacity: 0.8px;
    text-shadow: 3px 3px 3px rgba(0,0,0, 0.2);
    transition: ease-in 0.2s;
}
```
Результат:
![HEADER](https://github.com/vwsrv/how-to-learn/blob/main/images/README-images/HEADER.png)

## СЕКЦИЯ DESCRIPTION
```css
/*Использовалось flex позиционирование элементов*/
.description {
    display: flex;
    justify-content: center;
    margin: 0;
    padding: 0;
}
/*С учетом методологии БЭМ, с целью последующего переиспользования, была осуществлена стиллизация элементов two-columns*/
/*Для самого блока были заданы следующие параметры (подробнее см. в репозитории*/
.two-columns {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin-top: 100px;
    width: 80%;
  }
```
Результат:
![HEADER](https://github.com/vwsrv/how-to-learn/blob/main/images/README-images/TWO-COLUMNS.png)


## СЕКЦИЯ TECHNIQUES

```css
/*Для этой секции были определены следующие параметры*/
.techniques {
    width: 80%;
    margin: 100px auto 100px auto;
}
/*В рамках этой секции было использовано несколько блоков: section-title, section-subtitle, cards*/
/*Для стиллизации применялась методология БЭМ, с целью их последующего переиспользования*/
.section-subtitle {
    margin: auto;
    text-align: center;
    margin-top: 20px;
    max-width: 60%;
    line-height: 34px;
    font-size: 24px;
    font-weight: normal;
  }

  .section-title {
    margin: auto;
    text-align: center;
    padding: 0;
    line-height: 1.15;
    font-size: 60px;
    font-weight: 600;
    max-width: 60%;
  }  
/*Блок и элементы cards позиционировались при помощи свойств grid*/
.cards {
    display: grid;
    grid-template-columns: repeat(3, 235px);
    justify-content: space-between;
    margin: auto;
    width: 920px;
    text-align: center;
}
/*Поскольку согласно Брифа, третий элемент сетки должен был быть прижат к краю блока, использовался псевдокласс*/
/*для элемента cards*/
.cards__item {
    margin-right: 100px;
    padding: 0;
    width: 235px;
    margin: 0;
    list-style-type: none;
  }
  
  .cards__item:nth-child(3) {
    margin-right: 0;
}
```
Результат:
![TECHNIQUES](https://github.com/vwsrv/how-to-learn/blob/main/images/README-images/TECHIQUES.png)


## СЕКЦИЯ VIDEO

```css
/*Для позиционирования использовались свойства flexbox*/
.video {
  display: flex;
  flex-direction: column;
  margin-top: 100px;
  }

/*В рамках этой секции были переиспользованы блоки: section-title, section-subtitle (см. выше)*/
/*Элементы блока __iframe анимированы при наведении на них указателя мыши*/
```css
.video__iframe {
  margin-right: 20px;
  width: 515px;
  height: 316px;
  transition: 0.2s;
  border: 0;
}

.video__iframe:hover {
  transform: scale(105%);
  transition: ease-in 0.2s;
}
```
Результат:
![VIDEO](https://github.com/vwsrv/how-to-learn/blob/main/images/README-images/VIDEO.png)

## СЕКЦИЯ OAKLEY

```css
/*Для секции были заданы следующие свойства*/
.oakley{
    padding-top: 60px;
    background-color: #f2f2f2;
    display: flex;
    justify-content: center;
}
/*В рамках этой секции были переиспользованы блоки two-columns (см. выше)*/

Результат:
![OAKLEY](https://github.com/vwsrv/how-to-learn/blob/main/images/README-images/OAKLEY.png)

## СЕКЦИЯ FEYNMAN

```css
/*Для секции были заданы следующие свойства. Изображение является фоновым*/
/*Для того, чтобы feynman-subtitle, feynman__link были спозиционированы на одном уровне, блоку*/
/*feynman был указан внутренний верхний отступ, а у блока two-columns был убран нижний отступ*/
.feynman {  
    padding-top: 98px;
    min-height: 890px;
    margin-bottom: 100px;
    box-sizing: border-box;
    background-image: url("../../images/feynman.png");
    background-size: 867px 637px;
    background-repeat: no-repeat;
    background-position: left bottom;
    background-color: #f2f2f2;
    position: relative;
  }
/*В рамках этой секции были заданы собственные элементы: feynman-title, feynman-subtitle, feynman__link */
```
Результат:
![FEYNMAN](https://github.com/vwsrv/how-to-learn/blob/main/images/README-images/feynman.png)

## СЕКЦИЯ DIGITS

```css
/*Для секции были заданы следующие свойства.*/

.digits {
    height: 100%;
    padding-bottom: 100px;
  }

/*В рамках этой секции, с учетом методологии БЭМ были использованы элементы блока table*/
/*У элементу __cell также был присвоен модификатор _theme для последующего переиспользования в блоке kaufman*/
.table__cell {
    margin-top: 60px;
    width: 250px;
}

.table__cell_theme_dark {
    width: 200px;
    color: white;
    margin-right: 0;
    margin-top: 80px;
}
```  
Результат:
![DIGITS](https://github.com/vwsrv/how-to-learn/blob/main/images/README-images/DIGITS.png)

## СЕКЦИЯ KHAN

```css
/*Для секции были заданы следующие свойства.*/

.khan {
    background-color: #f2f2f2;
    padding-top: 105px;
  }

/*Первоначально с элементом __book-pic возникали проблемы, картинка была растянута по ширине*/
/*Указанная выше проблема решилась свойствами object-fit и object-position*/
.khan__book-pic {
  width: 620px;
  height: 608px;
  margin-right: 48px;
  object-fit: cover;
  object-position: top;
}
```
Результат:
![KHAN](https://github.com/vwsrv/how-to-learn/blob/main/images/README-images/khan.png)

## СЕКЦИЯ KAUFMAN

```css
/*Для секции были заданы следующие свойства.*/

.kaufman {
    position: relative;
    padding-bottom: 90px;
    padding-top: 90px;
    background-color: #1f1f1f;
    color: white;
    overflow: hidden;
    z-index: 1;
  }

/*Элемент секции __triangle анимирован при помощи keyframes "rotation" (см. выше)*/
/*Для того, чтобы элемент __triangle корректно отображался в блоке kaufman, ему был присвоен отрицательный z-index*/
.kaufman__triangle {
    width: 877px;
    height: 877px;
    position: absolute;
    background-image: url("../../../images/kaufman-triangle.svg");
    background-size: cover;
    right: -210px;
    top: 0;
    z-index: -1;
}
/*В текущей секции были переиспользованы элементы блока table и модификатор его элемента _theme_dark*/
```
Результат:
![KAUFMAN](https://github.com/vwsrv/how-to-learn/blob/main/images/README-images/KAUFMAN.png)

## СЕКЦИЯ RESOURCES

```css
/*Для секции были заданы следующие свойства.*/
.resources {
    padding-top: 100px;
    margin-bottom: 217px;
}  

/*Элемент блока resources: __logo были анимирован при помощи свойств CSS*/
/*__logo*/
.resources__logo {
    margin: 0;
    padding: 0;
    width: 270px;
    height: 38px;
    object-fit: fill;
    transition: 0.5s;
  }

.resources__logo:hover {
    transform: scale(130%);
    transition: ease-in-out 0.2s;
}
```
Результат:
![RESOURCES](https://github.com/vwsrv/how-to-learn/blob/main/images/README-images/RESOURCES.png)

## СЕКЦИЯ FOOTER

```css
/*Для секции были заданы следующие свойства.*/
.footer {
    display: flex;
    min-height: 350px;
    width: 100%;
    background-color: #1f1f1f;
    color: white;
}
/*Элемент блока footer: __social-icon является частью ссылки, при взаимодействии с которым происходит переход на сторонний ресурс*/
```html 
...
 <nav class="footer__column-links">
              <a href="#" class="footer__column-link">
                <img src="./images/youtube_color_white.svg" alt="Ютуб" class="footer__social-icon">YouTube</a>
              <a href="#" class="footer__column-link">
                <img src="./images/vk_color_white.svg" alt="ВК" class="footer__social-icon">Вконтакте</a>
              <a href="#" class="footer__column-link">
                <img src="./images/tiktok_color_white.svg" alt="Тикток" class="footer__social-icon">TikTok</a>
            </nav>
...
```
Результат:
![FOOTER](https://github.com/vwsrv/how-to-learn/blob/main/images/README-images/footer.png)

## Документация, в соответствии с которой производилась верстка:
- https://code.s3.yandex.net/web-developer/project-1/sprint-2-brief.pdf
- https://code.s3.yandex.net/web-developer/project-1/sprint-1-brief.pdf
