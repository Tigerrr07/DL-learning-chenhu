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