## 疑惑

1. 克隆了 main 分支的代码到本地的 main 文件夹
2. 本地新建了 login 和 register 文件夹
   login index.html + login.html
   register index.html + register.html
3. 然后 login 和 register 分别写代码
   login -> 提交到远程的 login 分支
   register -> 提交到远程的 register 分支
4. 然后在 main 文件夹
   git fetch 拉下远程的所有分支
   git merge origin/login -> 尝试先合并 login index.html 里面的文件能够合并
   但是问题出在 main 分支里面并没有出现 login 文件里面的 login.html

>哦！再次试验了一次！能成功！加油哇

## 快捷小册子：

```bash
# 0.拉取代码
git pull
# 1.提交代码
git add .
# 2.提交到暂存区
git commit -m "备注"
# 和远程的某个仓库建立连接
git remote add origin 仓库名
# 断开和远程某个仓库的链接
git remote remove origin 仓库名
git add remote
# 3.提交到远程仓库
git push origin 本地分支名：远程分支名
# 4.快速新建一个分支，并且切换
git checkout -b 新分支的名字
# 5.仅仅切换分支，没有新建分支
git checkout 分支名字
# 6.拉下远程的所有分支
git fetch
# 7.合并一个分支 比如在main分支 要合并login分支的代码
# 注意，前面跟仓库名 默认是origin
# 注意 合并完之后 要提交 才能够进行下一次合并
git merge origin/login
# 8.查看当前分支
git branch
# 9.查看提交记录
git log
# 10.查看提交的具体细节
git diff
# 查看当前的状态
git status
# 11.将当前的修改放到一个宝箱，暂时不管。
git stash
-> 切换到另一个分支 git checkout 另一个分支
git stash pop -> 这样能够把刚刚的修改弄出来 适合，在错误的分支上改了代码 想要挽回

# 11. 回退
git checkout . 撤销所有的操作

# 12. git rebase 和 git merge的区别
都是合并
rebase是重新换了一个基点，能够得到更加简洁的历史，分支不会那么混乱
merge是合并，会保留之前合并的各个分支，如果项目更加的庞大，就会导致分支更加的混乱。

# 13. git reset 和 git rebase的区别
git reset --hard 版本号 回退到某一个版本 "是回退的操作"
git revert -n 版本号 是撤销某一个版本的操作，比如这个版本，你添加了文件，那么撤销就是 删除这个文件。放好返一下 "是前进的操作"
- 比如新建了 a.txt b.txt c.txt revert能够指定的不要 “新建 b.txt这个操作”

```



git rebase 和 git merge的区别是什么？

<img src="https://typora-1309613071.cos.ap-shanghai.myqcloud.com/typora/image-20221010184753037.png" alt="image-20221010184753037" style="zoom:50%;" />





**git reset 和 git revert的更多指令**

```js
https://blog.csdn.net/tilblackout/article/details/124559992?ops_request_misc=&request_id=&biz_id=102&utm_term=git%20revert%20--hard%E6%98%AF%E4%BB%80%E4%B9%88&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-1-124559992.142^v52^js_top,201^v3^control_2&spm=1018.2226.3001.4187
```





# 1. 开源

开源的概念：

开放源代码

程序和源代码都开放，其他作者可以下载、修改、使用

闭源的定义:

只有作者能够看件源代码

其它作者只能看见程序，但是看不到源代码。

# 2. 开源许可协议

开源，不意味着没有限制，

有限制使用者和保护作者的需求

所以每个开源项目都要遵循开源许可协议

五大开源许可协议：

BSD

Apache Licence 2.0

**GPL：**

**·具有传染性**，你的项目使用的一块内容有 GPL 协议，那么你的项目也要满足 GPL 协议

**·强制开源**，不能闭源作为商业项目；

·著名的有 Linux，是开源的操作系统；其基础上开发的软件都是开源的

LGPL

**MIT：**

目前限制最少的协议，

修改后的代码或者发行包中必须包含原作者的许可信息

著名的有：jquery，Node.js

# 3. 为什么要开源

·开源，人人为我，我为人人

·给予使用者更多的权限

·能够有助于使用者的学习

·更加安全，人多力量大发现更多的 bug

# 4. 开源项目托管平台

免费存放开源项目的源代码的平台

出名的：

Github：全球最牛，没有之一，

Gitlab：私有性支持好，企业用户多

Gitee：国产，界面友好，速度快

以上都只支持 Git 的管理工具

# 5. Github

## 5.1 定义

全球最大的开源项目托管平台

call-打 call

Pull Request-做贡献

Issues-和作者讨论 bug 和需求

Fork-复制项目进行修改

创建属于自己的开源项目

只支持 Git 作为唯一的版本控制工具，但是不等于 Git，功能更多

