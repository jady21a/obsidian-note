Git 是目前世界上最先进的分布式版本控制系统
![[Pasted image 20220303204210.png]]
# 安装
用户签名   （首次安装须设置）
```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```
 初始化本地库（建仓库）
在所需初始化的目录下右键 git bash

### git init
###添加文件管理（暂时存档到本地，跟踪）//add 一次之后后续可省略 add 直接 commit 错误（须 add 后才能 commit）

### git add <file.txt>         
批量添加
git add .
git add --all

//不追踪   git rm --catched <file.txt>
提交改变（交付本地）
### git commit       

git commit -m `message`   -m//可省略输入修改备注

 查看状态

### git status
查看修改
git diff 《file》 commit后不可查看
用 `git diff HEAD -- readme.txt` 命令可以查看工作区和版本库里面最新版本的区别
![[Pasted image 20220304200957.png]]
查看文件
ll

查看历史记录
1. git log
2. git log -pretty=oneline
3. git log --oneline　　　只显示过去
4. git log reflog　　　　　显示所有记录　**

回到某一版本
git reset --hard <版本索引值>

丢弃工作区的修改， `git checkout -- file`
丢弃 add 操作，git reset HEAD `file`
添加到了暂存区时，想丢弃修改，分两步，第一步用命令 `git reset HEAD <file>`，就回到了工作区，第二步按工作区 操作。


## ssh 免密登录
$ cd ~
$ rm -r .ssh/
$ ssh-keygen -t rsa -C xyzjady21@outlook.com    enter *n
$ cd .ssh/

$ ll
total 5
-rw-r--r-- 1 jady 197121 2610 Mar  5 01:58 id_rsa
-rw-r--r-- 1 jady 197121  575 Mar  5 01:58 id_rsa.pub
$ cat id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQD5gv984V5/u8anSt+jLV08FTDZy7Qnkm88HWjN+gMykqvCr0kAu/U5YL3Xp7oO4YEWmiNQyXrQuI48ppKEUGCKJFq9b2y4nTH6YKMiEB70uyuvzng6qWC3wAVLFkyzSB98eHpw00Pe08BawAm9Q2uojSvrksCAM4m1Km1Zkpi+GJliybTl+tR1QXmUO4N4+5pA0hlr6R4bxHl/zhK2SX3QpsBk/hARyeefKVR8kp7OD1VdgmcZErtCzN2VVnO+vxMDU/L6GlB8ZUffY+KD1+j6DJinCTYi5a8ZKo+LLo5FHeMasia6PGY1cIiEIcnVT5pOjZ80r3qPzk5IjRXvgfh99M7WzZktuIwc1CquTzjow4zUDdPg6Qm3BEdcC51UU56vz89bE7FYE1qwhrBFtOjHQHuB6E8KS3+60ZKyXTiIoOyjf/fVWlqVNp50iM2Y073g23akO2ArIjc7eXOYk6NEBt8GTltzM1SelvhVyvOWPAkoC1syU4Zw/OSVGgjiEkk= xyzjady21@outlook.com

# 文件 push 到 github
$ git remote add key_ssh git@github.com: jady21a/git-test.git

## $ git  remote add origin git@github. com: jady21a/git-test. git

## git push origin master


jady@LAPTOP-LNHLN54O MINGW64 /newfile/gitdemo (master)
<<<<<<< HEAD
 $ git push key_ssh   master
=======
$ git push key_ssh master
$ git push  origin  main
>>>>>>> 4f235e5bd3fad3ba4b698b038964a9ea715e4eca

**//$ git push  origin  main**
###### 从github clone  //无需ssh
$ git clone git@github.com:jady21a/photo.git

## 分支 branch
切换分支     $ git checkout 《branch name》or git switch `name`
创建并切换到dev分支    
```$ git checkout -b dev```    //b  branch
```$ git switch -c dev```  //new version   c?
切换到已有的 `master` 分支
```
$ git switch master
```
 命令查看当前分支  `git branch`

把 `dev` 分支的工作成果合并到 `master` 分支上    //合并指定分支到当前分支
```
$ git merge dev
```
删除 `dev` 分支
```linux
$ git branch -d dev
```

解决冲突 tbc

bug分支

tag


# git 快捷键-
$ git config --global alias.stt status         //配置方法

| 指令    | =            |
| ------- | ------------ |
| stt     | status       |
| cm      | commit       |
| co      | checkout     |
| unstage | 'reset HEAD' |
| last    | 'log -1'     |
last //显示最后一次提交信息


不同文件夹下的txt文件不能提交
先pull 后push
push 后github仓库没有出现文件名
建库时选了readme

怎么在git用vs code编辑 Q


[git-cheat-sheet (gitee.io)](https://liaoxuefeng.gitee.io/resource.liaoxuefeng.com/git/git-cheat-sheet.pdf)
![[Pasted image 20220304151324.png]]


rf：
1.[自定义 Git - 廖雪峰的官方网站 (liaoxuefeng.com)](https://www.liaoxuefeng.com/wiki/896043488029600/900785521032192)
2.https://www.bilibili.com/video/BV1pW411A7a5?p=42



# lfs  large file storage
```
$ git lfs install
```

```
$ git lfs track "*. zip"
```

```
$ git add .gitattributes
```

```
$ git commit -m "track *.zip files using Git LFS"
```

```
$ git push origin master
```

Q:
ssh: connect to host github.com port 22: Connection timed out
fatal: Could not read from remote repository.
A: 
$ ping github. com
