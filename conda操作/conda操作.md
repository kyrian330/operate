1.先激活虚拟环境

```
activate
```

路径前面会出现（base），说明已经切换到 conda 环境了。

![1](img\1.png)



2.查看python版本

```
python -V
```



3.创建python3.6.3的虚拟环境，命名为 dev-env（如果你需要，可以创建其它版本的python）

```
conda create --name dev-env python=3.6.3
```

输入 y 确认创建。

![2](img\2.png)



查看所有虚拟环境（*表示当前所处哪一个环境）

```
conda env list
```

![3](img\3.png)

使用 conda 的一个重要原因是因为不同开发环境间可以快速切换。尽量给每个项目都创建自己的虚拟环境，才能发挥 conda 隔离不同项目、防止所需的库版本发生冲突的优势。



4.切换到指定的虚拟环境    conda activate name

```
conda activate dev-env
```

观察路径前的内容，发现成功从 base 切换到 dev-env。

![4](img\4.png)



5.运行脚本文件

```
python xxx.py
```

先切换到项目地址，再执行命令。

![5](img\5.png)



6.下载、卸载库/包

```
conda install package
conda uninstall package
```

例如 conda install padas。也可以使用 pip install package，暂时没明白二者的区别，以后知道了会更新。建议都使用 conda install ...。



7.导出环境

```perl
conda env export > environment1.yaml
```

将包的信息保存在 yaml 文件中。这个文件会生成在当前执行命令的路径下。

我会在桌面建文件夹 envs-yaml，进入文件夹再执行命令，这样文件就保存在该文件夹了。

![6](img\6.png)



yaml格式文件。

![8](img\8.png)



8.导出环境

假设用配置文件 environment1.yaml 创建新的虚拟环境。

注意：导入操作存在的意义是，我给你一份环境配置信息，你可以很轻松将环境复制过去。这样 B 机器可以拿到 A 机器的某个环境。现在我们一台电脑要导入同一份环境（我只用一台电脑演示），直接执行命令会报错。我们来观察一下 environment1.yaml。只需要把 第1行name，23行prefix修改一下就行。而如果你电脑的conda 没有dev-env这个名字的环境，是没必要修改的，可以直接执行导入命令。

![8](img\8.png)



name不能和conda现有环境重名，假设新环境名为 new_env。

![11](img\10.png)



```
conda env create -f C:\Users\TF\Desktop\envs-yaml\environment1.yaml
```

![11](img\11.png)



切换到 new_env，查看有什么包。

![12](img\12.png)



9.列出所有包

```
pip freeze > requirement.txt
```

![13](img\13.png)

文件保存在 C:\Users\TF\Desktop\envs-yaml 下。

10.删除指定环境

```
conda remove -n name --all
```

