# 特定のコミット内容を修正したい

## commands

``` terminal
### 直前のコミットメッセージ修正

$ git commit --amend -m '修正後コミットメッセージ'

### 2つ以上前のコミット修正

$ git log --oneline
1d6bb15 (HEAD -> feat/hogefuga, origin/feat/hogefuga) modified index.html
6b327c4 add index.html
0c489f3 add some comments on README
f159f13 add README
a9341dc first commit


$ git rebase -i HEAD~n // 戻したいコミットが HEAD から何番目か
                       // 上記ログの場合、 "0c489f3 add some comments on README" を戻したい場合は n = 3

// 戻したいコミットを edit に変更し、保存（:wq）
edit 0c489f3 add some comments on README
pick 6b327c4 add index.html
pick 1d6bb15 modified index.html

# Rebase f159f13..1d6bb15 onto f159f13
#
// 下の Commands にあるように、基本的に git rebase -i では様々な修正ができる
# Commands:
#  p, pick = use commit
#  r, reword = use commit, but edit the commit message
#  e, edit = use commit, but stop for amending
#  s, squash = use commit, but meld into previous commit
#  f, fixup = like "squash", but discard this commit's log message
#  x, exec = run command (the rest of the line) using shell
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out

Stopped at 0c489f3...  add some comments on README
You can amend the commit now, with

  git commit --amend

Once you are satisfied with your changes, run

  git rebase --continue

// 修正後、指示通り commit --amend し、 rebase --continue で完了
```

## refs

- [[git]特定のコミットの内容を修正する](https://dackdive.hateblo.jp/entry/2014/09/21/122200)
- [Gitのコミットメッセージを後から変更する方法をわかりやすく書いてみた](https://www.granfairs.com/blog/staff/git-commit-fix)
