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
	

	














