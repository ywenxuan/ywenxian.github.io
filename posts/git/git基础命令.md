# Git基础个人总结（简）

## 一、四个工作区

### 1.WorkSpace：工作目录

本地文件夹，用于存放项目代码

### 2.Stage/index：暂存区

用于临时存放你的改动，事实上它只是一个文件，保存即将提交到文件列表信息

通过【git add .】将工作内容添加到暂存区

### 3.Repository：资源库（本地仓库）

就是安全存放数据的位置，这里面有你提交到所有版本的数据。其中HEAD指向最新放入仓库的版本

通过【git commit -m "工作信息message"】将暂存区的内容提交到本地仓库

### 4.Remote：远程仓库

通过【git push -u origin(远程仓库名) master(当前分支名)】将本地仓库提交到远程仓库

![上传流程及命令](\picture\上传流程及命令.png)

## 二、文件四种状态

1. Untracked:未追踪

   将文件放到文件夹中，没有加入到git仓库，不参与版本控制。

2. 已追踪（加入到仓库）

   1. Unmodify:文件未修改
   2. Modified:文件已修改

3. Staged:暂存状态

![四种状态](\picture\四种状态.png)

## 三、基本命令

| git init                                              | 在当前目录新建一个Git代码库       |
| ----------------------------------------------------- | --------------------------------- |
| **git remote add [shortname] [url]**                  | **添加远程仓库**                  |
| **git remote show **                                  | **查看远程库**                    |
| **git add .      **                                   | **添加所有文件到暂存区**          |
| **git status [filename]**                             | **查看指定文件状态**              |
| **git status**                                        | **查看所有文件状态**              |
| **git commit -m "消息内容" **                         | **提交暂存区中的内容到本地仓库 ** |
| **git push -u origin(远程仓库名) master(当前分支名)** | **将本地仓库提交到远程仓库**      |
| **git clone [url]**                                   | **克隆远程仓库**                  |
| **分支操作**(暂时不清楚，用到再说)                    |                                   |
| **git branch**                                        | **列出所有分支**                  |
| **git branch (branchname)**                           | **创建分支**                      |
| **git checkout (branchname)**                         | **切换分支**                      |
| **git branch -d (branchname)**                        | **删除分支**                      |
| **git merge**                                         | **合并分支**                      |
|                                                       |                                   |
|                                                       |                                   |
|                                                       |                                   |
|                                                       |                                   |
|                                                       |                                   |