## 5.2 用法

### 5.2.1 注册账号

### 5.2.2 开辟一个新的仓库

<img src="C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211102205036180.png" alt="image-20211102205036180" style="zoom: 50%;" />

### 5.2.3 SSH 和 HTTPS 的区别

是什么：？

远程仓库的两种访问方式

区别：

- HTTPS。零配置，但是每次访问仓库时，都要重复输入账号和密码
- SSH。需要配置，但是每次从访问时，不用重复输入账号和密码

### 5.2.4 git 仓库内容导入到 Github

```
git remote add origin https://github.com/lizhihang123/project_01.git
git branch -M main
git push -u origin main
```

现有的这个代码

![image-20211102205359198](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211102205359198.png)

### 5.2.4 什么是 SSH

- 是 github 和本地仓库之间免登录和加密传输的一种访问方式
- 好处：1.免登录 2. 数据加密传输
- 由两部分组成：1.id_rsa 私钥文件，存放到本地 2. id_rda.pub 公钥文件，配置到 github

### 5.2.5 怎么配置

- 打开 Git Bash

- 粘贴命令

  ```
  ssh-keygen -t rsa -b 4096 -C "2420554367@qq.com"
  ```

- 连续敲击三次回车

<img src="C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211103203632404.png" alt="image-20211103203632404" style="zoom:50%;" />

这样表示设置成功

- 在如下路径查看是否有这两个文件

- <img src="C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211103204127925.png" alt="image-20211103204127925" style="zoom:50%;" />

- 复制 id_rsa.pub 文件里面的代码

- 点击头像-点击 settings

  <img src="C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211103204308409.png" alt="image-20211103204308409" style="zoom:50%;" />

  - 点击左侧的 SSL GBG keys

    <img src="C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211103204356623.png" alt="image-20211103204356623" style="zoom: 33%;" />

  - 点击增加

    ![image-20211103204444094](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211103204444094.png)

  - 复制代码即可，在 Title 里面取一个 key 的任意名字

    <img src="C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211103204501306.png" alt="image-20211103204501306" style="zoom:50%;" />

### 5.2.6 怎么判断是否配置成功

![image-20211103204912208](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211103204912208.png)

- ```
  ssh -T git@github.com
  ```

![image-20211103204959282](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211103204959282.png)

- ```
  输入yes
  ```

显示这段文字，表示配置成功

![image-20211103205023556](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211103205023556.png)

### 5.2.7 把本地仓库通过 SSH 导入到 github 仓库

- 本地文件导入到本地仓库

  - git init
  - git status
  - git add .
  - git status
  - git commit -m “”

- github 新建一个仓库，github 的仓库名可以和 git 的文件夹名不一致

- f 分别执行三串命令

- ```
  git remote add origin git@github.com:lizhihang123/pro_02.git
  git branch -M main
  git push -u origin main
  ```

- 最终看到图示效果，表示导入到 github 成功

  <img src="C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211103212009207.png" alt="image-20211103212009207" style="zoom:50%;" />

### 5.2.8 把 github 的代码克隆到本地

场景：本地的代码不小心删了

- 点击对应的仓库
- 选择 Code
- 点击 SSH
- 点击复制按钮
- 输入如下代码
- 显示 100%, 即可成功

```
git clone 对应的地址
```

![image-20211104091303265](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104091303265.png)

## 5.2.9 gitee

如果是 gitee 怎么操作？

```
mkdir heimatoutiao
cd heimatoutiao
git init
touch README.md
git add README.md
git commit -m "first commit"
git remote add origin https://gitee.com/Lizhihang123/heimatoutiao.git
git push -u origin "master"
```

如果是 SSH 就写

```
git remote add origin git@gitee.com:Lizhihang123/heimatoutiao.git
git push -u origin "master"
```

# 6. 分支

## 6.1 什么是分支？

平行宇宙，一个宇宙里面你在学习 Git，另一个宇宙里面你在学习 SVN。

正常情况下，这两个宇宙是互不干扰的，是两个分支。

但是一旦合并了，那么你就同时学会了 git 和 SVN。

在开发中的实际运用：

不同的工作人员有不同的任务要完成，要实现不同的功能，在不同的分支。

他们各自的任务做完了以后，合并到了一起，这个主轴就拥有了很多的功能。

<img src="C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104092151799.png" alt="image-20211104092151799" style="zoom:50%;" />

## 6.2 main 主分支

记录和保存程序的所有的代码

不允许程序员直接在 main 主分支上进行操作，这样风险很高，容易一不小心删除了所有的代码

所以程序员创建一个分支，做好了，再合并到 main 主分支上

## 6.3 功能分支

