# git 基本使用

git 分为 3 个区

- 工作区 —— 存放文件
- 暂存区 —— 工作区变更，提交到暂存区
- 版本库 —— 暂存区的内容，提交到版本库

<!-- more -->

status 颜色

- 红: 工作区变更了,但是**没有提交到暂存区**,此时 `git checkout .` 会撤回变更无法找回
- 绿: 已经提交到暂存区
- 无: 都被 git 管理起来了

```bash
git status # 查看文件状态（红）

git add . # 工作区-> 暂存区（变绿）

git rest HEAD # 把暂存区 -> 工作区（由红红变绿）

git checkout . #工作区 变更撤回
```

```bash
git commit -m '注释' # 暂存区 -> 版本库

git log  # 查看版本库 详细
```

> 空文件夹不会被 git 管理

# git 忽略文件

1. 根目录下新建`.gitignore`文件
2. 在里面写需要忽略的文件
   ```
   mode_models  # 直接忽略该目录
   .idea  # 忽略 该文件
   *.log  # 忽略 以.log结尾的文件
   ```

# git 多分枝

小公司常用方案: master 分支、dev 分支、bug 分支 、个人分支

常用分支操作

```bash
git branch #查看已建立的分支

git branch 分支名   # 建立分支

git checkout 分支名 # 切换分支

git merge 分支名    # 合并分支

git pull origin master
```
> git pull:
>  1. 暂存区 工作区 版本库 都会被替换成远程仓库分支的版本。

# git 搭建远程仓库

github:
创建一个空仓库

本地:

```bash
git init
git add .
git commit -m 'comment'

git remote add origin 仓库路径 #添加一个远程仓库地址名字叫origin（仅本地有效）
git push origin master # 把本地版本库-> origin对应的远程仓库的master上
```
> origin: 在本地仓库中对远程仓库起的别名, 一般叫origin
```bash
git clone 仓库地址
```

> 出现冲突, 怎么解决?

## 冲突情况

1. 多人开发同一分支
2. 不同分支同一文件被修改,然后merge

> 解决: 多pull



