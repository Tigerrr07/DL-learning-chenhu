创建版本库

初始化一个Git仓库，使用`git init`命令

添加文件到Git仓库，分两步：

* 使用命令`git add <file>` ，可反复多次使用，添加多个文件；
* 使用命令`git commit -m <messenge>`，完成提交.



工作区状态

* 掌握工作区状态，使用`git status`命令。
* 如果`git status`告知有文件被修改，可用`git diff`查看被修改内容.



时光区穿梭

* `HEAD`指向的版本是当前版本，因此`Git`可以在版本之间穿梭，使用`git reset --hard commit_id`.
* 穿梭前，使用`git log`查看提交历史，以便确定回退到哪个版本.
* 重返未来，使用`git relog`看看命令历史，查看要回到未来的哪个版本.

工作区和暂存区
* 工作区(working directory)是电脑中目录,比如我创建的`codegit`文件夹.
* 工作区的隐藏目录`.git`, 是Git的版本库, 其中最重要的是暂存区(stage), 以及Git为我创建的的第一个分支`master`, 以及指向master的一个指针`HEAD`.
* `git add`命令是把要提交的所有修改放到`stage`, 然后执行`git commit`一次性将`stage`的所有修改提交到分支.

撤销修改
* 场景一: 当改乱了工作区某个文件的内容, 直接丢弃工作区的修改, 用命令`git checkout -- file`.
* 场景二: 当改乱了工作区的某个内容, 还添加到了暂存区, 想丢弃修改, 分两步: 用`git reset HEAD <file>`回到场景一, 第二步用按场景一操作.
* 场景三: 已经提交不合适的修改到版本库, 撤销本次提交, 参考版本回退, 前提是没有推送到远程库.
 
 
删除文件
* 手动删除文件, 或用`rm`命令删除后, Git会知道删除了文件, 工作区和版本库就不一致, `git status`会告知哪些文件被删除. 两种选择
  * 从版本库中删除该文件, 用命令`git rm <file>`删掉, 并且`git commit`.
  * 删错了, 利用`git checkout -- test.txt`将文件恢复到最新版本. (`git checkout`其实是用版本库的版本替换工作区的版本, 无论工作区是修改还是删除, 都可以还原)
* 如果从版本库中也已删除, 使用`git reset --hard commit_id`也可恢复.

添加远程库
* 关联远程库, 使用命令`git remote add orgin git@server-name:path/repo-name.git`, `origin`是远程库默认习惯命名.
* 关联后, 使用命令`git push -u origin master`第一次推送master分支的所有内容.
* 此后每次本地提交后, 使用命令`git push origin master`推送最新修改

从远程库克隆
* 知道仓库的地址, 然后使用`git clone`命令克隆.
* Git支持多种协议, 包括`http`, 但`ssh`协议最快.

创建与合并分支
* 查看分支: `git branch`
* 创建分支: `git branch <name>`
* 切换分支: `git switch <name>`
* 创建+切换分支: `git switch -c <name>`
* 合并某分支到当前分支: `git merge <name>`
* 删除分支: `git branch -d <name>`
* 删除远程分支: `git push origin -d dev`