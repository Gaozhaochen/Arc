1. 初始化仓库
 git init

2. 查看仓库的状态
git status
![](https://i.imgur.com/E4cJFu8.png)

3. 向暂存区添加文件
git add
如果只是创建文件，该文件并不会记入Git仓库的版本管理对象，须要使用指令加入暂存区
![](https://i.imgur.com/ATKmi03.png)

4. 保存仓库的历史记录`
git commit 指令可以将当前暂存区中的文件保存到仓库的历史记录中；
![](https://i.imgur.com/LcWViEF.png)

5. 查看更改前后的差别
git diff 当前工作树与暂存区的区别
git diff HEAD 本次提交与上次提交之间的区别

### 分支相关操作
1. 显示分支列表
git branch 

2. 创建、切换分支
 git branch branch_1 
 git checkout branch_1
![](https://i.imgur.com/PnGOnrm.png)
或者是： git checkout -b branch_1

3. 删除分支
git branch -d iss53

4. 合并分支
git merge
合并到master分支时，首先切换到master分支； 在合并时加上--no-ff参数；
![](https://i.imgur.com/DPp1DtK.png)

5. 以图表形式查看分支
git log --graph

6. 回溯历史版本
git reflog 查看当前仓库执行过的操作日志； 
git reset  --hard 恢复到回溯历史的状态；
![](https://i.imgur.com/G6HsD5Y.png)

7. 修改提交信息
git commit -amend

8. 两次提交合并
git rebase -i HEAD~2
将pick部分删除，改写为fixup
![](https://i.imgur.com/pLxvBad.png)
![](https://i.imgur.com/FQ1QQ3u.png)


>注意

#####1. 两者提示区别
* Changes to be committed
说明已经是暂存状态，如果此时提交，该文件将被留在历史记录中；
* Changes not staged for commit 
跟踪的文件发生了变化，但是还没有放到暂存区；

#####2. git commit -m 和 git commit -am 区别
```
git add .
git commit -m "some str"
```

```
git commit -am "some str"
```
针对第一步中的git  add .命令的作用就是将本地修改过的文件且已经追踪的文件添加到本地的暂存区，
然后使用git commit -m "str"命令将暂存区的代码提交到本地仓库；

第二部其实就相当于第一步的结合，但是有区别的是git commit -am 'str'命令只能提交已经追踪过且修改了的文件，去过是新增文件就必须使用第一步的命令；若文件没有被git监视（如新增的一个文件），此时使用该命令会报错。






参考文章
https://git-scm.com/book/zh/v2 