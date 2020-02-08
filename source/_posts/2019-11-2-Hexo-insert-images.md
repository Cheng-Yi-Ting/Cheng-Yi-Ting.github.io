---
title: 如何在 Hexo 文章中插入本地圖片
date: 2019-11-3
tags:
  - Hexo
---

## Hexo文件設定

將 Hexo 文件裡面的<code> _config.yml </code>的此參數設定為true

```
post_asset_folder: true 
```

這個功能目的是在你使用<code>Hexo new 文章名稱</code>，建立一篇新的文章。文章相對路徑為<code>\source\_posts</code>，例如我輸入以下指令：

```
 Hexo new test 
```

目錄下就會生成一個<code>test.md</code>文件和一個與文章同名的資料夾，可以用來放置該文章相關的所有資源，例如圖片、附件等等。

<img src="2019-11-2-Hexo-insert-images-1.PNG"  align=center >

## 安裝 hexo-asset-image 套件

安裝 hexo-asset-image 圖片路徑轉換套件，使用<code>npm</code>進行安裝：

```
npm install https://github.com/CodeFalling/hexo-asset-image --save
```

## 插入圖片

```
![當圖片無法顯示時出現的文字](圖片檔名.PNG)
```

也支援使用 HTML 的<code>img</code>標籤，可以更改圖片高度、寬度等設定。

```
<img src="xx.png" width = "100%" height = "100%">
```

### 參考文獻

1. http://etrd.org/2017/01/23/hexo%E4%B8%AD%E5%AE%8C%E7%BE%8E%E6%8F%92%E5%85%A5%E6%9C%AC%E5%9C%B0%E5%9B%BE%E7%89%87/
2. https://blog.csdn.net/Sugar_Rainbow/article/details/57415705
