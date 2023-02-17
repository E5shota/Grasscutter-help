# 首先cd到yum包管理目录

```
cd /etc/yum.repos.d/
```

# 下载包管理配置文件

```
wget https://github.com/E5shota/Grasscutter-help/blob/main/mongodb-org-6.0.repo
```

# 安装mongodb

```
sudo yum install -y mongodb-org
```

# 安装Java-17

##### 找一个位置放一下java-17

```
cd ~
```

##### 1、下载安装包

```
wget https://download.oracle.com/java/17/latest/jdk-17_linux-x64_bin.tar.gz
```

##### 2、解压安装包,修改包名为jdk-17

```
tar zxf jdk-17_linux-x64_bin.tar.gz
rm -rf jdk-17_linux-x64_bin.tar.gz
mv jdk-17.0.3.1/ jdk-17
```

##### 3、移动Java文件夹到/usr/local目录中

```
mv jdk-17 /usr/local/
```

##### 4、将java添加到环境变量中，编辑下方文件

```
vim /etc/profile
```

把下面的代码放到这个文件的最下面

```
export JAVA_HOME=/usr/local/jdk-17
export PATH=/usr/local/php/bin:/usr/local/jdk-17/bin:$PATH
```

##### 5、加载刚才修改的文件

```
source /etc/profile
```

##### 6、验证是否安装java成功

```
java -version
```

显示下面的东西就说明你的Java安装成功

![](https://github.com/E5shota/Grasscutter-help/blob/main/java%20-version.png)


