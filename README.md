# util

可以给项目配上公钥，但是如果没有使用id_rsa这样的文件名，会授权失败。

授权失败后，可以使用ssh-agent来管理私钥

````shell
$ ssh-agent -s
# Agent pid 59566
$ ssh-add ~/.ssh/id_rsa
````

*注： 如果执行 ssh-add 时显示错误 Could not open a connection to your authentication agent. 那么执行

````shell
eval `ssh-agent -s`
````

如果我们想要查看ssh代理中已经添加了哪些私钥，可以使用'ssh-add -l'来进行查看

我们还可以列出代理中所有私钥对应的公钥内容，使用'ssh-add -L'

如果我们想要从代理中移除某个已经添加的私钥，可以使用'ssh-add -d'命令指定要移除的私钥

我们也可以一次性清空代理中的所有私钥，使用'ssh-add -D'指令即可

关闭ssh-agent的办法是'ssh-agent -k'
