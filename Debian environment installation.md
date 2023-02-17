# Debian系安装环境

## 1.首先安装MongoDB

1. 首先导入包管理系统使用的公钥。
   
   ```
   wget -qO - https://www.mongodb.org/static/pgp/server-4.2.asc | sudo apt-key add -
   ```

该操作应以响应`OK`。

但是，如果收到指示`gnupg`未安装的错误，则可以：

1. `gnupg`使用以下命令安装及其所需的库：

```
sudo apt-get install gnupg
```

   2.安装完成后，重试导入密钥：

```
wget -qO - https://www.mongodb.org/static/pgp/server-4.2.asc | sudo apt-key add -
```

### 创建MongoDB包管理库

```
echo "deb http://repo.mongodb.org/apt/debian buster/mongodb-org/4.2 main" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.2.list
```

### 重新加载本地软件包数据库。

```
sudo apt-get update
```

如果预计的不错的应该已经报`libssl1.1`错误了，解决办法

```
echo "deb http://security.ubuntu.com/ubuntu focal-security main" | sudo tee /etc/apt/sources.list.d/focal-security.list

sudo apt-get update
sudo apt-get install libssl1.1
```

### 安装MongoDB软件包

```
sudo apt-get install -y mongodb-org
```

### 启动MongoDB

```
sudo systemctl start mongod
```

如果在启动时收到类似于以下内容的错误 [`mongod`](https://mongodb.net.cn/manual/reference/program/mongod/#bin.mongod "宾蒙哥")：

`Failed to start mongod.service: Unit mongod.service not found.`

首先运行以下命令：

```
sudo systemctl daemon-reload
```

然后再次运行上面的启动命令。

### 验证MongoDB已成功启动。

```
sudo systemctl status mongod
```

### 您可以有选择地通过发出以下命令来确保MongoDB将在系统重启后启动：

```
sudo systemctl enable mongod
```

## 2.安装openjdk-java-17

```
apt install openjdk-17-jre openjdk-17-jdk -y
```

## 安装其他工具

```
sudo apt install git unzip wget -y
```

## 

```
cd ~
```



```
wget https://github.com/Grasscutters/Grasscutter/raw/development/keystore.p12
```

复制`BinOutput`目录与`ExcelBinOutput`到`resources`目录中

```
cd ~ && cd /root/yuanshen/  && cp -r ExcelBinOutput/ /root/yuanshen/resources

cp -r BinOutput/ /root/yuanshen/resources
```

最后执行一下命令启动服务器

```
java -jar grasscutter-1.4.3.jar
```

## [Debian安装MongoDB官网教程](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-debian)
