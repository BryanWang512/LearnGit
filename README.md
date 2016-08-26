# LearnGit
repository to learn git
first change

git init  -- create a git repositroy
git add (filename * n) -- add a file to commit
git commit -m "log" -- commit to repositroy
git status -- check the repositroy status
git diff (filename) --  check the difference between the last version
git log 	-- check the commit log
git log -pretty=oneline -- check the cmd log oneline
git reflg --check the cmd log
git reset --hard HEAD^ -- rollback to the last version
git reset --hard HEAD^^^ -- rollback to the last 3 version
git reset --hard HEAD~n -- rollback to the last n version
git reset --hard commit_id -- rollback to the version whose id is commit_id
git checkout -- file  --丢弃工作区修改
git reset HEAD file  --丢弃暂存区修改

$ ssh-keygen -t rsa -C "email" 
--创建ssh key pair；private key:id_rsa; pub key:id_rsa.pub

git remote add origin git@github.com:BryanWang512/LearnGit
-- github.com:BryanWang512/LearnGit 远程库url: BryanWang512帐号 LearnGit仓库
，远程库的名字就是origin  关联一个远程库

$ git push -u origin master --把本地库的内容推送到远程，用git push命令，实际上是把当前分支master推送到远程  由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

git clone git@github.com:BryanWang512/LearnGit  -- clone remote repositroy


查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>

删除远程分支: git push origin :branch-name --冒号前面的空格不能少，原理是把一个空分支push到server上，相当于删除该分支。

创建远程分支: git push origin branch-name  --先切换到本地创建的新分支

$ git log --graph --pretty=oneline --abbrev-commit --查看分支合并图

<<<<<<< Updated upstream
$ git merge --no-ff -m "merge with no-ff" dev --合并分支时，加上--no-ff参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而fast forward合并就看不出来曾经做过合并。

git stash --可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作：

git stash list --查看工作现场

git stash pop --恢复的同时把stash内容也删了：

git stash apply --恢复，不删除stash内容

git stash drop --删除stash内容

git branch -D <name> --丢弃一个没有被合并过的分支，强行删除。

git remote --查看远程库的信息 -v显示更详细的信息
--以下将远程分支拉取到本地 的步骤
git remote show origin --show
git remote update
git fetch
git checkout -b local-name origin/remote-name --将远程分支拉取到本地