也就是 6.2 提到的不能直接在 main 分支上进行操作，那么就要有功能分支，在功能分支上进行操作，然后合并到 main 主分支。

注意：

main 主分支，全程都存在，生命周期长

功能分支，生命周期短，一合并，就没了。

## 6.4 查看分支

查看当前有哪些分支

带星号的是当前所处的

```
git branch
```

![image-20211104094512280](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104094512280.png)

## 6.5 创建分支

创建 login 分支

注意：此时只是单单创建，但是并没有跳转到 login 分支上，仍旧在 main 分支上

```
git branch login
```

<img src="C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104094617886.png" alt="image-20211104094617886" style="zoom:67%;" />

## 6.6 如何切换分支

切换到 login 分支上

```
git checkout login
```

![image-20211104094638287](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104094638287.png)

![image-20211104094718034](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104094718034.png)

## 6.7 快速跳转分支

先跳转到主分支上

```
git checkout main
```

注意：使用这行代码 前必须先执行上面那行代码。意思是，在主分支上，才能创建一个新的分支并跳转到新的分支上。

不能在别的分支上面创建新的分支并跳转

```
git checkout -b 分支名字
```

![image-20211104094746494](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104094746494.png)

## 6.8 合并分支

- 切换到功能分支

- ```
  git checkout reg3
  ```

- 进行修改操作

- 切换到 main 主分支

- ```
  git checkout main
  ```

- 进行合并

- ```
  git merge reg3
  ```

  发现 主分支上也有这个操作

## 6.9 删除分支

- 切换到 main 分支先

```
git checkout main
```

- 再删除

```
git branch -d reg3
```

如果在 reg3 上面删除，reg3 分支，就会报错

![image-20211104100830290](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104100830290.png)

下面流程才是对的：

<img src="C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104100848625.png" alt="image-20211104100848625" style="zoom:50%;" />

## 6.10 遇到冲突时的合并

- reg1

  - 切换到 reg1
  - 修改内容
  - 提交到暂存区并上传到 git 仓库

- main

  - 切换到 main

  - 修改内容

  - 提交到暂存区并上传到 git 仓库

  - 合并

  - ```
    git merge reg1
    ```

  - 要手动修改

    - ![image-20211104101401309](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104101401309.png)

      一个是接受 main 的;接受传入文件的；都保留；比较不同

  - 必须分别执行以下两端代码

    - ```
      git add .
      ```

    - ```
      git commit -m "提交内容"
      ```

      ![image-20211104101639945](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104101639945.png)

## 6.11 代码从本地推送到远程分支

git push -u 远程仓库的别名 本地分支的名称：远程分支的名称

远程仓库的别名写 origin，默认情况都写这个

本地分支的名称写要推送过去的功能分支的名字

远程分支的名称随便取

不取默认和本地分支的名称一致

```
git push -u 远程仓库别名 本地分支名:远程分支名称
```

<img src="C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104105712702.png" alt="image-20211104105712702" style="zoom:50%;" />

注意：如果 github 已经有这个分支了，那么下一次命令只写如下即可

```
git push
```

## 6.12 查看远程仓库的分支信息

```
git remote show origin
```

show 后面跟的是远程仓库的别名 默认是 origin

![image-20211104110152160](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104110152160.png)

## 6.13 从远程仓库下载分支到本地 / 跟踪分支

**这个是下载仓库喽**

直接下载，分支名字和远程仓库的分支名字一致

```
git checkout reg1ister
```

reg1ister 是远程仓库的一个分支名

下载的同时改名字

```
git checkout reg origin/reg1ister
```

- reg 是想要修改的名字

- origin 是想要下载内容的远程仓库的别名

- reg1ister 是从远程仓库下载的内容的别名

## 6.14 把远程分支的最新代码下载本地的对应分支

- 先在 github 上面修改编辑代码

  - ![image-20211104122425602](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104122425602.png)

  - ![image-20211104122455344](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104122455344.png)

  - 编辑内容，下面添加第二个方框的描述性语言

  - 在本地的 git，添加命令

    ```
    git pull
    ```

    - 本地记得切换到相同的分支，查看相同文件的 代码 发现也发生了变化

## 6.15 删除远程仓库的分支

- 在 git 执行

  - ```
    git push origin --delete reg1ister
    ```

  - 在远程仓库刷新一下即可发现没有这个分支了

- 区别：在本地删除对应的分支

  - ```
    git branch
    ```

    - 先切换到 main 分支

    - ```
      git checkout main
      ```

  - ```
    git branch -d reg1ister
    ```

  - ```
    // 发现显示没有充分合并
    //git branch -D reg1ister
    ```

    ![image-20211104123145808](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20211104123145808.png)

## 6.16 断开本地与远程仓库链接

```shell
git remote remove origin
```
