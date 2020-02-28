---
title: 變更 Visual Studio Code 介面語系為中文
date: 2019-11-5
tags:
  - IDE
  - VSCode
---

本篇介紹如何修改Visual Studio Code為繁體中文，其他不同語系修改方式皆相同，只要安裝不同語系插件即可。



* 點擊Extension圖示(或是按下<code>ctrl+shift+X</code>)
* 在搜尋欄位輸入 Chinese(Traditional)搜尋中文化套件
* 點擊 install 按鈕安裝

<img src="2019-11-5-Visual-Studio-Code-Chinese-1.png" >

* 安裝完成後按下快捷鍵<code>ctrl+shift+p</code>開啟搜尋列
* 輸入Configure Display Language

<img src="2019-11-5-Visual-Studio-Code-Chinese-2.png" >

* 開啟 locale.json 檔進行設定
* 把 "locale":"en" 的 en 改成 zh-TW 後存檔

<img src="2019-11-5-Visual-Studio-Code-Chinese-3.PNG" >

* 重啟Visual Studio Code
* 完成繁體中文語系設定

### 參考文獻

1. https://medium.com/mr-brown/ide-visual-studio-code-%E4%B8%AD%E6%96%87%E5%8C%96%E6%95%99%E5%AD%B8-ff0abd789608
