# Git

## TODO
1. 增加commit message template

## Git/Github
* $ git config --global user.name "duidae"
* $ git config --global user.email "duidae@gmail.com"
* $ git clone https://github.com/duidae/source.git
* pull request https://gitbook.tw/chapters/github/pull-request.html
* check out specific branch
  * $ git clone -b mark/newArch-testProtoBuf https://github.com/duidae/carta.git CARTAvis
* branch
  * https://zlargon.gitbooks.io/git-tutorial/content/branch/create_delete.html
  * 這篇很清楚: https://gogojimmy.net/2012/01/21/how-to-use-git-2-basic-usage-and-worflow/
  * $ git branch // show branch
  * $ git branch [branch name]  // create a branch
  * $ git checkout [branch name] // 切換branch
  * $ git branch -D [branch name] // delete local branch
  * $ git push origin --delete [branch name]  // delete remote branch
  * $ git reset --hard ORIG_HEAD // 取消merge
  * $ git reset HEAD <file> // 取消已經add的file
  * $ git checkout -- <file> // 重新checkout某個檔案, 檔案修爛可以重來
 
```
$ git checkout master // switch to branch master
$ git pull origin master // Now pull the latest changes in master
$ git merge testBranch // Merge with the testBranch
$ git push origin master // Push the changes to master

$ git branch -D testBranch // delete local branch
$ git push origin --delete testBranch  // delete remote branch
```

* remove directory
  * $ git rm -r one-of-the-directories
  * $ git commit -m "Remove directory"
  * $ git push
* log
  * [git history](https://git-scm.com/book/zh-tw/v1/Git-%E5%9F%BA%E7%A4%8E-%E6%AA%A2%E8%A6%96%E6%8F%90%E4%BA%A4%E7%9A%84%E6%AD%B7%E5%8F%B2%E8%A8%98%E9%8C%84)
  * [git log 高級用法(好文)](https://github.com/geeeeeeeeek/git-recipes/wiki/5.3-Git-log-%E9%AB%98%E7%BA%A7%E7%94%A8%E6%B3%95)
  * $ git log -p -2
  * $ git log --stat  //這比較好用
  * $ git log --graph --oneline --decorate
* diff
  * $ git diff [filename]
  * $ git diff HEAD^^ HEAD main.c //看main.c 現在與前兩版的差異
* commit
  * $ git commit --amend // 修正commit message
  * 如何寫git commit message
    * https://blog.louie.lu/2017/03/21/%E5%A6%82%E4%BD%95%E5%AF%AB%E4%B8%80%E5%80%8B-git-commit-message/
    * https://blog.wu-boy.com/2015/09/how-to-write-git-commit-message/
    * https://chris.beams.io/posts/git-commit/
    * Pro git https://git-scm.com/book/en/v2
    * git message template https://robots.thoughtbot.com/better-commit-messages-with-a-gitmessage-template
* remote repository
  * $ git remote -v
  * $ git remote get-url origin //show出這個repo是從哪fetch來的
* submodule
  * https://blog.wu-boy.com/2011/09/introduction-to-git-submodule/comment-page-1/
* undo a merge in github
  * https://gitbook.tw/chapters/rewrite-history/reset-revert-and-rebase.html
    * Reset	把目前的狀態設定成某個指定的 Commit 的狀態，通常適用於尚未推出去的 Commit。
    * Rebase	不管是新增、修改、刪除 Commit 都相當方便，用來整理、編輯還沒有推出去的 Commit 相當方便，但通常也只適用於尚未推出去的 Commit。
    * Revert	新增一個 Commit 來反轉（或說取消）另一個 Commit 的內容，原本的 Commit 依舊還是會保留在歷史紀錄中。雖然會因此而增加 Commit 數，但通常比較適用於已經推出去的 Commit，或是不允許使用 Reset 或 Rebase 之修改歷史紀錄的指令的場合。
  * revert
    * $ git revert HEAD
    * $ git push
    * https://github.com/geeeeeeeeek/git-recipes/wiki/5.2-%E4%BB%A3%E7%A0%81%E5%9B%9E%E6%BB%9A%EF%BC%9AReset%E3%80%81Checkout%E3%80%81Revert-%E7%9A%84%E9%80%89%E6%8B%A9
  * $ git reset --hard master^
  * https://stackoverflow.com/questions/42860234/how-to-undo-a-merge-in-github
* fork出來的repo與原始repo同步
  * 1.打开你的github fork repo;
  * 2.点击Pull request;
  * 3.点击new pull request.默认情况下，github会比较original/your fork，这时应该不会有任何输出，因为你并没有做过任何变更；
  * 4.点击switching the base.这时github将反过来比较yourfork/original，这时你将看到original相对你fork时的所有commit;
  * 5.点击create a pull request for this comparison，这时将会反过来向你的repo提交一个pull request;
  * 6.这时你作为你自己fork的repo的owner，你就可以点击confirm the merge，大笔一挥，所有的改动都被你一网打尽了@！
* git clone 後為何local只看得到 "master"
  * git clone 會下載remote所有branch並在local產生一個對應remote master的locat master, 但因 $ git branch只會顯示local branch, 所以才只會看到一個master而已, $ git branch -a即可看到所有的branch
  * 如何在local也產生一個和remote一樣的branch以供開發呢？
    * $ git branch branchone origin/branchone
