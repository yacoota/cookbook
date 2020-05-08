
[软件下载](https://www.oracle.com/java/technologies/javase-jdk14-downloads.html)


1、安装
```
命令：
tar zxf /data/firework/upload/jdk-14.0.1_linux-x64_bin.tar.gz -C /data/firework/software/jdk
```

2、配置
```
命令：
vi ~/.bash_profile

export JAVA_HOME=/data/firework/software/jdk/jdk-14.0.1
export PATH=.:$JAVA_HOME/bin:$PATH
```

3、加载
```
命令：
source ~/.bash_profile
```