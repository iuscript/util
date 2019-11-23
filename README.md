# util

可以给项目配上公钥，但是如果没有使用id_rsa这样的文件名，会授权失败。

授权失败后，可以使用ssh-agent来管理私钥

````shell
$ ssh-agent -s
# Agent pid 59566
$ ssh-add ~/.ssh/id_rsa
````
