创建版本库

初始化一个Git仓库，使用`git init`命令

添加文件到Git仓库，分两步：

* 使用命令`git add <file>` ，可反复多次使用，添加多个文件；
* 使用命令`git commit -m <messenge>`，完成提交。



工作区状态

* 掌握工作区状态，使用`git status`命令。
* 如果`git status`告知有文件被修改，可用`git diff`查看被修改内容。



时光区穿梭

* `HEAD`指向的版本是当前版本，因此`Git`可以在版本之间穿梭，使用`git reset --hard commit_id`。
* 穿梭前，使用`git log`查看提交历史，以便确定回退到哪个版本。
* 重返未来，使用`git relog`看看命令历史，查看要回到未来的哪个版本。
