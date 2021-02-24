Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.
Creating a new branch is quick AND simple.
Add a new branch by lihui.

好吧，这些废话没有意义。
1、这个是按照ProGit第二版的介绍建立的示例文件。
2、Git init建立时已经有这个文件了。还有LICENSE。
3、然后手工随意建立了2个c文件，以便能够顺利执行git add

20210222
检查github，并Clone了该项目mystudy_git

这是在创建了分支testing后，并在分支testing下进行了一个修改readme.txt操作后返回到master分支。
此时readme.txt的内容是master分支最后内容，testing分支下修改的内容没了。
20210224
git checkout master

继续修改readme.txt内容，但没有修改分支名。
在commit时而是注释一个特殊内容。
