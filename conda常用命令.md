————————————————
版权声明：本文为dave的笔记文档，遵循 CC 4.0 BY-SA 版权协议，转载请附上原文出处及本声明。
## conda 常用命令
也可选择图形界面——anaconda-navigator

+ conda list 查看安装了哪些包。
   
+ conda env list 或 conda info -e 查看当前存在哪些虚拟环境

+ conda update conda 检查更新当前conda

+ conda create -n py27 python=2.7
  
  conda create -n py35 python=3.5

+ python -version 检查当前环境python版本

+ source active py27（py35） 激活虚拟环境

+ conda install -n py35 [包名] 将包安装到虚拟环境下

+ deactivate py35 关闭虚拟环境

+ conda remove -n py27 --all 移除虚拟环境

+ conda remove --name $py35 $package_name 移除环境中的某个包

[Window安装Anaconda后，conda不是内部或者外部命令](https://blog.csdn.net/u011361880/article/details/75294226)



### 查询完整帮助文件

 `conda create --help` or `conda create -h` 其实“--”参数一般都有简写。

### 管理conda和anaconda

`conda info` 查询conda信息

`conda update conda` 升级conda

`conda update anaconda` 升级anaconda

### 管理环境
`conda info -e` 环境信息

`conda create -n test python=2.7` 创建环境test，并指定python版本，此例为2.7

`source activate test` 激活环境

`source deactivate test` 关闭环境

`conda remove --name test --all` 删除环境

### 包管理
`conda list`列出所有安装的包的信息

`conda search beautiful-soup` 查询包

`conda install -n test beautiful-soup` 安装包，并指定安装环境，如果没有-n test，则安装到当前环境

`conda update beautiful-soup` 升级包

`conda remove -n test beautiful-soup` 移除包