����һ��learngit�汾��
$ mkdir learngit
$ cd learngit
$ pwd   //pwd����������ʾ��ǰĿ¼
---------------------------------------
ͨ��git init��������Ŀ¼���Git���Թ���Ĳֿ�
$ git init
---------------------------------------
������git add����Git�����ļ���ӵ��ֿ�
$ git add readme.txt
������git commit����Git�����ļ��ύ���ֿ�
$ git commit -m "wrote a readme file"


---------------------------------------
git status�������������ʱ�����ղֿ⵱ǰ��״̬
$ git status
---------------------------------------
git diff�鿴difference����ʾ�ĸ�ʽ����Unixͨ�õ�diff��ʽ
$ git diff readme.txt 

git diff HEAD -- readme.txt������Բ鿴�������Ͱ汾���������°汾������
$ git diff HEAD -- readme.txt 
---------------------------------------
git log������ʾ���������Զ���ύ��־
$ git log
$ git log --pretty=oneline //
---------------------------------------
git reset���
$ git reset --hard HEAD^
��һ���汾����HEAD^������һ���汾����HEAD^^����Ȼ����100���汾д100��^�Ƚ�������������������д��HEAD~100

$ git reset --hard 3628164 //$ git reset --hard (commit id)ָ���ص�δ����ĳ���汾
---------------------------------------
git reflog������¼���ÿһ������
$ git reflog
---------------------------------------
git checkout -- file���Զ������������޸ģ�
$ git checkout -- readme.txt
--����Ҫ
����git checkout -- readme.txt��˼���ǣ���readme.txt�ļ��ڹ��������޸�ȫ�����������������������
һ����readme.txt���޸ĺ�û�б��ŵ��ݴ��������ڣ������޸ľͻص��Ͱ汾��һģһ����״̬��
һ����readme.txt�Ѿ���ӵ��ݴ������������޸ģ����ڣ������޸ľͻص���ӵ��ݴ������״̬��
��֮������������ļ��ص����һ��git commit��git addʱ��״̬��
---------------------------------------
����git reset HEAD file���԰��ݴ������޸ĳ�������unstage�������·Żع�������
$ git reset HEAD readme.txt
git reset����ȿ��Ի��˰汾��Ҳ���԰��ݴ������޸Ļ��˵�����������������HEADʱ����ʾ���µİ汾��
---------------------------------------
����git rm����ɾ��һ���ļ���
$ git rm test.txt
���һ���ļ��Ѿ����ύ���汾�⣬��ô����Զ���õ�����ɾ��
����ҪС�ģ���ֻ�ָܻ��ļ������°汾����ᶪʧ���һ���ύ�����޸ĵ�����
---------------------------------------

---------------------------------------
***            Զ�ֿ̲�            ****
---------------------------------------
����SSH Key:
$ ssh-keygen -t rsa -C "youremail@example.com"
�������Լ����ʼ���ַ(һ·�س���ʹ��Ĭ��ֵ����)

�û���Ŀ¼���ҵ�.sshĿ¼��������id_rsa��id_rsa.pub�����ļ�������������SSH Key����Կ�ԣ�id_rsa��˽Կ������й¶��ȥ��id_rsa.pub�ǹ�Կ

��½GitHub
�㡰Add SSH Key������������Title����Key�ı�����ճ��id_rsa.pub�ļ�������
---------------------------------------
����git remote add origin git@server-name:path/repo-name.git�����زֿ����
origin:Զ�̿�����־���origin
server-name:path/repo-name.git:GitHubGitHub�˻���/Զ�̿�

$ git remote add origin git@github.com:michaelliao/learngit.git

---------------------------------------
���ؿ�������������͵�Զ�̿��ϣ�
git push -u origin master��һ������master��֧���������ݣ�
�˺�ÿ�α����ύ��ֻҪ�б�Ҫ���Ϳ���ʹ������git push origin master���������޸ģ�

***�����һ��ʹ��Git��clone����push��������GitHubʱ����õ�һ�����棺
***The authenticity of host 'github.com (xx.xx.xx.xx)' can't be established.
***RSA key fingerprint is xx.xx.xx.xx.xx.
***Are you sure you want to continue connecting (yes/no)?
***������ΪGitʹ��SSH���ӣ���SSH�����ڵ�һ����֤GitHub��������Keyʱ��
��Ҫ��ȷ��GitHub��Key��ָ����Ϣ�Ƿ��������GitHub�ķ�����������yes�س����ɡ�
---------------------------------------


