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

尝试
git mergetool
返回如下信息：
This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
tortoisemerge emerge vimdiff
No files need merging

主要就是没有配置。


git branch
git branch -v
git branch --merged
git branch --no-merged

在掌握分支知识后，了解常见的工作流程：
长期分支、特性分支 

远程分支
git remote show github
信息如下：
* remote github
  Fetch URL: git@github.com:myjackfox/mystudy_git.git
  Push  URL: git@github.com:myjackfox/mystudy_git.git
  HEAD branch: master
  Remote branch:
    master tracked
  Local ref configured for 'git push':
    master pushes to master (fast-forwardable)
git ls-remote github
信息如下：
3501a2af40952d0cf151e433eb1451d3008bd920        HEAD
3501a2af40952d0cf151e433eb1451d3008bd920        refs/heads/master
0411fbf9ba8117e83f306f09ee85a2f2e097b029        refs/tags/V1.0
7b32e45654f1a7202dd858e783f2806a01021124        refs/tags/V1.0^{}
c9d295cf9eacff1e5e2cb5ce8c59ca9c43d509b3        refs/tags/V1.1
67e6630adf5c2431549d8a3bcfbd61a4d2a597ec        refs/tags/V1.1^{}
902bbc87ca1c540d93f4bca571ee97175194da38        refs/tags/V2.0
1f43b86e3bad972ad1ad452f0fdced2b124f915a        refs/tags/V2.0^{}
0411fbf9ba8117e83f306f09ee85a2f2e097b029        refs/tags/show
7b32e45654f1a7202dd858e783f2806a01021124        refs/tags/show^{}

远程分支这部分走马观花，因为没有实际用起来，不好理解。

推送
git push origin servefix
git fetch origin
git checkout -b serverfix origin/serverfix

跟踪分支
git checkout --track origin/serverfix
git checkout -b sf origin/serverfix
git branch -u origin/serverfix
git branch -vv

拉取

删除远程分支
git push origin --delete serverfix

变基
git checkout experiment
git rebase master

git checkout master
git merge experiment

git rebase --onto master server client
git checkout master
git merge client
git rebase master server
git checkout master
git merge server
git branch -d client
git branch -d server

变基的风险