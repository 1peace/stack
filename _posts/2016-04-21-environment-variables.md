---
layout: post
title:  "Environment Variables"
date:   2016-04-21
categories: develop
---

## Mac 启动加载文件位置（可设置环境变量）

### 1. 首先要知道你使用的Mac OS X是什么样的Shell，使用命令

```
echo $SHELL
```

- 如果输出的是：`csh`或者是`tcsh`，那么你用的就是C Shell
- 如果输出的是：`bash`，`sh`，`zsh`，那么你的用的可能就是Bourne Shell的一个变种

- Mac OS X 10.2之前默认的是C Shell
- Mac OS X 10.3之后默认的是Bourne Shell

### 2. 如果是Bourne Shell，那么你可以把你要添加的环境变量添加到你主目录下面的`.profile`或者`.bash_profile`，如果存在没有关系添加进去即可，如果没有生成一个

__Mac配置环境变量的地方__

#### 1. `/etc/profile`（建议不修改这个文件）

全局（公有）配置，不管是哪个用户，登录时都会读取该文件。

#### 2. `/etc/bashrc`（一般在这个文件中添加系统级环境变量）

全局（公有）配置，bash shell执行时，不管是何种方式，都会读取此文件。

#### 3. `~/.bash_profile`（一般在这个文件中添加用户级环境变量）

每个用户都可使用该文件输入专用于自己使用的shell信息,当用户登录时,该文件仅仅执行一次!

---

## MAC 修改host文件

```
sudo vi /etc/hosts
```

---

## Linux下查看和添加PATH环境变量

__PATH的格式为：__

`PATH=$PATH:<PATH 1>:<PATH 2>:<PATH 3>:------:<PATH N>`，中间用冒号隔开。

__添加PATH环境变量：__

```
export PATH=$PATH:/path/to/dir1
```

__查看PATH环境变量：__

```
echo $PATH
```

__操作示例：__

```
vi .bash_profile
export PATH=$PATH:/path/to/dir1
:wq

# 立即生效（不报错则成功）
source /etc/profile
source .bash_profile
```
