Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.
Creating a new branch is quick AND simple.
Add a new branch by lihui.

�ðɣ���Щ�ϻ�û�����塣
1������ǰ���ProGit�ڶ���Ľ��ܽ�����ʾ���ļ���
2��Git init����ʱ�Ѿ�������ļ��ˡ�����LICENSE��
3��Ȼ���ֹ����⽨����2��c�ļ����Ա��ܹ�˳��ִ��git add

20210222
���github����Clone�˸���Ŀmystudy_git

�����ڴ����˷�֧testing�󣬲��ڷ�֧testing�½�����һ���޸�readme.txt�����󷵻ص�master��֧��
��ʱreadme.txt��������master��֧������ݣ�testing��֧���޸ĵ�����û�ˡ�
20210224
git checkout master

�����޸�readme.txt���ݣ���û���޸ķ�֧����
��commitʱ����ע��һ���������ݡ�

<<<<<<< HEAD
����ģ�����һ�������޸���֧hotfix1��
git checkout -b hotfix1
�������һ�У�hotfix�С�
git add readme.txt
git commit -a -m "in branch hotfix1:Add a hotfix line in readme.txt"
git checkout master
git merge hotfix1

�����޸���ϲ����л���master��ɾ�����Ѿ��ϲ��ķ�֧��
git branch -d hotfix

���Ͼ���������޸���������ʽ���ߵ��޸���֧����master��
�²������лص������޸Ĵ��������޸�iss3�����⡣
git checkout iss3
�����޸ġ�
=======
���ʱ�򣬹���Ŀ¼�Ǹɾ��ˡ�
git status
�Ѿ�ȷ�ϡ�
��ʼģ�����������������ϣ��������iss3���з�֧����
git checkout -b iss3
�޸�readme.txt
�ڷ�֧iss3���޸ĵ����ݡ�

��;����ֽ��������ͣiss3����ת��master����hotfix��֧�����޸���Ȼ��ϲ���master��
����ú���ת�ص�iss3�������д�����¼���β������˵������


>>>>>>> iss3


�������ڴ����iss3��ת��master�����кϲ�������Ľ����
git checkout master
git merge iss3
����������Ϣ��ʾ��
D:\MyStudy\Git>git merge iss3
Auto-merging readme.txt
CONFLICT (content): Merge conflict in readme.txt
Automatic merge failed; fix conflicts and then commit the result.
Ȼ���ٴ�readme.txt�����ݾͱ��������������ӣ����������õ���������ס

����
git mergetool
����������Ϣ��
This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
tortoisemerge emerge vimdiff
No files need merging

��Ҫ����û�����á�


git branch
git branch -v
git branch --merged
git branch --no-merged

�����շ�֧֪ʶ���˽ⳣ���Ĺ������̣�
���ڷ�֧�����Է�֧ 

Զ�̷�֧
git remote show github
��Ϣ���£�
* remote github
  Fetch URL: git@github.com:myjackfox/mystudy_git.git
  Push  URL: git@github.com:myjackfox/mystudy_git.git
  HEAD branch: master
  Remote branch:
    master tracked
  Local ref configured for 'git push':
    master pushes to master (fast-forwardable)
git ls-remote github
��Ϣ���£�
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

Զ�̷�֧�ⲿ������ۻ�����Ϊû��ʵ����������������⡣

����
git push origin servefix
git fetch origin
git checkout -b serverfix origin/serverfix

���ٷ�֧
git checkout --track origin/serverfix
git checkout -b sf origin/serverfix
git branch -u origin/serverfix
git branch -vv

��ȡ

ɾ��Զ�̷�֧
git push origin --delete serverfix

���
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

����ķ���