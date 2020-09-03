# gunicorn + supervisor + nginx 部署django
## 创建超级用户
```
root@server:~# adduser lichy
root@server:~# passwd lichy
# 把新创建的用户加入超级权限组
root@server:~# usermod -aG wheel lichy
# 切换到创建的新用户
root@server:~# su - lichy
# 切换成功，@符号前面已经是新用户名而不是 root 了
lichy@server:$
```
## 安装python3
```
提前安装好系统依赖包：
centos: 
    yum install openssl-devel bzip2-devel expat-devel gdbm-devel readline-devel sqlite-devel gcc gcc-c++  openssl-devel libffi-devel python-devel mariadb-devel
ubuntu:
   sudo apt-get install zlib1g-dev libbz2-dev libssl-dev libncurses5-dev default-libmysqlclient-dev libsqlite3-dev libreadline-dev tk-dev libgdbm-dev libdb-dev libpcap-dev xz-utils libexpat1-dev liblzma-dev libffi-dev libc6-dev

1. 获取

wget https://www.python.org/ftp/python/3.6.2/Python-3.6.2.tgz
tar -xzvf Python-3.6.2.tgz -C  /tmp
cd  /tmp/Python-3.6.2/

2. 把Python3.6安装到 /usr/local 目录

./configure --prefix=/usr/local
make
make altinstall

3. 更改/usr/bin/python链接

ln -s /usr/local/bin/python3.6 /usr/bin/python3
```
## 安装maridb
```
1. 安装

    sudo yum install mariadb-server
2. 启动， 重启

    sudo systemctl start mariadb
    sudo systemctl restart mariadb

3. 设置bind-ip

    vim /etc/my.cnf
    在 [mysqld]:
        下面加一行
        bind-address = 0.0.0.0

4. 设置外部ip可以访问

    先进入mysql才能运行下面命令:
        mysql 直接进入就行

    GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY '123456' WITH GRANT OPTION;

    FLUSH PRIVILEGES

5. 设置服务器的对外端口

6. 安装mysqlclient出问题

    centos 7：
        yum install python-devel mariadb-devel -y

    ubuntu：
        sudo apt-get install libmysqlclient-dev

    然后：
        pip install mysqlclient
```
## 从服务器上拉取代码创建虚拟环境安装依赖包,进入虚拟环境

## 安装gunicorn
```
$ pip install gunicorn
```
### 运行
```
gunicorn blogproject.wsgi -w 2 -k gthread -b 0.0.0.0:8000
```