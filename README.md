# GitFlowPractice
## GitFlow工作流

> Vincent Driessen曾经写过一篇博文，题为 `A successful Git branching model`（一个成功的Git分支模型）。Gitflow工作流程就是从这篇文章里来的。
>
> Gitflow工作流程围绕项目发布定义了严格的分支模型。其特色在于，它为不同的分支分配了非常明确的角色，并且定义了使用场景和用法。除了用于功能开发的分支，它还使用独立的分支进行发布前的准备、记录以及后期维护。

<br/>

![GitFlow工作流图解](./Images/git-flow最终图.png)

<br/>

## 分支介绍

| 分支    | 作用                       |
| ------- | -------------------------- |
| master  | 历史迭代分支               |
| develop | 集成最新开发特性的活跃分支 |
| f_xxx   | feature 功能特性开发分支   |
| b_xxx   | bug 修复分支               |
| r_xxx   | release 版本发包分支       |

<br/>

## 初步流程

> 每家公司的 `GitFlow` 工作流，都不一样。我们采用如上 `GitFlow` 简单模拟一下
>
> 顺便熟悉一下 `Git` 如何对项目协作开发。

```python
git clone `url`

git checkout origin/dev	# 切换到远程分支

git branch -b dev		# 创建本地分支

git branch --set-upstream-to=origin/dev		# 把本地分支映射到远程分支上
```

<br/>

每次写代码建分支前都要保证 `dev` 是最新代码

```python
git checkout dev

git pull
```

<br/>

最终提交合并请求 `merge request`

```python
# 新建功能分支，并映射到remote
git checkout -b f_login
# git branch --set-upstream-to=origin/f_login

# 接下就自主开发
git add xxx
git commit -m'xxxx'

git add xxx
git commit -m'xxxx'

# 最后提交到remote
# git push --set-upstream origin f_login
git push
```

<br/>

删除已开发完毕的功能分支

```python
git checkout dev 

git pull

git branch -d f_login

git branch -dr origin/login
```

<br/>

又新增开发功能，重复上述步骤

```python
git checkout -b f_register
# git branch --set-upstream-to=origin/f_register

git add xxx
git commit -m'xxxx'

git push
```

<br/>

## 冲突解决

### 方案一

在 `Github` 网站上手动解决冲突

<br/>

### 方案二

```python
# 拉取远程分支
git fetch origin develop

# 让本地当前分支与远程分支进行比较
git branch diff origin/develop 
```

比较哪里不一样、哪里有冲突，进行修改后重新提交

```python
git add xxx
git commit -m'xxx'

git push
```

<br/>

### 方案三

```python
在本地分支同步(拉取)远程分支
git pull origin develop

会发现自动合并不了，检查冲突文件，然后进行修改
修改完成然后在进行提交

git add 冲突文件
git commit -m'xxx'
git push


```

