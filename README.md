# Basic Git Instruction

基本git指令操作與ubuntu vim使用。
[Git 教學](https://www.youtube.com/watch?v=LZ4oOzZwgrk&list=PLlyOkSAh6TwcvJQ1UtvkSwhZWCaM_S07d)可以看這個YT教學，教的不錯，但Remote and Github那章建議別看自己學，在未熟知使用git之前不要動Organization的Repositories，弄壞會被我扁，但也還好沒有我允許你也動不了🙂️🙂️🙂️

## Vim Usage

### 指令狀態
* ESC		變更為指令狀態
* :"num"	指令狀態下,移動至num
* :set number	顯示行數

### 編輯
* Ctl + v	指令狀態下，變為多行狀態
* i or shift + i	變為編輯狀態
上面兩個一起使用可變為多行編輯，再按下ESC完成多行編輯。

* dd		指令狀態下刪除一行
* y		複製該行內容
* p		貼上複製內容
也可以搭配多行狀態進行多行編輯。

## Git Setting

### 須先進行git初始設定，以下為初始設定參考，可自定義。
* git config --global user.email "user@email.com"	設定使用者資訊
* git config --global user.name "user name"		設定使用者資訊
* git config --global alias.st status 		設定簡寫
* git config --global core.editor vim 		設定commit編輯器
* git config --global merge.tool vimdiff		設定mergetool編輯器

### git 指令
* git add .			將目錄內所有檔案納入track狀態
* git rm --cached "file"	從track狀變成untrack狀態
* git commit			新增commit
* git commit --amend		修改當前commit
* git status			查看git目前狀態

* git reset HEAD			恢復原本commit狀態，更改內容會重置！！！
* git branch "branch name"		創建新分支
* git checkout -b "branch name"	創建新分支後切換至分支
* git branch -m "old branch name" "new branch name"	更改分支名稱

* git merge "branch name"		與目前分支融合
* git merge --no-ff "branch name"	與目前分支融合，融合分支會保留分支
* git rebase "branch name"	將此branch基底移植到另一個commit

* git reflog 			歷史git改動

* git tag 			顯示所有tag
* git tag -a "tag info"	新增tag

### git 上傳至 github
#### 電腦需要有SSH 公鑰註冊進你的github帳戶
* git remote add "remote name" "url"	新增remote
* git push -u "remote name"		上傳遠端，設定推送分支的上游，第一次上傳分支用-u就好
* git push "remote name"		上傳遠端
* git push -f "remote name"		強制上傳遠端，謹慎使用！！！

* git pull "remote name"		遠端抓取最新內容並merge到master，不建議使用
* git fetch --prune "remote name" 	從遠端抓取最新所有內容
* git fetch "remote name"		從遠端抓取最新內容
* git merge remotes/origim/main	將遠端跟本地端分支合併
* git rebase remotes/origim/main	跟上面同理，但建議使用這個

* git push "remote name" "local branch":"remote branch"	將指定本地端branch上傳/更新至雲端
* git push --tags			上傳所有tag至遠端
* git push "remote name" tag "tag_name"	上傳指定tag至遠端，建議使用這個

