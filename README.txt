Useful Git Commends
git init——通过git init命令把这个目录变成Git可以管理的仓库
git status——git status命令可以让我们时刻掌握仓库当前的状态
git add——用命令git add告诉Git，把文件添加到仓库
git remove -r -f —— 从本地和版本库中的文件删除
git commit -m ——用命令git commit告诉Git，把文件提交到仓库
git diff
git log
git reset——回退版本
$ git reset --hard 3628164        $ git reset --hard HEAD^^
git reflog
git clone
git remote -v add git@

Have to creat the new ssh key on the Github:
$ ssh-keygen -t rsa -C "youremail@example.com"
id_rsa和id_rsa.pub

git push A(origin) B(branch master)
