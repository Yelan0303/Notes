# 一.准备工作



所需软件：Node.js,Git,Hyper-v(可选)

Node.js	https://nodejs.org/en/

Git		https://git-scm.com/

下完找好地方随便装，全程默认，反正看不懂



# 二.检查

安装完成后打开CMD，输入

```
git --version
```

```
node -v
```

无顺序要求，输入后出现版本号即可

# 三.生成本地内容

终端中跳转到想要生成博客的文件夹（或在文件夹中右击选择在Hyper中打开）

## 1.安装hexo

```
npm install hexo-cli -g
```

执行此命令可能速度较慢，建议更换国内源`npm config set registry http://registry.npm.taobao.org`

安装过程中不报错即可，警告忽视

安装完成后运行`hexo -v`

出现版本号即表示安装成功

## 2.生成本地Blog文件

```
hexo init blog
```

出现Start blogging with Hexo!即为成功

此步完成后，将生成blog文件夹

## 3.进入上一步生成的Blog文件夹

```
cd blog
```

跳转到blog目录下

## 4.npm安装

```
npm install
```

同理，无报错即可，警告忽视

## 5.启动本地服务器，用于预览主题

运行 `hexo server`，`hexo s`也可

此时，可在本地访问 http://localhost:4000/

按Ctrl+c之后，无法再访问此网页

## 6，生成静态网站文件

```
hexo g
```

无报错即可，警告不管

## 7.小结

至此，本地工作告一段落

# 三.注册Github并建库

## 1.注册并登录GitHub

注册登录GitHub

## 2.新建repository

右上角头像左侧加号，repo name随意填,Description自选，默认库为公开状态，

选择Add a README file，点击Create repository即可

## 3.设置

创建完成后点击库界面Settings

下拉找到GitHub Pages,点击黄色提示框中蓝色字体。

Source中选择Branch 为main

# 四.ssh keys

## 1.连接github

blog文件夹中右击选择 Git Bash Here,git中输入

`git config --global user.name "	"` 双引号中填入你注册的Github的用户名

`git config --global user.email " "` 双引号中填入你注册Github所用邮箱

## 2.生成ssh密钥

github点击头像，选择settings,下拉左侧找到SSH and GPG keys.

右侧点击 NEW SSH KEYS,title随便填。

终端跳转到log目录下或直接在blog目录下使用Git Bash Here,输入

`ssh-keygen -t rsa -C " "`  引号内内容为注释，随意填写即可

之后一直按回车即可，如果此步骤非第一次，可能会出现询问是否覆盖，输入y即可

## 3.获取ssh密钥

输入 `cat ~/.ssh/id_rsa.pub` 即可生成密钥

拷贝后粘贴到key处即可

## 4.检查

blog下git bash here，输入 `ssh -T git@githun@com`

输入yes， 出现successfully authenticater即可，不管but后内容

## 五.修改配置

blog目录下，打开_config.yml（VScode为佳，记事本也可）

\#URL下，在url的下一行顶格输入 `root: / /` 空格处填你创建的库名称

\#Deployment下，

```
type: git
```

`repo: 链接`

```
branch: main
```

repo与branch前面都有两个空格，即与上面的type对齐，原文件中不存在，均需自己填写，

注：冒号与后面的内容之间均有一个空格

### 链接获取方法

github主页->头像->Your Repostiories->你创建的库，点进去->绿色按钮code->链接

# 六.发布

## 准备

在正式上传到Github之前，还有一步准备工作

打开github，Settings->Developer settings->Personal access tokens->Generate new token

note随便填，但别忘了，等会要用，select scopes下选repo,然后下拉点绿色按钮，对号后生成一串口令，复制下来找个地方存好，以免遗忘，当你关闭这个页面后，你将无法再次库看到

## 发布

终端中位置跳转到blog下，`npm i hexo-deployer-git`

同理，不报错就行

运行 `hexo d`

弹出一个github的登录框，输入你的github帐号

在Username for的提示中输入之前设置的note,在Password for的提示中输入之前保存的口令（输入过程不可见，建议cv大法，以免输错），输完后按回车。

# 七.视检

本地工作完结，回到github，进入刚才创建的库，进入settings下拉找到GitHub Pages，点进去，source下Branch若不为main，则修改为main，可以看到 Your site is published at （）的字样，括号内即为你的博客的网址。

一开始为蓝底，且有感叹号，等一会刷新页面，上传成功后为绿底且前面有对号。

# 八.完结

点进去，加载时祈祷不要404

好了，大功告成。

Hexo个人博客搭建完成

# 九.问题总结

## 1.使用hexo s命令时出错，强行关闭终端后无法再次使用

node.js在后台运行，占用了本地的4000端口，打开任务管理器，下拉找到node.js，关闭即可

也可以在使用命令时调用其他端口

## 2.修改本地内容后更新到github

```
hexo clean` 		`hexo g`		`hexo s`		`hexo d
```

四条命令依次使用

## 3.

还有啥问题等想到了并且肯动弹了再写

