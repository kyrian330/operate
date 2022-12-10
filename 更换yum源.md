### 更换yum源



首先备份 /etc/yum.repos.d/CentOS-Base.repo 文件

- 备份

```ABAP
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
```



- 进入 /etc/yum.repos.d/ 里，下载对应版本 repo 文件（以centos7为例）

```ABAP
http://mirrors.163.com/.help/CentOS7-Base-163.repo
```



- 下载

```ABAP
wget http://mirrors.163.com/.help/CentOS7-Base-163.repo
```



- 替换

```ABAP
mv CentOS7-Base-163.repo CentOS-Base.repo
```



- 生成缓存

```ABAP
yum clean all

yum makecache
```

------



### 核心思想

**/etc/yum.repos.d/CentOS-Base.repo** 是yum的配置文件，将源文件替换成我们需要的yum源就行。

------



### 更多

除了网易之外，国内还有其他不错的 yum 源，比如中科大和搜狐。

中科大的 yum 源，安装方法查看：https://lug.ustc.edu.cn/wiki/mirrors/help/centos

阿里云的yum源下载，**`wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo`**

