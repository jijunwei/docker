# docker

执行查询docker版本号，看是否安装成功
docker --version
 
正常情况下会出现如下视图
￼
docker启动：
service docker start
docker开机自启动：
chkconfig docker on
 
 
1.2：Docker-Compose安装
Docker-Compose安装可参照官网步骤进行，需要服务器支持curl功能，如果服务器不支持curl，需要执行如下操作安装curl依赖：
yum install curl
根据官网所指向github项目，目前docker-compose最新版为1.15.0
执行如下操作下载docker-compose
curl -L https://github.com/docker/compose/releases/download/1.15.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-composechmod +x /usr/local/bin/docker-compose
该下载目录为/usr/local/bin/docker-compose，且权限已经给出，再执行docker-compose --version检查版本号，或许会有如下示：
￼
如果出现上述提示，执行以下操作
cp /usr/local/bin/docker-compose /usr/bin
将docker-compose拷贝至/usr/bin目录下，再次执行
docker-compose --version
正常情况下会打印docker-compose的版本信息，如下视图
￼
 
docker常用命令如下：
杀死所有正在运行的容器
docker kill $(docker ps -a -q)
删除所有已经停止的容器
docker rm $(docker ps -a -q)
删除所有镜像
docker rmi $(docker images -q)
强制删除所有镜像
docker rmi -f $(docker images -q)

