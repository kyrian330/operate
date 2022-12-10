### 创建 vue 项目

1.win10终端输入 node 查看是否安装 node.js

```
D:\D盘桌面\Blog前端>node
Welcome to Node.js v16.13.2.
```



2.全局安装 vue。(只需安装一次，下次就可以直接用 vue 命令创建 vue 项目)

```
npm install -g @vue/cli
```



3.定位到项目目录，终端创建 vue 工程。（假设项目命名为 blog-vue）

```
vue create blog-vue
```

结果如下，开头让我更新 vue，不用理。下面的 my、mytest 是我之前保存的配置。

![1](img\1.png)



一开始按下方向键，选择Manually select features，按enter，进入自定义配置。

![2](img\2.png)



我们一般选择添加 Router、Vuex，去掉 Linner / Formatter。（点击空格键进行选择）

![3](img\3.png)



再回到  (*) Choose Vue version 选项，enter 进入。

![4](img\4.png)



enter 选择 3.x。下一步是否选择 history mode for router，建议选 y。

![5](img\5.png)



接下来选择 In package.json。

![6](img\6.png)





下一步会询问你是否保存当前的配置方案，选 y 会让你选择一个保存名。像我上面保存的 my、mytest。

![7](img\7.png)

这里我选择 y，并命名为 base-config。（意思就是基础配置，这个配置方案很常用）

![8](img\8.png)



点击 enter后，在工作目录（这里是 D:\D盘桌面\Blog前端）下开始创建 vue初始工程，卡住就按f5刷新一下。

![9](img\9.png)



创建成功后，结构如下

![10](img\10.png)



根据提示，进入工程根目录（上图），执行npm命令，运行程序。

```
cd blog-vue

npm run server
```

![11](img\11.png)



启动成功后，访问对应网址。 http://localhost:8080/

![12](img\12.png)



![13](img\13.png)



### 开发

​		创建成功，终端输入 ctrl + c 退出窗口。将 vue项目拖入idea进行开发。最好使用专业版 idea，才能下载 vue.js插件进行开发。

第一次 idea 会提示你下载 vue.js。（我之前下载过）

![14](img\14.png)



如图，代码有颜色。

![15](img\15.png)



选择 add configuration 添加配置。

![16](img\16.png)



点击 + 号，再选择 npm。

![17](img\17.png)



Script输入 serve，package.json 定位到项目根目录的 package.json。

![18](img\18.png)



以后点击 serve 旁边的启动键就可以运行 vue 项目。

![19](img\19.png)



### 切换 cnmp

查看镜像地址。

```
D:\D盘桌面\Blog前端\blog-vue>npm get registry
https://registry.npmjs.org/
```



安装 cnpm

```
npm install -g cnpm
```



更换淘宝镜像地址

```powershell
npm config set registry http://registry.npm.taobao.org/
```



使用 cnmp 可以加快下载速度。

```
cnpm install xxx
```



查看已经下载了那些模块。

```
// 查看当前文件夹
npm list -depath=0

// 查看全局安装的所有模块
npm list -depath=0 -global
```

