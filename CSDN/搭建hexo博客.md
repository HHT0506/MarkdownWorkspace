## 1.安装Git

[下载地址](https://gitforwindows.org/)，下载后，一路安装即可。

## 2.安装nodejs

[下载地址](https://nodejs.org/en/download/)，选择Windows Installer(.msi) 64-bit，一路安装。

安装后，git bash中检测是否成功

```cpp
node -v
npm -v
```

### 3.安装hexo

```cpp
npm install -g hexo-cli
```

使用`hexo -v`查看版本。

在某一路径下新建一blog文件夹，执行

```cpp
hexo init
```

```cpp
npm install
```

再执行

```cpp
hexo g
```

```cpp
hexo s
```

此时可以在浏览器中输入localhost:4000查看生成的本地博客。

4.创建github仓库

仓库名为`xxx.github.io`，其中`xxx`为你的用户名，区分大小写。

5.生成ssh

```cpp
git config --global user.name "yourname"
```

```cpp
gitconfig --global user.email "youremail"
```

```cpp
ssh-keygen -t rsa -C "youremail"
```

`yourname`和`youremail`分别对应github的用户名和邮箱。

找到电脑中生成的`id_rsa.pub`文件，里面数据即为公钥，复制公钥，在github中新建SSH key。

查看是否成功

```cpp
ssh -T git@github.com
```

### 6.将hexo推送至github仓库

打开blog中的`_config.yml`，拉到最后，修改为：

```cpp
deploy:
  type: git
  repo: https://github.com/yourname/yourname.github.io.git
  branch: main
```

注意：

* yourname换成自己的用户名
* branch一定对应自己仓库的分支，之前创建仓库默认分支是master，后来默认为main。

安装deploy-git

```cpp
npm install hexo-deployer-git --save
```

推送至仓库

```cpp
hexo clean
```

```cpp
hexo g -d
```



## 参考

[hexo史上最全搭建教程](https://blog.csdn.net/sinat_37781304/article/details/82729029)

[解决github 打开、拉取、推送速度慢的问题](https://blog.csdn.net/natahew/article/details/81387885)

[解决 Failed to connect to github.com port 443:connection timed out](https://blog.csdn.net/Hodors/article/details/103226958?utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.control&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.control)

[【开发工具的那些故事】git问题记录（一）： Failed to connect to github.com port 443: Timed out](https://blog.csdn.net/yy339452689/article/details/104040279)

[Git报错解决：OpenSSL SSL_read: Connection was reset, errno 10054 错误解决](https://blog.csdn.net/weixin_43945983/article/details/110882074)

[Hexo启动页面显示extends includes/layout.pug block content include includes/recent-posts.pug include](https://github.com/HHT0506/HHT0506.github.io.git/)

[hexo修改主题](https://zhuanlan.zhihu.com/p/137338730)

[有哪些好看的 Hexo 主题？ - 温水青蛙的回答 - 知乎]( https://www.zhihu.com/question/24422335/answer/46357100)

