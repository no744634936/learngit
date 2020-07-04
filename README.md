场景
有时候没注意分支，直接在 master 上做开发了，但是这是团队开发的大忌。那如果发生了这种情况怎么办，也不用着急， 我教你怎么解决。

解决问题
假设你现在在 master 分支上已经修改了文件，那么我们可以使用下面的命令把当前未提交到本地（和服务器）的代码推入到 Git 的栈中：
$ git stash

查看效果：
$ git status 

切换分支：
$ git chekout -b 3_create_category

还原代码：
$ git stash apply
ok，问题解决。
