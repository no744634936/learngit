
git 一般工作流程
 
 1,首先在github上面建立一个库，test


2,本地建立同名文件夹test

	git init 


3,本地test文件夹里编辑文件后，

	git add .
        git commit -m "first commit"
	git add origin https://..............
	git push origin master


这样就将本地的文件推送到了github上面。


4,本地建立dev分支，并推送到github上面

	git checkout -b dev
	git push origin dev


5,dev 分支的 branch保护设定(master分支也得做保护设定才行)

	setting -> Branch protection rules -> add rules ->输入dev-> Require pull request reviews before merging  选需要一个人来codereview



6,现在就可以选择共同开发的人一起开发了

	setting -> collabrator ->输入github账号名。然后等回信


7，被邀请的人开始工作。

	git clone https://github.com/no744634936/testgit.git -b dev　　首先克隆dev branch
	
	cd到克隆的文件夹下面

	git pull origin  dev

8，开发开发，首先要从dev分支上面切一个branch 
	
	git branch        查看分支

	git checkout dev  首先切换到dev分支上面

	git checkout -b feature/20190919-advertiser_fix_the_list     切一个feature并换到这个feature上面


9，被邀请的人修改文件后

	git add .

	git commit -m ""

	git push origin  也可以写   git push origin feature/20190919-advertiser_fix_the_list

	git push --set-upstream origin feature/20190919-advertiser_fix_the_list



10，回到github页面。选择feature/20190919-advertiser_fix_the_list 分支，点击new pull request


11，选择reviewer，来检查代码


12，选择dev分支 点击create pull request


14，之后我就可以点击 pull requests 然后点击file changed 然后点击承认。


15，最后点击merge pull request，点击confirm merge。 github上面新的代码就加入了dev里面了。


16，这时候远程的dev变了，但是被邀请人的本地的dev并没有变。所以被邀请人就要

	git pull origin dev  从远程把内容拉过来。
	
        git checkout dev (一定要移动到dev分支上才能切新的feature)

	git checkout -b feature/20190919-advertiser_add_function




--------------------------------------------------------------
处理Git 忘记切分支修改了代码的情况

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

---------------------------------------------------------------------


