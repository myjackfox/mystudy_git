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