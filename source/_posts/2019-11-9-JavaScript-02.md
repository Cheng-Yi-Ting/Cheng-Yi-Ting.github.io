---
title: JavaScript 物件
date: 2019-11-10
tags:
  - JavaScript

---

<img src="logo.svg" style="width:15%;">

## 物件及屬性

<strong>所有基本型別 (Primitives) 以外的值都是物件。</strong>

一個物件可以是個零至多種屬性的集合，而屬性是鍵 (key) 與值 (value) 之間的關聯。 一個屬性的「值」可以是某個基本型別，也可以是另一個物件，甚至可以是一個函數。

可以透過 <code>new</code> 關鍵字來建立一個物件實體，再替這個物件新增屬性與方法：

例如，我們可以定義一個物件為 <code>myCar</code> ，並賦予三個屬性， <code>make</code> 、  <code>model</code> 和 <code>year</code> 。

```javascript
var myCar = new Object();
myCar.make = 'Ford';
myCar.model = 'Mustang';
myCar.year = 1969;
```

或是使用大括號<code> { } </code>來建立一個物件，並且在建立物件的同時直接指定屬性至該物件內。

這種建立物件的方式稱為「物件實字 (Object literal)」。

```javascript
var myCar = {
  make : 'Ford',
  model : 'Mustang',
  year : 1969
};
```

## 屬性存取

物件的屬性可以透過<code> . </code>來進行存取：

```javascript
myCar.make;
myCar.model;
myCar.year;
```

或是可以透過<code> [ ] </code>來進行存取：

```javascript
myCar['make'];
myCar['model'];
myCar['year'];
```

存取物件沒有的屬性會顯示 <code>undefined</code> 。

```javascript
myCar.color; // undefined
```

## 新增 / 更新 屬性

新增與更新屬性的語法是一樣的，只需對屬性進行指派值的動作。

```javascript
myCar["year"]=1995;
myCar["color"]="yellow";
myCar.tire="EDITION";
```

## 屬性刪除

透過 <code>delete</code> 關鍵字來刪除，刪除後的屬性會變成 undefined：



```javascript
myCar.color="red";
myCar.color;  //red
delete myCar.color;
myCar.color;  //undefined
```

## 參考文獻

1. https://ithelp.ithome.com.tw/articles/10190962

2. https://ithelp.ithome.com.tw/articles/10193605

3. https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Guide/Working_with_Objects
