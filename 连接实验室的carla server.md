# 连接实验室的carla server

## 安装edu vpn

[Download - eduVPN](https://www.eduvpn.org/client-apps/)

ubuntu要22.04以上版本才能装，所有我只能装window的

以下是设置步骤：

https://doku.lrz.de/pages/viewpage.action?pageId=87425039&showLanguage=en_GB

 

## 可选：安装putty

安装好后，如图设置，点击open

<img title="" src="file:///E:/github_repos/study/img/putty.png" alt="putty.png" width="429">

输入用户名和密码即可进入



## 创建python3.8的conda环境

**<u>一定要python3.8才能和server上的版本对应！</u>**

```shell
conda activate --name carla13 python=3.8
```

 

## 安装carla0.9.13

**<u>一定要用pip安装，从github上下载的whl文件都是对应python3.7的，不行！</u>**

```shell
pip install carla==0.9.13
```

 

## 安装examples文件的依赖包

```shell
cd examples
python -m pip install -r requirements.txt
```

 

## 运行carla client

Note: 是20000不是2000(default)哦！用vim dockerfile.yaml可以查看到

```shel
python manual_control.py --host 10.157.150.3 –-port 20000
```
