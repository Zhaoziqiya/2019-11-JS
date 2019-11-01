# git与github

- git:版本控制工具
    版本的时光穿梭
- github:网站、远程代码管理仓库、贵圈既有平台（交流、学习）


### 集中式 VS 分布式

    SVN：集中式
        弊端:版本控制必须需要网络支持，一般SVN都是局域网，只能是公司内部人员使用，外界的人想参与开发是比较麻烦的，中央服务器不一定就稳定，一旦出事中央服务器所有资源都洗白白。

    GIT：分布式
        不需要网络支持就能进行版本控制，只要能上网还要有开发权限都能参与开发，就算远程仓库库出事儿，计算机已经有了历史记录

    GITHUB：程序员交友网站、远程仓库、帮助学习


### 初始化版本控制状态

1.找到要控制的文件目录

2.鼠标右键，找到git bash here 点击

3.打开控制台：输入：git init

    版本控制都是基于.git这个隐藏文件的，如果不小心把.git文件删除，那么就不能

    查看git状态
        git status

    通过tab补全


    通过ll查看目录的文件，或者ls查看详细目录

    通过上下键去切换刚才输入的命令


### 设置作者信息
    - 设置用户名  git config --global user.name "你的名字"(这个名字想好)
    - 设置邮箱    git config --global user.email "你的邮箱"()

    工作区到暂存区
        git add 指定文件名放到暂存区

        git add . 批量指定文件放到暂存区

    暂存区到版本区
        git commit -m"注释" (你能直接识别的注释即可)

        上传到githob
        git puch origin master


    快速把工作区的代码放到版本区(已经被管理过的文件)    
        git commit -a -m"注释"
            注意：
                上面这个命令，前提条件是文件已经提交过一次才可以使用

    查看版本:
        git log
        git reflog   （查看所有的历史记录（包括历史区回滚后））

    出现nothing to commit, working directory clean就说明没有文件没被管理了（都被管理了）

- 回滚
    git reset --hard 历史ID


- touch .gitignore (创建.gitignore文件)

在文件中填写过滤的文件或文件夹

*.zip、*.rar、*.via、*.tmp过滤这些后缀名的文件

排除指定文件夹下的文件， /txt/1.txt

排除指定文件夹  \txt2

git rm -r --cached .  如果已经提交过的代码，使用.gitignore是无效的，那么请使用前面这段代码


- clear清屏

- 如果发现:号就按Q键退出

- 查看各大区域的区别
    - 工作区到暂存区  git diff
    - 工作区到版本区  git diff master
    - 暂存区到版本区  git diff --cached


- 把本地git的版本上传到github上管理

    - 设置秘钥:
        ssh-keygen -t rsa -C "your_email@example.com"

    - 登录github，右边头像下拉列表有个settings，找到SSH and GPG keys，找到new ssh key点击，把秘钥放到文本框中，点击add ssh key。

    - 在github上创建一个项目
        - 加号下拉列表，第一个创建新项目
        - 仓库名称
        - 说明
        - 公开
        - README打钩

- 查看远程仓库
    - git remote -v   
- 创建远程仓库
    - git remote add origin 远程地址
    ```
       比如: git remote add origin git@github.com:nizp/2019-10-8.git
    ```

- 同步远程
    - git pull origin master

- 推送到远程
    - git push origin(远程名字) master(分支名)
    ```
        比如:git push origin master
    ```
- 删除远程仓库
    - git remote remove 远程名字


- 克隆项目
    - 找到远程仓库的地址，git clone远程仓库地址 回车



## 过滤指定文件
    - 创建一个 .gitignore 的文件
    - touch .gitignore (创建文件)
    - 配置过滤项


    - 如果说配置不起作用，可以洗把之前的操作清除一下，在过滤操作清楚命令
        git rm -r --cached .

    撤销回滚：
        git reset --hard 版本id
        


## github
    其实有很多代码托管平台

    把我们的代码放到远程仓库
- 第一种方式

        1.在github上创建一个项目
        2.绑定密匙：.ssh-keygen -t rsa -C""
        3.确定版本是最新的（没有东西可以提交了）
        4.查看远程仓库：git remote -v （使用git init的时候是查不出来东西的）
        5.添加远程仓库：git remote add origin （这个名字是可以改变的）git@github.com:
        6.git pull origin master （保证能够成功上传，进行远程操控的）
        7.git push origin master

- 第二种方式

        1.先在远程仓库创建一个项目
        2.git clone 项目的地址
        3.git add . git commit -m ""
        4.git push origin master
    

### node的安装（自带就有npm）

- 项目的初始化
    - npm init -y
- npm install 安装程序

- npm uninstall 删除安装程序

- npm 目前是全球最大的包管理平台（里面有很多的代码资源）

npm install nrm -g

- 测nrm的速度  
    - nrm test
- 切换资源路线
    - nrm use taobao

- yarn的安装
    - npm install yarn -g

    - yarn add 安装程序
    - yarn remove 要删除的程序

end

