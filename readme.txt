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

<<<<<<< HEAD
现在模拟进入一个紧急修复分支hotfix1。
git checkout -b hotfix1
这里多了一行，hotfix行。
git add readme.txt
git commit -a -m "in branch hotfix1:Add a hotfix line in readme.txt"
git checkout master
git merge hotfix1

经过修复与合并后，切换到master，删除掉已经合并的分支。
git branch -d hotfix

以上就是完成了修复，并将正式上线的修复分支并入master。
下步就是切回到问题修改处，继续修改iss3的问题。
git checkout iss3
继续修改。
=======
这个时候，工作目录是干净了。
git status
已经确认。
开始模拟在正常工作基础上，针对问题iss3进行分支处理。
git checkout -b iss3
修改readme.txt
在分支iss3下修改的内容。

中途因出现紧急情况暂停iss3处理，转回master进行hotfix分支紧急修复，然后合并入master。
处理好后，再转回到iss3继续进行处理（记录本次操作情况说明）。


>>>>>>> iss3


上面是在处理好iss3后，转回master，进行合并操作后的结果。
git checkout master
git merge iss3
出现如下信息提示：
D:\MyStudy\Git>git merge iss3
Auto-merging readme.txt
CONFLICT (content): Merge conflict in readme.txt
Automatic merge failed; fix conflicts and then commit the result.
然后再打开readme.txt后，内容就变成了了上面的样子，两个部分用单书引号括住