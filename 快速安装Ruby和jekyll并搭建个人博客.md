# 快速安装Ruby和jekyll并搭建个人博客


>疫情期间，家里电脑win10，具体搭建日期2020/03/02，今后不保证时效性。

>GithubPages + jekyll 前期GithubPages 参考文档[Creating and Hosting a Personal Site on GitHub](http://jmcglone.com/guides/github-pages/)

## Ruby 和 jekyll 的安装
### Step.1.安装rubyinstaller-devkit
>老版本rubyinstaller和devkit是分开的
>[快速安装rubyinstaller-devkit](https://blog.csdn.net/mscf/article/details/82627951)

- 1、从[https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/)下载Ruby+Devkit的安装包；

- 2、双击开始安装，选择全部安装；

- 3、在安装结束时，去除ridk install的选项，因为从默认的原去下载几百兆会非常缓慢；

- 4、查找Ruby安装目录下的msys64\etc\pacman.d，编辑更新源：
    ```java
    Server = https://mirrors.tuna.tsinghua.edu.cn/msys2/mingw/i686 
    加入mirrorlist.mingw32首位

    Server = https://mirrors.tuna.tsinghua.edu.cn/msys2/mingw/x86_64 
    加入mirrorlist.mingw64首位

    Server = https://mirrors.tuna.tsinghua.edu.cn/msys2/msys/$arch 
    加入mirrorlist.msys首位
    ```
- 5、执行在命令行执行`ridk install`（如果安装时选择了不加入系统环境变量的，去Ruby安装目录的bin之下执行），一路回车至结束；

- 6、更新gem源：(安装完rubygems后 此步)
    ```java
    gem sources --add https://mirrors.tuna.tsinghua.edu.cn/rubygems/ --remove https://rubygems.org/
- 7、在命令行行下查看gem是否正常安装
    >gem -v

### Step.2.安装RubyGems
[Github+Jekyll 搭建个人网站详细教程](https://www.jianshu.com/p/9f71e260925d)

- 1、从[https://rubygems.org/pages/download](https://rubygems.org/pages/download)下载RubyGems的安装包`.zip`；

- 2、解压至指定位置，在这里我存放于`D:\rubygems-3.1.2`
- 3、进入命令行 切换至rubygems目录，执行命令
    >ruby setup.rb
- 4、在命令行行下查看gem是否正常安装
    >gem -v

gem对源的操作
```java

//常用的源
http://rubygems.org/
http://gems.github.com
http://gems.rubyforge.org
http://ruby.taobao.org      //国内源，适合安装大多数常见的gem


//1.如果需要设置代理的话，需要先进行：
set http_proxy=url

//2.查看gem源
gem sources

//3.删除默认的gem源
gem sources --remove http://rubygems.org/

//4.增加taobao作为gem源
gem sources -a http://ruby.taobao.org/

//5.查看当前的gem源
gem sources

//6.清空源缓存
gem sources -c

//7.更新源缓存

gem sources -u
```


### Step.3.安装jekyll

- 1、在命令行行下输入 `gem install jekyll` 安装jekyll
    >gem install jekyll
- 2、在命令行行下输入 `gem install bundle` 安装
    >gem install bundle
- 3、在命令行行下输入 `jekyll --version`可看到jekyll的版本则说明jekyll安装成功。
    >jekyll --version



### Step.4.新建一个本地博客项目
- 1、在命令行行下`cd`到目标位置
    >gem install jekyll
- 2、在命令行行下输入 `jekyll new myblog`新建`myblog`
    >jekyll new myblog
    - 如果不报错，会在当前目录下新建 myblog 文件夹，即新建一个简单的博客静态站点目录；
    - 需要连接网络下载一些文件，所以执行时会有点慢；

- 3、在命令行下`cd`到新建的项目文件夹`myblog`
    >cd myblog

- 4、在命令行下输入 `jekyll serve` ，运行服务器
    >jekyll serve
- 5、在浏览器中输入 [http://127.0.0.1:4000/](http://127.0.0.1:4000/) 访问测试

更多jekyll命令，可参照官网[Jekyll Command Line Usage](https://jekyllrb.com/docs/usage/)

### Step.5.利用`jekyll`模板快速建站
- 1、Jekyll模板站点有哪些
    - [jekyllthemes.org/](http://jekyllthemes.org/)
    - [jekyllthemes.dev/](https://jekyllthemes.dev/)
    - ......  
- 2、下载Jekyll模板
    - 下载压缩文件，解压输出至 `本地目标位置`
    - 找到github仓库，直接在 `本地目标位置` 进行`git clone`
    >git clone 
- 3、预览Jekyll模板
    - 在命令行下`cd`到模板解压路径下，输入命令 `jekyll serve`
    - //如果发现报错，没有生成想要的本地博客，那就输入命令 `bundle exec jekyll serve`，然后就发现可以了。//未使用到这里，先写着
    - [http://127.0.0.1:4000/](http://127.0.0.1:4000/) 打开预览
- 4、修改Jekyll模板
    - 各随喜好


## GitHub Pages域名绑定
参考[GitHub免费搭建个人网站](https://www.jianshu.com/p/7124c5fe0fa7)
>购买的阿里云域名

>域名解析

- 进入你的域名控制台

- 点击解析进入解析添加解析

>记录类型

- 记录类型我们选择CNAME，别名记录，就是把一个域名完完全全设置为另外一个域名的别名

>主机记录

主机记录就是域名前缀，常见用法有：
```
www：解析后的域名为www.aliyun.com

@：直接解析主域名 aliyun.com

*：泛解析，匹配其他所有域名 *.aliyun.com

mail：将域名解析为mail.aliyun.com，通常用于解析邮箱服务器

二级域名：如：abc.aliyun.com，填写abc

手机网站：如：m.aliyun.com，填写m

显性URL：不支持泛解析（泛解析：将所有子域名解析到同一地址）
```



