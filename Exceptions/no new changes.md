## git push到gerrit上的时候提示no new changes
 **! [remote rejected] master -> refs/for/master (no new changes)**
 
### 问题分析：  
  Git bash提示：no new changes表示没有新的提交。Gerrit根据commit id和changeId判断是否有新的提交，如果以上两者都是相同的，则Gerrit会拒绝提交。
### 解决办法1：
git commit --amend生成新changeId
### 解决办法2：
找到前一个commitId，使用git reset --soft commitId，撤销提交后重新commit。然后再次push 即可。
