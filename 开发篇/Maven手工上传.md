#### 操作说明
```
 mvn install:install-file        -Dfile=<path-to-file> -DgroupId=<group-id>  -DartifactId=<artifact-id> -Dversion=<version> -Dpackaging=<packaging>   
    
```
实例： $ D:\apache-maven-3.0.4\bin>
```
mvn install:install-file -DgroupId=net.sf.xsshtmlfilter -DartifactId=xss-html-filter -Dversion=1.5 -Dpackaging=jar -Dfile=D:/xss-html-filter-1.6-SNAPSHOT.jar
```

#### 上传后问题
+ 依赖jar无法自动下载问题
```
切换到maven仓库，按照上传的group:artifact:version查找对应文件目录，将此目录下自动生成的pom文件内容，替换为jar内部的pom文件内容，再次mvn命令刷新下看看。
```