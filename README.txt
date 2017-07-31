==============CentOS下git的命令行的操作==========
1.基本操作
	1)新建一个文件夹，做测试
	2)将此目录变为Git可管理的仓库
		:git init
	3)在该文件夹编辑自己的文件信息
	4)添加文件
		:git add file-name/git add .
	5)提交修改
		:git commit -m "说明文字"
	6)查看git的日志
		:git log
		:git log --pretty=oneline//只显示简要的信息
	7)查看版本号
		:git reflog
	8)回撤到对应的版本号
		:git reset --hard版本号
	9)删除已经提交的文件
		:git rm 文件名


=================================================
2.centOS下git连接到远程仓库GitHub
	1)如果是第一次连接到远程仓库，需要创建SSH
	:ssh-keygen -t rsa -C "your mail address"
	2)在.SSH目录下会有连个文件。一个是id_rsa，另一个是id_rsa.pub,对应一个是私钥，一个是公钥。
	3)将公钥中的内容添加到你的GitHub账号下，避免由于格式引起的错误，可以先
	:cat id_rsa.pub
	把内容打印到控制太再选择copy

	::在关联到远程仓库的时候，需要先执行基本操作，提交代码

	4)在GitHub仓库中新建一个仓库,根据提示在控制台关联仓库
	:git remote add origin git@github.com:xxx/xxxxx.git,将本地文件push上去
	:git push -u origin master
	第一次push加上-u参数，以后再push就直接push就可以了
	这时就可以在GitHub上看到push的内容了。

	5)克隆仓库到本地
		:git clone git@github:xxx/xxxxx.git//通过SSH方式克隆
		:h还有通过Https的

=================================================
3.分支
	1)创建分支，并且切换到创建的分支(示例中的分支名字dev)
		:git checkout -b dev
		相当于:git branch dev & git checkout dev
	2)切换分支
		:git checkout xxx
	3)查看分支，*表示指向当前分支
		:git branch
	4)合并分支测试(没有冲突)
		在当前分支下做更改
		然后
		:git add .
		:git commit
	5)切换到主分支
		:git checkout maseter
	6)合并分支
		:git merge dev
		//此时主分支是最新的内容
	7)现在可以删除dev分支
		:git branch -d dev
	
	=====冲突测试
	*新建并且切换一个分支develop，并且做修改
	*git add &&git commit
	*切换主分支 git checkout master
	*在主分支下做同样的更改
	*git add&&git commit
	*然后合并分支 git merge develop,会发现有冲突
	*手动修改合并

	*查看合并的图 git log --graph --pretty=oneline
	*强行删除分支git branch -D <name>

=================================================
4.标签Tag
	发布版本时，通常在版本库中打一个标签，这样就可以唯一确定了打标签时刻的版本。取某个标签的版本，就是把那个打了标签的时候的历史版本取出来

	1)带有说明的标签，用-a指定表签名，-m指定说明文字，后面指定commit
	id,如果没有指定就是最新commit的
	:git tag -a v1.0 -m "version 1.0 released" 3628164
	:git show v1.0//查看标签
	2)推送某个标签到远程
	:git push origin <tgname>
	3)本地删除标签
	:git tag -d xxxx
	4)如果已经push到远程仓库了，需要先删除本地标签，然后删除远程的标签
	:git push origin:refs:/tags/xxx
	5)推送全部未推送过的本地标签
	:git push origin --tags
















