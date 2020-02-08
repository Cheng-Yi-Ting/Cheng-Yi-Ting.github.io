---
title: JavaScript 變數與資料型別
date: 2019-11-9
tags:
  - JavaScript

---

<img src="logo.svg" style="width:15%;">

<br/>

## 變數

變數是用來儲存資料和進行運算的基本單位，就像是資料的容器。

例如下面這個例子，x y z 都是所謂的變數：

```javascript
var x = 1;
var y = 2;
var z = x + y;
```

JavaScript 變數的命名有一定規則和限制：

1. 變數的開頭只能是字母、底線<code>_</code>或錢字號<code>$</code>，後面可以是英文字母、底線<code>_</code>  或是錢字號 <code>$</code> 以及數字。 
2. 大小寫有區別，例如變數 <code>test</code> 不等於變數 <code>Test</code>
3. 變數名稱不可以是[保留字](https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Reference/Lexical_grammar "Title")，否則會出現 <code style="color:#DC143C;background-color:#DCDCDC">SyntaxError</code>。

```javascript
var break = 'test';
```

<code style="color:#DC143C;background-color:#DCDCDC" >Uncaught SyntaxError: Unexpected token 'break'</code>

JavaScript 允許的字母還包含 Unicode，所以中文也可以用作變數名稱，例如：

```javascript
var 測試 = 'test';
console.log(測試);
```

## 弱型別

相較於<code>Java</code>、<code>C++</code>「強型別」語言，宣告出來的變數無法再被指派為其他型別的值，而JavaScript為「弱型別」語言，其變數擁有以下特性：

- 變數並沒有綁定任何的型態
- 變數本身無需宣告型別
- 宣告後的變數可以被自由指派為其他型別的值

## 範例

```javascript
var test = 'test';
console.log(test);    //"test"
test = 100;                   
console.log(test);    //100
```

## 變數無法被刪除

在 JavaScript 中，變數無法被刪除：

```javascript
var test = 'test';
console.log(test);    //"test"
delete test;                   
console.log(test);    //"test"  
```

如果是刪除物件的屬性，則刪除後該屬性為 undefined：

```javascript
var Employee = {
  firstname: "John",
  lastname: "Doe"
}

console.log(Employee.firstname);
// expected output: "John"

delete Employee.firstname;

console.log(Employee.firstname);
// expected output: undefined
```

## 變數的資料型別

<strong>變數沒有型別，值才有。</strong>

JavaScript 內建的型別主要可以分成基本型別 (Primitives) 與物件型別 (Object) 兩大類：

基本型別：

- string
- number
- boolean
- null
- undefined

除了上述幾種之外，都可以歸類至物件型別 (Object)。

判斷型別的方式，可以透過 typeof 運算子。

```javascript
console.log(typeof 'test');//  string
console.log(typeof 100);//  number
console.log(typeof true);//  boolean
console.log(typeof window.alert);  // 'function'
console.log(typeof null);          // 'object'
```

雖然透過 typeof 去檢查一個「函式 (function) 」的時候，會得到 "Function" 的結果，但實際上仍屬於 Object 的一種。

而 typeof null 的結果為 Object 。

## string

JavaScript 沒有 char (字元) 的概念，只有字串。字串使用 ' ' (單引號) 或是 " " (雙引號) 將文字放入其中，兩者不可混用，意即用單引號開頭的，就要用單引號收合，反過來說也是。 單引號與雙引號的使用在 JavaScript 沒有什麼差異。

### 特殊符號的處理

要在單引號內包覆單引號，或是雙引號內包覆雙引號就會出現問題：

```javascript
var name = "My name is "Ray"";
```

<code style="color:#DC143C;background-color:#DCDCDC" >Uncaught SyntaxError: Unexpected identifier</code>

可以在符號前加上 \ (跳脫字元)來解決。

```javascript
var name = "My name is \"Ray\"";
console.log(name);//My name is "Ray"
```

### 字串內容斷行

多行字串時，可以透過 \ (反斜線) 來繼續：

```javascript
var test = '這次\
連假\
要出去玩';
console.log(test);//這次連假要出去玩
```

請注意 \ 反斜線後面不能有任何字元

## number

整數或帶有小數點的數字都是數值型別
另外還有幾種特殊的數字：

- Infinity (無限大) 
- Infinity (負無限大)
- NaN (不是數值，Not a Number)。

## boolean

值只有兩種：true 以及 false，布林值通常用在判斷式，作為控制程式流程的用途。

## Null

null 在 JavaScript 中表示一個空值，變數要經過宣告並賦予 null ，才會形成 null 型態。

```javascript
var test = null;
```

## undefined

變數在初始的時候未給予任何值，宣告 test 時因為沒有賦予任何值所以是 undefined，如果先定義 test 為 100 ; 接著再把 test 設為 undefined，我們會發現 test 又再次變成了undefined了。

```javascript
var test; 
console.log(test);//undefined
test=100;
test=undefined;
if(test===undefined){
  console.log("test is undefined.");
}
```

## 參考文獻

1. https://ithelp.ithome.com.tw/articles/10190873
