=================================================
1.centOS下git连接到远程仓库GitHub
	1)如果是第一次连接到远程仓库，需要创建SSH
	:ssh-keygen -t rsa -C "your mail address"
	2)在.SSH目录下会有连个文件。一个是id_rsa，另一个是id_rsa.pub,对应一个是私钥，一个是公钥。
	3)将公钥中的内容添加到你的GitHub账号下，避免由于格式引起的错误，可以先
	:cat id_rsa.pub
	把内容打印到控制太再选择copy
	4)在GitHub仓库中新建一个仓库,根据提示在控制台关联仓库
	:git remote add origin git@github.com:xxx/xxxxx.git,将本地文件push上去
	:git push -u origin master
	第一次push加上-u参数，以后再push就直接push就可以了
