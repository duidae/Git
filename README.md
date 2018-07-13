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
* show current branch
  * $ git branch
* remove directory
  * $ git rm -r one-of-the-directories
  * $ git commit -m "Remove directory"
  * $ git push
* git log
  * [git history](https://git-scm.com/book/zh-tw/v1/Git-%E5%9F%BA%E7%A4%8E-%E6%AA%A2%E8%A6%96%E6%8F%90%E4%BA%A4%E7%9A%84%E6%AD%B7%E5%8F%B2%E8%A8%98%E9%8C%84)
  * [git log 高級用法(好文)](https://github.com/geeeeeeeeek/git-recipes/wiki/5.3-Git-log-%E9%AB%98%E7%BA%A7%E7%94%A8%E6%B3%95)
  * $ git log -p -2
  * $ git log --stat  //這比較好用
  * $ git log --graph --oneline --decorate
* git diff
  * $ git diff [filename]
* git branch
  * https://zlargon.gitbooks.io/git-tutorial/content/branch/create_delete.html
  * $ git branch [branch name]
  * $ git branch //list branch
* 如何寫git commit message
  * https://blog.louie.lu/2017/03/21/%E5%A6%82%E4%BD%95%E5%AF%AB%E4%B8%80%E5%80%8B-git-commit-message/
  * https://blog.wu-boy.com/2015/09/how-to-write-git-commit-message/
  * https://chris.beams.io/posts/git-commit/
  * Pro git https://git-scm.com/book/en/v2
  * git message template https://robots.thoughtbot.com/better-commit-messages-with-a-gitmessage-template
