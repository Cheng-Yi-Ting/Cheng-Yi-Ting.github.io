---
title: Hexo 備份
date: 2020-02-08
tags:

- Hexo
- GitHub
- Git
---



我們在使用 Hexo 網誌框架時，會事先在 GitHub 上新增 GitHub Pages 來完成 Blog 搭建，透過輸入  `hexo g -d`  進行部署，所產生的是靜態網頁並發布在網站上，不過卻沒有備份到 .md 檔案，這樣我們辛辛苦苦寫的文章卻沒有備份到。所以本篇將會說明如何將我們所撰寫的文章，及相關的配置設定一同備份至 GitHub ，這樣當原始檔案遺失時才有機會進行還原，而不是只有 Hexo 所產生出的靜態檔案。

# 

<img src="2020-02-08-HexoBackup-1.PNG" style="width:100%;">

每次透過  `hexo g -d`  後  `master`  會儲存 Blog 的靜態檔案。

# 分支建立

因為需要要儲存其它的檔案，所以要先在自己的 GitHub Pages 的 Repository 上建立一個新的分支， Repository 名稱為 `username.github.io` ，當然你也可以存在別的 Repository  。一開始只會有  `master`  分支，而這邊示範為在原本的 Repository 上新增 `backup` 分支。

# 步驟

初始化這個目錄，進行版本控制。

```
git init
```

建立新分支  `backup`  ：

```
git checkout -b backup
```

將檔案加到暫存區及儲存庫：

```
git add .
git commit -m "Commit update"
```

設定要推上遠端 GitHub Server 的節點：

```
git remote add origin git@github.com:username/username.io.git
```

可以使用  `npm scripts`  來執行上面重複的命令：

```
{    
    "scripts": {
        "b": "git add . && git commit -m \"Commit update\" && git push origin master:backup"
    }
}
```

每行命令用  `&&`  符號來分開執行。

之後就可以透過輸入  `npm run b`  來佈署  `.md`  檔、主題及相關配置：

```
npm run b
```

<img src="2020-02-08-HexoBackup-2.PNG" style="width:100%;">

當切換至分支  `backup`  後就會看到原本在本地的檔案。



# 參考文獻

1. [Hexo 備份 md 檔 - 《Chris 技術筆記》](https://dwatow.github.io/2019/01-03-hexo/hexo-backup-to-branch/)
