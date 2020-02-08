---
title: 為什麼 height:100 沒有作用?
date: 2019-11-04
tags:
  - HTML
  - CSS
---

## 設定 height:100% 元素沒反應!?

當設計一個頁面的時候，你設置了一個div元素，希望元素能佔滿整個瀏覽器窗口，最自然的做法，你會給這個div添加 <code>width:100px;</code> <code>height:100px;</code> 的css屬性。然後你會發現，這個元素的寬度會擴展到整個瀏覽器窗口，但是高度卻沒有起任何作用，那為什麼height:100%會無法作用呢？

按照常理推斷，當我們用CSS的height屬性定義一個元素的高度時，這個元素應該要按照設定在瀏覽器的縱向空間裡擴展相應的空間距離，例如：一個div元素的height為100px;，那它應該在頁面的豎向空間裡佔滿100px的高度才對。

根據W3C的規範，百分比的高度在設定時需要根據這個元素的父元素容器的高度。所以，如果你把一個div的高度設定為height:50%;，而它的父元素的高度是100px時，那麼，這個div的高度應該是50px。

## 瀏覽器寬度和高度

瀏覽器在計算寬度時會考慮瀏覽器窗口的打開寬度。如果不給寬度設定任何值，那瀏覽器會自動將頁面內容填滿整個橫向寬度。

但是高度的計算方式完全不一樣。事實上，瀏覽器根本就不計算內容的高度，除非內容超出了視窗範圍(導致滾動條出現)；否則，瀏覽器就會簡單的讓內容往下堆砌，頁面的高度根本就無需考慮。

當你讓一個元素的高度設定為百分比高度時，無法根據獲取父元素的高度，也就無法計算自己的高度，所以瀏覽器不會對這個值有任何的反應。

## 範例

設定元素 <code>width:100px;</code> <code>height:100px;</code>

```html
<!DOCTYPE html>
<body>
  <div style="width:100%;height:100%;background-color:green;">
    <p>
      元素設定高度為100%
    </p>
  </div>
</body>
</html>
```

<img src="2019-11-4-height-100percent-1.PNG" >

現在你給了這個div的高度為100%，它有兩個父元素 <code>&lt;body&gt; </code>和 <code>&lt;html&gt;</code> ；為了讓div的百分比高度起作用，需要設定這兩個屬性的高度。

```html
<!DOCTYPE html style="height:100%">
<body style="height:100%">
  <div style="width:100%;height:100%;background-color:green;">
    <p>
      元素設定高度為100%
    </p>
  </div>
</body>
</html>
```

從這個範例中你可以發現， <code>height:100%; </code>生效了

<img src="2019-11-4-height-100percent-2.PNG" >

### 參考文獻

1. http://www.webhek.com/post/css-100-percent-height.html
2. https://segmentfault.com/a/1190000012707337
