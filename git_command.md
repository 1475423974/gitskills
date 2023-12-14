#config
git config --global user.name "donghang"  （local更改个人branch）
git config --global user.email "dh1475423974@163.com"
#连接github
git clone +ssh
cd repo目录

#创建版本库
mkdir learngit
cd learngit
pwd #显示当前路径
git init

#放入文件
touch readme.txt#创建txt
git add readme.txt
git add readme1.txt
git add. #add everything in folder
git commit -m "add 2 files"
ls #查看文件是否存在

#建立branch
git checkout -b branch_1 #新建branch_1
git checkout main #返回main
git merge branch_1 #将branch_1合并到main  通常不能用！
git checkout -d branch_1 #删除原branch

git pull origin #(remote->local)
git push origin #(local main->remote main) 通常remote protected 不能用

Sync remote and local:先submit pull request，然后pull合并local
-git pull main from remote to local
-create a new branch local
-add files, commit changes
-push local branch to remote branch
    git push origin报错，根据提示可输入
	git push —set-upstream l1b#写title，做描述，并选择reviewer
-submit a pull request on github to ask to merge remote branch to remote main
-someone approve, merge happen
-now, remote main accepted the merge from remote branch
	-but local main has not merged local branch yet
-git pull main again, so local main is in sync with remote main
	git pull

#Conflict
-修改file1，保留===的上部或下部
-重新加入
git add file1.txt
git commit -m ‘resolve conflict'

#版本回退
git status #随时查看，掌握工作区状态
git diff readme.txt #查看修改内容
git log --pretty=oneline#查看提交日志
git reset --hard HEAD^ #回退到上个版本
git reset --hard 1094a #返回到某个未来版本
cat readme.txt #查看内容
git reflog #查看之前的每条命令

#conda 设置项目的python版本
conda create -n lecture_1 python=3.12
#建在git-intro路径下
conda deactivate
conda activate lecture_1
which wpython

pip install requests -U #安装最新版本requests包
pip install requests==12.0
#requirements.txt # all packages version required in pandas
pip install -r requirements.txt #安装所有需要的包，写在txt里，放在 current working directory路径下（git-intro）
pip list #查看所有安装包









