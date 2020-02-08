---
title: 使用 HTML+CSS 製作簡易名片
date: 2019-11-5
tags:
  - HTML
  - CSS
---

程式碼同步於此連結：
[使用 HTML+CSS 製作簡易名片](https://codepen.io/BobbyLashley/pen/vWVjye "Title")

使用*{ }選取器取消網頁所有物件的間距為0：

```css
* {
  font-family : 微軟正黑體;
  margin: 0;
  padding: 0;
}
```

為了使div元素的height為整個瀏覽器窗口高度，需先將其父元素設定為100%，這樣子元素高度才會起作用，也就是<code>width:100%;</code> <code>height:100%;</code>

```css
html,body{
  width : 100%;  
  height : 100%;
}
```

延伸閱讀：
[為什麼 height:100% 沒有作用?](https://cheng-yi-ting.github.io/2019/11/05/2019-11-4-height-100percent/ "Title")

設定背景為綠色，頁面最上和最下留30px的黑邊；使用box-sizing屬性來讓元素的內距和邊框不會增加元素本身的寬度：

## CSS

```css
body{
  background-color : #A9CEAE;
  border-top : solid 30px #3B3E3C;
  border-bottom : solid 30px #3B3E3C;
  box-sizing : border-box;
}
```

## HTML

```html
<body>
    <div class="mark">NEVER<br> &nbsp&nbsp&nbsp&nbsp&nbspSTOP
    </div>
</body>
```

<img src="2019-11-4-Business-Card-1.png" >

## CSS

  以下是包含各個元素的CSS設定

```css
.mark {
    font-size: 230px;
    position: absolute;
}

.namecard {
    width: 500px;
    height: 300px;
    border-radius: 15px 5px 5px 15px;
    margin: auto;
    margin-top: 100px;
    padding-left: 100px;
    background-color: #3B3E3C;
    color: white;
    letter-spacing: 1px;
    box-shadow: 25px 25px 15px -20px rgba(0, 0, 0, 0.5);
    position: relative;
}

.namecard h2 {
    font-size: 30px;
}

.namecard h2 span {
    font-size: 17px;
    font-weight: 300;
}

.namecard h5 {
    font-size: 15px;
    letter-spacing: 1px;
    font-weight: 300;
}

.namecard p {
    font-size: 15px;
    font-weight: 300;
}

.hr1 {
    border: 2px solid gray;
    box-shadow: 0px 2px 5px black;
}

.gap {
    width: 35px;
    height: 240px;
    right: 540px;
    top: 30px;
    position: absolute;
    background-color: #A9CEAE;
    border-radius: 15px 0px 0px 15px;
    box-shadow: inset 25px 20px 20px -20px rgba(0, 0, 0, 0.5);
}

.vline {
    position: absolute;
    height: 299px;
    right: 520px;
    border: solid 2px gray;
}

.screw {
    border: solid 2px gray;
    border-radius: 100%;
    position: absolute;
    width: 10px;
    height: 10px;
    /*   background-color : gray; */
}

.screw1 {
    right: 500px;
    top: 15px;
}

.screw2 {
    right: 500px;
    top: 280px;
}
```

## h5,h2,p CSS設定

```css
h5 {
    display: block;
    font-size: 0.83em;
    margin-block-start: 1.67em;
    margin-block-end: 1.67em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-weight: bold;
}

h2 {
    display: block;
    font-size: 1.5em;
    margin-block-start: 0.83em;
    margin-block-end: 0.83em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-weight: bold;
}

p {
    display: block;
    margin-block-start: 1em;
    margin-block-end: 1em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
}
```

## HTML

```html
<body>
    <div class="mark">NEVER<br> &nbsp&nbsp&nbsp&nbsp&nbspSTOP
    </div>
    <div class="namecard">
        <div class="gap"></div>
        <div class="vline"></div>
        <div class="screw screw1"></div>
        <div class="screw screw2"></div>
        </br>
        <h2>鄭亦渟
            <span>Cheng Yi Ting</span>
        </h2>
        <h5>國立中正大學-資訊工程學系</h5>
        <hr class="hr1" />
        <p>"Opportunity seldom knocks twice."<br>Love to try anything I haven't experienced.</p>
    </div>
</body>
```

<img src="2019-11-4-Business-Card-2.PNG" >
