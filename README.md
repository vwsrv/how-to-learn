# ПЕРВЫЙ ПРОЕКТ В РАМКАХ ОБУЧЕНИЯ НА ПЛАТФОРМЕ Яндекс.Практикум
## Текущий проект выполнялся в два этапа:
> Спринт 1. (flexbox, позиционирование, БЭМ: структура)
> Спринт 2. (HTML: видео, iframe, embed, API, БЭМ: пути к файлам)

`!NB!` Текущий проект выполнен без кроссбраузерной адаптации.

1. Каждый "шаг" в написании кода фиксировался в комитах.
2. Все исправления в рамках код-ревью зафискированы.

## PAGE
```css
/*были заданы следующие параметры страницы*/
.page {
    min-width: 1100px;
    max-width: 1600px;
    margin: 0 auto;
    font-family: "Helvetica Neue", Arial, sans-serif;
  }
```
## HEADER
```css
/*Использовалось flex позиционирование элементов*/
header {
    display: flex;
}
/*Для стиллизации элементов были использованы keyframes*/
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
```

PS

```
[Результат:]
![HEADER](https://github.com/vwsrv/how-to-learn/vwsrv/how-to-learn/blob/main/images/README-images/HEADER.png)
```

## TECHNIQUES

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
