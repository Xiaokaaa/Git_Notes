- [1 学习链接](#1-学习链接)
- [2 如何克隆GitHub项目到本地](#2-如何克隆github项目到本地)
  - [2.1 安装Git](#21-安装git)
  - [2.2 克隆项目到本地](#22-克隆项目到本地)
  - [2.3 参考链接](#23-参考链接)
- [3 如何将本地项目上传到GitHub](#3-如何将本地项目上传到github)
  - [3.1 注册GitHub账号](#31-注册github账号)
  - [3.2 GitHub项目创建](#32-github项目创建)
  - [3.3 将本地仓库推送到远程仓库](#33-将本地仓库推送到远程仓库)
  - [3.4 可能遇到的问题](#34-可能遇到的问题)
  - [3.5 参考链接](#35-参考链接)
  - [3.6 同步项目到本地仓库](#36-同步项目到本地仓库)
  - [3.7 Git 撤销上一次 push](#37-git-撤销上一次-push)
- [4 GitHub分支相关操作](#4-github分支相关操作)
  - [4.1 GitHub修改当前仓库的默认分支](#41-github修改当前仓库的默认分支)
  - [4.2 查看分支、创建分支、合并分支](#42-查看分支创建分支合并分支)
- [5 快速建立本地仓库与远程仓库连接（团队常用操作）](#5-快速建立本地仓库与远程仓库连接团队常用操作)
  - [5.1 配置ssh key](#51-配置ssh-key)
  - [5.2 克隆团队项目到本地](#52-克隆团队项目到本地)
  - [5.3 拉取](#53-拉取)
  - [5.4 推送](#54-推送)
- [6 团队多人协作（进阶）](#6-团队多人协作进阶)
  - [6.1 项目负责人（张三）新建一个项目仓库](#61-项目负责人张三新建一个项目仓库)
  - [6.2 项目负责人邀请他人（李四）加入项目](#62-项目负责人邀请他人李四加入项目)
  - [6.3 总结](#63-总结)
  - [遇到的问题及解决方案](#遇到的问题及解决方案)


## 1 学习链接

- 菜鸟教程·Git教程：[[link]](https://www.runoob.com/git/git-tutorial.html)

## 2 如何克隆GitHub项目到本地

### 2.1 安装Git

- Git官网链接：[[link]](https://git-scm.com/)，如下图直接点击下载即可。

  ![](image%2FGit_Image%2Fimage1.png)

- 下载完毕，运行安装程序，一直点击`next`即可。

- 检查安装 (按下`Win`+`R`打开命令行，输入`git --version`查看)，出现下图结果表示安装成功。

  ![](image%2FGit_Image%2Fimage2.png)

### 2.2 克隆项目到本地

- 选择一个文件夹作为本地仓库。

  <div align="left">
    <img src="image%2FGit_Image%2Fimage3.png" alt="image3.png" width="250" style="margin-right: 20px;" />
    <img src="image%2FGit_Image%2Fimage4.png" alt="image4.png" width="290" style="margin-left: 20px;" />
  </div>

- 输入命令：`git init`，效果如下，所选文件夹会多一个`.git`文件夹。

  ![](image%2FGit_Image%2Fimage5.png)

- 将需要克隆的项目从GitHub上复制项目链接地址。

  ![](image%2FGit_Image%2Fimage6.png)

- 输入命令`git clone 链接`即可克隆项目到本地，如下图所示。

  ![](image%2FGit_Image%2Fimage23.png)

### 2.3 参考链接

- CSDN博客·如何克隆GitHub上的项目到本地：[[link]](https://blog.csdn.net/qq_45542879/article/details/116403788)

## 3 如何将本地项目上传到GitHub

### 3.1 注册GitHub账号

- 进入[GitHub](https://github.com/)主页，注册并登录。

### 3.2 GitHub项目创建

- 进行如下操作新建一个项目

  <div align="left">
    <img src="image%2FGit_Image%2Fimage24.png" width="300" style="margin-right: 10px;" />
    <img src="image%2FGit_Image%2Fimage25.png" width="400" style="margin-left: 10px;" />
    <img src="image%2FGit_Image%2Fimage26.png" />
  </div>


- 创建成功后进入项目页面，其中的网址在后面git上传会用到。

  ![](image%2FGit_Image%2Fimage27.png)

### 3.3 将本地仓库推送到远程仓库

- 进入项目所在路径，打开Git Bash。
- 输入`git init`，在当前项目的路径下会生成本地的git管理。（会发现在当前目录下多了一个`.git`文件夹）
- 输入`git add . `，将当前目录和其子目录中的所有新的或已修改的文件添加到 Git 的暂存区
- 输入`git commit -m “first commit”`，“first commit”表示你对这次提交的注释
- 输入`git remote add origin https://自己的仓库url地址`，将本地的仓库关联到GitHub上。
- 输入`git push -u origin master`，将本地的 "master" 分支推送到远程仓库 "origin"，操作结束。

### 3.4 可能遇到的问题

- 如果执行`git push -u origin master`后出现如下错误，

  ![](image%2FGit_Image%2Fimage28.png)

  则需要输入`git config --global http.sslVerify false`解除ssl验证，之后再次执行`git push -u origin master`即可，这个时候可能需要输入github账号和密码，效果如下。

  ![](image%2FGit_Image%2Fimage29.png)
- 如果出现

  ![](image%2FGit_Image%2Fimage30.png)

  则可尝试一下使用覆盖提交的方式，输入`git push -f origin 分支名`，其中`-f`是覆盖提交的参数。

### 3.5 参考链接

- CSDN博客·在github上上传本地项目步骤（两种方式）：[[link]](https://blog.csdn.net/oNew_Lifeo/article/details/115189603)
- CSDN博客·解决Git上传代码error: failed to push some refs to ‘xxx‘hint:(e.g., ‘git pull ...‘) before pushing again错误：[[link]](https://blog.csdn.net/qq_43265673/article/details/107392047)

### 3.6 同步项目到本地仓库

- 从远程仓库（origin）的master分支拉取最新的更改到你的本地仓库。
  ````
  git pull origin master
  ````

### 3.7 Git 撤销上一次 push 
- 查看最近 push 的版本
- 返回之前版本
  - 回退到上个版本：`git reset --hard HEAD^ `
  - 退到/进到 指定 commit_id 版本：`git reset --hard commit_id` 
- 参考链接：[[link]](https://blog.csdn.net/m0_37605197/article/details/110919455)


## 4 GitHub分支相关操作

### 4.1 GitHub修改当前仓库的默认分支

  ![](image%2FGit_Image%2Fimage31.png)

  ![](image%2FGit_Image%2Fimage32.png)

  ![](image%2FGit_Image%2Fimage33.png)

  ![](image%2FGit_Image%2Fimage34.png)

  ![](image%2FGit_Image%2Fimage35.png)

- 参考链接：CSDN博客·github_修改当前仓库的默认分支。[[link]](https://blog.csdn.net/xuchaoxin1375/article/details/111414527)

### 4.2 查看分支、创建分支、合并分支

- 分支git命令

| 命令                        | 解释                                  |
|:--------------------------|:------------------------------------|
| git branch                | 列出本地已经存在的分支，并且当前分支会用\*标记            |
| git branch -r             | 查看远程版本库的分支列表                        |
| git branch -a             | 查看所有分支列表（包括本地和远程，remotes/开头表示远程分支）  |
| git branch -v             | 查看一个分支的最后一次提交                       |
| git branch --merged       | 查看哪些分支已经合并到当前分支                     |
| git branch --no-merged    | 查看所有未合并工作的分支                        |
| git branch 新分支名称          | 创建分支命令                              |
| git checkout 分支名称         | 切换分支命令                              |
| git checkout -b 新分支名称     | 创建分支的同时，切换到该分支上                     |
| git branch -d 分支名称        | 删除分支（不能删除当前所在的分支，如果要删除，必须先切换到其他分支上） |
| git branch -D 分支名称        | 强制删除                                |
| git push origin :分支名称     | 分支名称前有个冒号，分支名前的冒号代表删除。              |


- 如果删除时报错：`error: The branch '分支名称' is not fully merged.`（意思是：分支未完全合并）。解决方法是使用强制删除：`git branch -D 分支名称`
- 参考链接：CSDN博客·Git详细教程（五）：查看分支、创建分支、合并分支：[link](https://blog.csdn.net/qq15577969/article/details/107632375)


## 5 快速建立本地仓库与远程仓库连接（团队常用操作）

### 5.1 配置ssh key

* 为什么要配置？
  在往github上push项目的时候，如果走https的方式，每次都需要输入账号密码，非常麻烦。而如果采用ssh的方式，就不再需要输入，只需要在github自己账号下配置一个ssh key即可。
* 怎么配置?
  - 检查本地主机是否已经存在ssh key
    ````
    cd ~/.ssh
    ls
    //如果存在id_rsa 和 id_rsa.pub文件，说明已经有SSH Key
    ````
  - 如果不存在则输入命令`ssh-keygen -t rsa -C 邮箱`，生成ssh key，如下
    ````
      ssh-keygen -t rsa -C "xxx@xxx.com" 
      // 执行后一直回车即可
    ````
  - 找到../.ssh/id_rsa.pub文件，复制文件内容
  - 在GitHub上添加公钥
    进入github网站，点击`Settings`->`SSH and GPG keys`->`New SSH key`，将复制的内容粘贴到这添加即可
  - 输入命令`ssh -T git@github.com`验证是否设置成功

### 5.2 克隆团队项目到本地

- 选择一个文件夹作为本地仓库,输入命令`git clone 链接`即可克隆项目到本地。

### 5.3 拉取

- 进入本地仓库，打开Git Bash，输入`git pull 远程仓库 分支`拉取最新的更改到本地仓库，如下所示
  ````
  git pull origin master
  ````

### 5.4 推送

- 本地仓库文件更新后，依次执行以下操作将本地仓库上传到远程仓库的某分支上
  ````
  git add .         // 将当前目录和其子目录中的所有新的或已修改的文件添加到 Git 的暂存区
  git commit -m "first commit"        // 将已经添加到暂存区的更改进行提交，提交时间如“update2023.10.18_v1”
  git branch -M master                // 重命名当前分支为 "master"，如果不需要命名，可以不执行该操作
  git remote add origin "ssh的链接"    // 如果配置了ssh key则不需要执行该步骤
  git push -u origin master           // 将本地的 "master" 分支推送到远程仓库 "origin"
  ````
  
  ![](image/Git/Quick_setup.png)


## 6 团队多人协作（进阶）
### 6.1 项目负责人（张三）新建一个项目仓库
- 登录GitHub，点击头像->Your projects->New project.

  ![](image%2FGit_Image%2Fimage6.jpg)

  <div align="left">
      <img src="image%2FGit_Image%2Fimage7.png" width="600" style="margin-right: 10px;" />
    </div>

  ![](image%2FGit_Image%2Fimage8.png)

- 克隆项目到本地

  ![](image%2FGit_Image%2Fimage10.png)

- 张三为自己负责的内容新建了个文件夹，并建了个 `.txt` 描述，将测试任务分配给大家

  ![](image%2FGit_Image%2Fimage9.png)

- 张三先新建 `Zhangsan` 分支
  
  ```
  git checkout -b Zhangsan
  ```

- 将内容 push 到远程 Zhangsan 分支
  
  ```
  git add .
  git commit -m "备注（更新时间_操作人员）"
  git push origin Zhangsan
  ```

  ![](image%2FGit_Image%2Fimage11.png)

  ![](image%2FGit_Image%2Fimage12.png)

  ![](image%2FGit_Image%2Fimage13.png)

- 此时张三本地修改了内容，即 test1 测试完成

  ![](image%2FGit_Image%2Fimage14.png)

- 张三需要将内容再次 push 到远程 Zhangsan 分支

  ![](image%2FGit_Image%2Fimage15.png)

- 但是，Zhangsan 分支未与与主分支合并，所以远程仓库会出现以下情况
  - 远程 Zhangsan 分支内容已更新
 
  <div align="left">
    <img src="image%2FGit_Image%2Fimage16.png" width="700" style="margin-right: 10px;" />
    <img src="image%2FGit_Image%2Fimage17.png" width="700" style="margin-right: 10px;" />
  </div>

  
  - 但是 main 主分支没有同步

  ![](image%2FGit_Image%2Fimage18.png)

- 所以，多人协作时，不仅要将本地仓库 push 到远程分支，还要与主分支合并，确保主分支内容最新，方便别人拉取最新内容。命令如下
  ```commandline
  git checkout main     # 切换分支
  git merge origin Zhangsan  # 合并
  git push origin main  # 推送
  ```

  ![](image%2FGit_Image%2Fimage19.png)

- 此时远程 main 分支就更新了。

  ![](image%2FGit_Image%2Fimage20.png)

  ![](image%2FGit_Image%2Fimage21.png)


### 6.2 项目负责人邀请他人（李四）加入项目
- 先在GitHub上邀请他人并给与相应push权限。

  ![](image%2FGit_Image%2Fimage22.png)

- 他人接受邀请，加入项目后，将项目通过ssh将项目clone到本地
  
  <div align="left">
      <img src="image%2FGit_Image%2Fimage36.png" width="500" style="margin-right: 10px;" />
    </div>


  ![](image%2FGit_Image%2Fimage37.png)

  ```
  git clone <地址>
  ```
- 新建本地分支

  clone 下来默认是在主分支 main 下，所以李四需要新建自己的本地分支

  ```
  git checkout -b Lisi
  ```
 
  ![](image%2FGit_Image%2Fimage39.png)

- 更新内容

  在文件夹中新建一个txt文件，李四完成了测试，更新以下。
  
  ![](image%2FGit_Image%2Fimage38.png)
  

- 修改好后，push到自己远程分支

  ![](image%2FGit_Image%2Fimage40.png)

  现在李四远程分支上有了最新内容，但是 main 分支上没更新
  
  ![](image%2FGit_Image%2Fimage41.png)

  <div align="left">
      <img src="image%2FGit_Image%2Fimage42.png" width="500" style="margin-right: 10px;" />
    </div>

- merge 自己分支与主分支

  <div align="left">
      <img src="image%2FGit_Image%2Fimage43.png" width="500" style="margin-right: 10px;" />
    </div>

  此时，main 分支已经同步了 Lisi 的最新内容，搞定！！
 
  <div align="left">
    <img src="image%2FGit_Image%2Fimage44.png" width="500" style="margin-right: 10px;" />
   </div>


### 6.3 总结
- 成员每次推送之前，都应先把最新的版本pull到自己的本地分支。
- 更新好内容后，先推送到远程分支，再与主分支合并。

- 首次加入并更新项目
```
git clone <地址>    # 克隆项目
git checkout -b <新分支名>

# 修改完提交（在新分支中）
git pull origin <主分支>  # 拉取最新内容

git add .     # 首次修改
git commit -m "备注"
git push origin <新分支>
git checkout <主分支>
git merge <新分支>
git push origin <主分支>
```

- 非首次更新项目
```
# 拉取最新内容
git checkout <新分支>
git pull origin <主分支>

# 修改完提交
git add .    
git commit -m "备注"
git push origin <新分支>
git checkout <主分支>
git merge <新分支>
git push origin <主分支>
```

### 遇到的问题及解决方案
- 【Github】ssh: connect to host github.com port 22: Connection refused
  - 解决方法：[CSDN 博客](https://blog.csdn.net/weixin_43835470/article/details/135642699)