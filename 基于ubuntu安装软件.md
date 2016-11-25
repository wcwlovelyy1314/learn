# 安装Nodejs
下载编译后的文件`node-v0.12.14-linux-x64.tar.gz`  
上传到`/home/ncd`（主目录）执行：  
```bash
tar -xf node-v0.12.14-linux-x64.tar.gz
sudo mv node-v0.12.14-linux-x64/ /usr/local/node-v0.12.14
# sudo ln -s -T /usr/local/node-v0.12.14/bin/node /usr/local/bin/node
# sudo ln -s -T /usr/local/node-v0.12.14/bin/npm /usr/local/bin/npm
sudo ln -sf /usr/local/node-v0.12.14/bin/* /usr/local/bin/
```

# 安装postgresql
下载所有依赖包，[下载地址(全部下载)](http://ops.imedpower.com/ubuntu/postgresql/)  
依赖包都是从[这里](http://apt.postgresql.org/pub/repos/apt/pool/main/) 下载到的。  
其他软件如有依赖缺失，可以到这里来找 
上传到`/home/ncd/postgresql/`（主目录下）执行：
```bash
# cd postgresql
sudo dpkg -i *.deb
```

# 安装mongodb
下载编译后的文件    
上传到 `/home/ncd`（主目录）执行：  
```bash
tar -xf mongodb-linux-x86_64-ubuntu1404-3.2.6.tgz
sudo mv mongodb-linux-x86_64-ubuntu1404-3.2.6 /usr/local/mongodb3.2.6
sudo ln -sf /usr/local/mongodb3.2.6/bin/* /usr/local/bin/
```

# 安装pm2和bunyan
把模拟环境安装好的打包上传到主目录，执行：
```bash
tar -xf bunyan.tar.gz
tar -xf pm2.tar.gz
sudo mkdir /usr/local/lib/node_modules
sudo mv bunyan/ pm2/ /usr/local/lib/node_modules
sudo ln -sf /usr/local/lib/node_modules/*/bin/* /usr/local/bin
```

# 安装jdk和jetty
执行：
```bash
tar -xf jdk-8u73-linux-x64.tar.gz
tar -xf jetty-distribution-9.3.9.v20160517.tar.gz
sudo mv jdk1.8.0_73/ /usr/local/
sudo ln -sf /usr/local/jdk1.8.0_73/bin/* /usr/local/bin/
```
配置环境变量：`vim /etc/profile`  
```bash
# 在最下面添加
JAVA_HOME=/usr/local/jdk1.8.0_73
CLASS_PATH=.:$JAVA_HOME/lib:$JAVA_HOME/jre/lib

export JAVA_HOME CLASS_PATH
```

# 安装nginx
[下载地址](http://nginx.org/packages/ubuntu/pool/nginx/n/nginx/nginx_1.10.0-1~trusty_amd64.deb)  
[下载页面](http://nginx.org/packages/ubuntu/pool/nginx/n/nginx)应该有很多版本，全部是stable版本，可以选择最新的  
```bash
sudo dpkg -i nginx_1.10.0-1~trusty_amd64.deb.deb
```

安装完成后，执行：
```bash
cd /etc/nginx
sudo vim nginx.conf
# 在 include /etc/nginx/conf.d/*.conf; 下面添加：
include /etc/nginx/sites-enabled/*;

# 可能需要删除 conf.d/default.conf
mv conf.d/default.conf conf.d/default.conf.bak
# 然后创建配置文件
sudo mkdir sites-enabled sites-available
# 然后复制一份配置文件过去，把相关路径、端口号修改正确
sudo vim sites-available/production # 把内容填进去，并修改
cd sites-enabled
sudo ln -s ../sites-available/production # 不知道为什么，创建一个软链接必须先到目标目录，然后执行这个命令
# 然后reload
sudo nginx -s reload
```
