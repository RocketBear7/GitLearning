# Git



## Git简介

Git 是一个分布式版本控制系统。

GIt的缔造者是大名鼎鼎的林纳斯·托瓦茲 (Linus Torvalds)，Git 最初的目的是为了能更好的管理 Linux 内核源码。

## Git安装

Git官网：https://git-scm.com/

Git中文网：https://git.p2hp.com/

**1.前往官网下载对应系统的安装包，然后傻瓜式安装（一路next）**

![image-20240829162241668](C:\Users\14461\AppData\Roaming\Typora\typora-user-images\image-20240829162241668.png)

**2.检验Git是否安装成功**

![image-20240831162045898](./assets/image-20240831162045898.png)

## Git安装完成后的必要配置

安装完成后，还需要最后一步设置，在命令行输入：

```bash
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。你也许会担心，如果有人故意冒充别人怎么办？这个不必担心，首先我们相信大家都是善良无知的群众，其次，真的有冒充的也是有办法可查的。

注意`git config`命令的`--global`参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。

## 基础命令

| 命令                                        | 说明                                                         |
| ------------------------------------------- | ------------------------------------------------------------ |
| **git config --global user.name \<name>**   | 配置当前仓库用户名，使用--global参数对当前系统登录用户的所有本地仓库都生效。 |
| **git config --global user.email \<email>** | 配置当前仓库用户邮箱，使用--global参数对当前系统登录用户的所有本地仓库都生效。 |
| **git init \<directory>**                   | 创建指定目录并将其设为本地仓库，不带参数则将当前目录初始化为一个本地仓库。 |
| **git clone \<repo>**                       | 将指定仓库克隆到本地，指定的仓库可以是由HTTP或SSH指定的远程路径。 |
| **git add \<directory>**                    | 将指定目录的所有修改添加到下一次commit中。也可以只指定某个文件。也可以使用.添加所有修改到。 |
| **git commit -m  "\<message>"**             | 提交暂存区的修改，使用指定的message作为提交信息。            |
| **git status**                              | 显示哪些文件未被跟踪、未被暂存或者已被暂存但尚未提交。       |
| **git log**                                 | 以缺省格式显示全部commit历史，其后可以跟上很多选项。         |
| **git log --oneline**                       | 每行显示一条commit。                                         |

## 远程仓库

| 命令                                   | 说明                                                         |
| -------------------------------------- | ------------------------------------------------------------ |
| **git remote add \<name> \<url>**      | 添加一个新的远程仓库，添加后可用\<name>作为指定\<url>远程仓库的名字。 |
| **git pull \<remote>**                 | 从指定\<remote>抓取所有分支的commit并立刻合并到本地仓库。    |
| **git fetch \<remote> \<branch>**      | 从远程抓取指定分支的所有commit到本地。去掉将\<branch>将抓取远程所有分支的修改。 |
| **git push \<remote> \<local_branch>** | 将当前分支推送到指定的远程仓库 。如果远程没有对应的分支，将自动在远程创建此分支。 |

## 时空穿梭

| 命令                              | 说明                                                      |
| --------------------------------- | --------------------------------------------------------- |
| **git rm --cached \<file>**       | 将指定目录或文件从暂存区删除。                            |
| **git restore \<file>**           | 撤销工作区的修改，使其恢复到最近一次add或commit时的状态。 |
| **git reset --hard \<commit_id>** | 将当前版本回退到commit_id指定的版本。                     |

## 分支

| 命令                         | 说明                                |
| ---------------------------- | ----------------------------------- |
| **git branch**   |查看所有分支|
| **git branch \<branch_name>** | 创建名为branch_name的分支           |
| **git switch \<branch_name>** | 切换到名为branch_name分支           |
| **git switch -c \<branch_name>** | 创建+切换到名为branch_name的分支    |
| **git merge \<branch_name>** | 合并名为branch_name的分支到当前分支 |
| **git branch -d \<branch_name>** | 删除名为branch_name的分支         |

