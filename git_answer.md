### 基本介紹 GIT 簡略歷史、使用緣由、何為版本控制？
最初目的是為了更好地管理Linux核心開發而設計
版本控制：是一種記錄一個或若干文件內容變化，以便將來查閱特定版本修訂情況的系統

### 版本控制的邏輯說明
將每個節點視為不同版本，對檔案做更動後紀錄到repo，會對應到下一個節點，如下圖所示。
![邏輯說明](https://gitbook.tw/images/tw/gitflow/why-need-git-flow/flow.png)

### Git 常用指令集介紹
| 指令 | 功能 |
| - | - |
| gic clone "url"| 抓遠端儲存庫下來 |
| git init | git 初始化 |
| git status | 查看目前的狀態 |
| git add . | 新增所有檔案 |
| git rm "file name"| 刪除檔案 |
| git commit -m "commit message" | 提交檔案 |
| git log | 列出版本紀錄 |
| git pull | 從遠端儲存提取 |
| git push | 從遠端儲存推送 |

### .gitignore 配置 
新增.gitignore檔案，在裡面放入要忽略的檔案路徑名稱
### 分支的使用方法
建立分支
``` bash
git branch <branchname>
```
切換分支
``` bash
git checkout <branchname>
```
合併分支
``` bash
git merge <branchname>
```
刪除分支
``` bash
git branch -d <branchname>
```
---
### Commit 介紹及使用
Commit：將暫存區的檔案提交到儲存庫儲存

``` bash
git commit -m "commit message"
```
### GitFlow 介紹
主要的分支有 master、develop、hotfix、release 以及 feature 這五種分支
<br />

**Master 分支**
主要是用來放穩定、隨時可上線的版本。
<br />

**Develop 分支**
這個分支主要是所有開發的基礎分支，當要新增功能的時候，所有的 Feature 分支都是從這個分支切出去的。
<br />

**Hotfix 分支**
當線上產品發生緊急問題的時候，會從 Master 分支開一個 Hotfix 分支出來進行修復，Hotfix 分支修復完成之後，會合併回 Master 分支，也同時會合併一份到 Develop 分支。
<br />

**Release 分支**
當認為 Develop 分支夠成熟了，就可以把 Develop 分支合併到 Release 分支，在這邊進行算是上線前的最後測試。
<br />

**Feature 分支**
當要開始新增功能的時候，就是使用 Feature 分支的時候了。