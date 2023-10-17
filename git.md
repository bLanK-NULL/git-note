# git 基本使用
git 分为3个区

* 工作区 —— 存放文件
* 暂存区 —— 工作区变更，提交到暂存区
* 版本库 —— 暂存区的内容，提交到版本库

status颜色
* 红: 工作区变更了,但是**没有提交到暂存区**,此时 `git checkout .` 会撤回变更无法找回
* 绿: 已经提交到暂存区
* 无: 都被git管理起来了

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

> 空文件夹不会被git管理

# git 忽略文件

1. 根目录下新建`.gitignore`文件
2. 在里面写需要忽略的文件
    ```
    mode_models  # 直接忽略该目录
    .idea  # 忽略 该文件
    *.log  # 忽略 以.log结尾的文件
    ```

# git 多分枝

小公司常用方案: master分支、dev分支、bug分支 、个人分支

常用分支操作

```bash
git branch #查看已建立的分支

git branch 分支名   # 建立分支

git checkout 分支名 # 切换分支

git merge 分支名    # 合并分支
```

> 合并分支核能出现冲突, 怎么解决?



