# 2356360027.github.io  

# Git/GitHub~大学生入门级版本控制教学
## 目录  
[前言](#前言)  
[什么是Git/GitHub?](#什么是gitgithub)  
[下载Git](#下载git)  
[GitHub注册](#github注册)  
[git的基本操作（版本管理）](#git的基本操作版本管理)  
[分支/branch（合作开发）](#分支branch合作开发)  
[**项目的开发流程规则（Git Flow/GitHub Flow）！！！！**](#项目的开发流程规则git-flowgithub-flow)  
[GitHub](#GitHub)  
[SHA-1码](#sha-1码)   
[后言/叠甲](#后言叠甲)

## 前言
        本文是一个简单介绍Git的使用方法的文章。目的是帮助各位大学生对Git和GitHub有一个简单的入门了解。从而达到用Git来对自己项目的版本有序控制与更新，甚至用GitHub实现多人共同开发。  
        其实早有一些软件可以实现可视化操作，可以更简单的实现Git的操作。但是基础操作更能让我们理解Git的基层，让我们理解更加深刻，打好结实的基础。但是不是说不建议学习可视化操作软件。相反，我还希望大家在学习了基础操作后去认真学习一下。  
        

## 什么是Git/GitHub?
用专业的语言来说：“Git是一款分布式版本的版本控制系统”，是一个软件。而GitHub是一个网站，其本体是一个巨大的服务器（线上Git服务器）。  

        按我的理解来说，git有俩个功能，一个是版本管理，另一个是合作开发。  
        1. 版本管理：大家都知道存档点吧，而git就是一个可以帮你记录存档点的本地存档器软件。你可以记录并随时回到你项目的某个版本。  
        2. 合作开发：这个软件不仅可以记录你的存档，还可以和小伙伴一起完这个项目。你可以把你的存档“复制”一份出去，让他接着你的存档玩。如果你觉得他的存档玩的比你好的话，你们的存档还能合并，共享彼此的进度。
GitHub是一个网站，一个分享自己本地存档的服务器，也是一个远程仓库。  

        在这个网站上可以通过按钮简单的操作，就能实现比较复杂的Git操作。同时也可以分享一些不错的项目。同时，他也是非常棒的开发者履历平台。当然，你同样可以找一些优质项目借鉴一下子。  
        (～￣▽￣)～  
        还有一件事~（老爹音）：  
        值得一提的是，GitHub网站项目的借鉴可以不用注册账号，甚至不用学会git，直接下载压缩包。对小白非常的友好。当然这样干的话也会丢失项目之前的存档，或者说是历史记录。  
## 下载Git
        想要用git来管理你的项目，那当然得先把git下载下来呀。但是git的下载这里不多介绍，给大家推一篇csdn博客指路。讲的也是非常详细的。
[csdn博客链接在此][csdn博客：git下载]  
- 这里建议把编译器设置成VS code，但如果你向和Vim激情对线的话另当别论  
o(*￣▽￣*)o
## GitHub注册  
        注册的话相信对于各位混迹于互联网多年的“分号斗罗”简简单单。此处附上GitHub官网。
[GitHub官网][GitHub官网]       

        GitHub注册，当你想用GitHub网站共同开发项目或者分享你自己的项目的时候，就需要像一个博客一样注册一个自己的账号啦。  
        但是由于GitHub这个网站的服务器是在国外，所以在访问GitHub这个网站的时候可能就需要老爹的魔法啦。  
        当然，也有其他的方法，这里同样这里也不多叙述，提供一个比较简单的方法。  
        ~(￣▽￣)~*
[csdn博客链接：GitHub链接不上的简单方法][GitHub连不上怎么办]  


## Git的基本操作（版本管理）
那么那么，接下来就开始介绍git的基础操作，也就是版本管理部分啦。  
各位看官，你细听分说~   
 
- Git的基本操作（版本管理）の小目录  
[Git的办公区域](#git的办公区域)  
[Git指令的操作位置](#git指令的操作位置)  
[windows和Linux/macOS操作目录](#windows和linuxmacos操作目录)  
[git init (初始化git仓库)](#git-init-初始化git仓库)  
[git add（把工作区域内容提交到暂存区）](#git-add-把工作区域内容提交到暂存区)    
[git status (查看文件状态)](#git-status-查看文件状态)   
[git commit（把暂存区内容提交到存储区）](#git-commit-把暂存区内容提交到存储区)  
[git log（查找历史版本记录）](#git-log-查找历史版本记录)    
[git checkout (切换版本)](#git-checkout-切换版本)


### Git的办公区域
在讲Git的基操之前，首先应该说明的，git的大致区域划分以方便大家理解下面的指令。  

首先，Git分为三个区间：  
  工作区/工作目录（Working Direcfory）；  
  暂存区(Staging)；  
  存储区(Reposifory)
1. 工作区/工作目录（Working Direcfory）
   - 你的本地文件，你打开文件夹看到的，可以直接操作的就可以理解为工作目录。  
   可以理解为各位小朋友每天晚上写作业的桌子。桌子上你写的所有作业，不管是英语，数学，物理巴拉巴拉什么的（所有文件类型），都是在桌子这个平台上面操作的。而桌子这个平台就理解为工作区。 
 
2. 暂存区(Staging)   
   - 你可以理解为各位小朋友的“小组长”。各位小朋友做完作业以后是不是要把作业交给“小组长”那面再交给老师呀。这个“小组长”是暂时存放你的项目的，而我们的目的是把项目交给老师。而如果我们"突然"想起来有作业没写完，哎，就可以在交给老师批阅之前及时在课上面把作业补完后重新提交给“小组长”。  
   - 需要注意的是，“小组长”在收作业之前会简单的检查你的作业，如果只交空本子（文件夹）小组长是不会识别到的啦。但是如果再里面写一篇作文（文件），即使只写作文的题目也算（一个内容为空的文件），小组长才会收你的作业。谁说只有题目的作文不是作文呢？没有题目的作文是无题，我只是无容罢了。  
ʅ（´◔౪◔）ʃ
   - Git会会根据文件的内容来识别文件，生成文件对应的SHA-1码，所以即使俩个文件名不一样也会生成相同的Bolb型的SHA-1码。而文件的地址和名字则记录于Tree型的[SHA-1码](#sha-1码)里。文章最后会有详细的讲解。  
(～o￣3￣)～

2. 存储区(Reposifory)  
    - 储存区就是老师的批阅啦。老师会给每个作业打上“已阅”，并注明日期什么的。此时就说明你的作业内容，提交人，提交时间什么的老师以及记录在案了。除非你退学（删除'.git'文件夹），否则你的表现记录都会一直记在老师的小本本里面。



Git的存档操作就是在这三个区间完成的，在大概理解了这三个区间后就可以开始具体指令的学习啦。
### Git指令的操作位置
- 我们的所有指令要有输入的地方。而这个地方就是git bash。需要我们在我们要管理的根目录里面左键一下空白的地方再右键点击open git bash here就可以打开啦。    
- 根目录是你的项目需要git管理的所有的东西，再往外一层git将不会理会    
- -git是Linux开发者作的，或多或少有一些Linux的影子我这里附带整理了一些基基本的windows和Linux/macOS操作区别。简单说也就是cmd和git bash的指令区别
### windows和Linux/macOS操作目录
|Windows| Linux/macOS|说明 | 
|:-----------:| :-------------:|:-------------:|
|cd|cd|切换目录|  
|cd|pwd|获取当前所在位置|  
|dir|ls|列出当前所在的文件列表|  
|mkdir|mkdir|创建新的目录（文件夹）|  
|无|touch|创建文件|  
|copy|cp|复制文件|  
|move|mv|移动文件|  
|del|rm|删除文件|  
|**`cls`**|**`clear`**|**`清除上面内容`**|  

其中大部分都拿鼠标来的快，但是clear指令可以帮助你在你的git bash很乱的时候清空一下命令行就不用重启git bash了，可以节省很多时间是一个应当掌握的指令。  
但是如果你要是想在人前显圣的话就可以偷偷练一下之后在假装不经意间用出来。  
    同学：Σ(っ °Д °;)っ？？？？？？？？
### git init （初始化git仓库）
想让Git做你项目的版本管理器，就必须先让Git接管你的项目，也就是先完成入班仪式。这时候你就该在你打开的git bash指令框里面输入:

```C#
git init
```
        这时，你的根目录里面的内容就会全部被Git所管理，其实悄悄的出现了一个.git文件夹（默认.开头的文件是隐藏状态，如果要找倒他只需要在文件夹最上面点查看，把"隐藏的项目"勾上即可）。Git的操作全在里面实现。  
如果你不希望Git管控这个项目，只需要把.git文件夹删除即可，但之前的版本记录会全部丢失，不可找回。  
如果你有某些文件不想让Git管理，或者一些机密文件（如数据库的存取密码，服务器密匙）不适合上传。也有办法： 
1. 新建一个文本文件，把文件名改为：.gitignore(注意前面有个点)
2. 在里面输入文件的全名，如：
   - one.html（一个文件）
   - *.tmp(所有后缀为.tmp的文件)
   - fruits/apple/*.exe(fruits/apple文件下的所有后缀为.exe的文件)
### git add （把工作区域内容提交到暂存区）
ok，现在你的项目已经有git来开始守护了。要想保存存档，你需要做俩步，git add与git commit。现在我们将工作区的文件放到暂存区里。 在git bash里接着输入：
```c#
git add --a
```
- `git add --a` 等价于 `git add --all` 等价于 `git add *`
- 如果你在git add之后，又改动了文件，那么应该再次向暂存区提交一次。
 
- 当然也可以只交部分内容，把--a换成文件全称即可。但是兄弟你记住，你可以没事找事，但别一直找事，直接都commit就完了。  
～(￣▽￣～)(～￣▽￣)～
- `git add .`与`git add --a`他们并不等价，区别如下  

Git 2.X 版本之前：
|使用参数| 删除的文件|提交内容 | 
|:-----------:| :-------------:|:-------------:|
|--all|可更改|根目录下所有内容|
|.|不可更改|当前路径下的所有内容|

Git 2.X 版本之后：
|使用参数| 删除的文件|提交内容 | 
|:-----------:| :-------------:|:-------------:|
|--all|可更改|根目录下所有内容|
|.|可更改|当前路径下的所有内容|

### git status （查看文件状态）
你可以输入git status来查看你文件的状态，以便你来理解，简单介绍一下。  
在git bash里接着输入：
```c#
git status
```
- 里面有四种文件状态情况：  
  1.`Changes to be committed`:表示已经从工作区add到暂存区的文件   
  2.`Changes not staged for commit`:表示工作区，暂时区都存在的文件  
  3.`Untracked files`:表示只在工作区有的文件  
  4. `both modified`:合并时有冲突的文件  
### git commit （把暂存区内容提交到存储区）
在我们向暂存区提交完之后，就该向存储区交作业了。  
在git bash里接着输入：
```c#
git add -m "啦啦啦"
```
- 如果觉的先add再commit有脱了裤子放屁的嫌疑。那么在前面加一个-a即可偷懒。o(*￣▽￣*)o    
在git bash里输入：  
`git add -a -m "啦啦啦"`

- 在啦啦啦里面是写本次提交的注释的地方，你应当明确告诉自己或者其他人这次改动了嘛。尽量客观，别“我改了给bug”，谁也不知道你动那了。也别写个800字小作文。简洁明了的说就行,比如"#01 bug fixed"。中文英文都行，但英语显的咱逼格高。  
(～￣▽￣)～
- 有些人说那为什么Git这样麻烦呀，直接commit不就完了吗。其实，commit是往存档里面存的，是会被记录的。打游戏不可能走一步记录一下，同样敲代码也一样。如果你commit太多code review的时候就不好查了，如果commit的比较有规律的话，就比较舒服了。
- 什么时候commit：
    1. 下班时间到：今天爷不敲了，commit一下。说：“X年X月X日~项目没啥进展，段位还掉了一段”  
    2. 阶段性任务完成：今天完成一个任务，虽然没到下班的点，但还是值得commit一下。说：“#1 bug fixed”告诉他们这个项目没了你跑不了。  
    3. 如"蜜"：  
        -  问：今天你commit了吗？  
        - 答：如"蜜"。   
        咱想啥时候"蜜"就啥时候"蜜"。
### git log （查找历史版本记录）
既然是存档，那就应该有回档功能吧。但回档得先查查咱要回哪个档吧。  
在git bash里接着输入：
```c#
git log
```
- 还记不记得咱们上面提到的[SHA-1码](#sha-1码)。git log查到的commit后面就紧紧的跟着。你可以把它当成commit的身份证号码。
- git log后面可以加参数辅助查询。  
   1. `git log --oneline`   
  在log后面加上--oneline会让输出结果更加简洁，看到更多的commit。  
  2. `git log --oneline --graph`  
  --graph会显示干了什么，一般与--oneline连用因为不用--oneline的时候这个消息已经出现了  
  3. `git log --oneline --auther="绣花锤头\|擎天尊"`  
  --auther="绣花锤头"   这个语句会查到'绣花锤头'或者'擎天尊'作者的commit看看是谁干的好事。  
  "反斜杠(mua的，反斜杠敲不出来)"符号表示或者的意思，必须要加上"反斜杠(mua的，反斜杠敲不出来)"否则|会被判定成文字而不是或者。
  4. `git log --oneline --grep="偷懒"`   
  --grep：提交信息的关键字  
  5. `git log --oneline -S "偷懒"`   
  -S：文件名的关键字  
  6. `git log --since="10am" --until="10pm" --after="2023-08"`   
  2023年8月之后上午十点到晚上十点交的commit，具体自己会意  
  7. `git log 文件名 -p`   
  -p：看每次commit干了什么
  看单一文件，具体自己会意  

### git checkout （切换版本）
在查完历史版本之后，接下来要做的就是读取存档了。  
在git bash里接着输入：
```c#
git checkout HEAD^
```
- 这个指令会恢复你当前'HEAD'所处前一个commit。简单理解就是“恢复上个版本”。  
- 在Git 1.8.5之后的版本，可以用'@'替代'HEAD'  
- 而'^'表示前一次，故'git checkout HEAD^^'就是前俩次，当想恢复的版本次数是3，5甚至100，10000次的时候难道敲10000个'^'吗？(๑¯∀¯๑)？  
no no no！  
在多个版本的"读档"，我们一般直接在'git checkout '后面跟想恢复版本的"[SHA-1码](#sha-1码)"。(他的"ID"用'git log'查哦。)如：  
`git checkout e16c8af`：表示回到'e16c8af'这个版本。但是会出现'detachde HEAD'，你问我具体为啥？[往后看！](#headmaster的区别)  
或者，用'~'后加数字表示"前几个"。如：  
`git checkout HEAD~2`：回到前俩个版本  
- 值得注意的是，'HEAD'和'master'是有区别的。关于'HEAD'和'master'是什么，有什么区别，我们在分支时会[详细介绍](#headmaster的区别)
- 当然，'git checkout '也可以[切换分支](#git-checkout-切换分支)，这个我们也在后面的分支时介绍  

## 分支/branch（合作开发）

- 分支/branch（合作开发）の小目录  
[什么是分支](#什么是分支)  
[git branch（查看分支情况）](#git-branch-查看分支情况)  
[git branch xxx （创建分支）](#git-branch-xxx-创建分支)  
[git branch -m xxx xxx （更改分支名字）](#git-branch--m-xxx-xxx-更改分支名字)  
[git branch -d xxx （删除分支）](#git-branch--d-xxx-删除分支)  
[git checkout （切换分支）](#git-checkout-切换分支)  
[git merge xxx （合并分支）](#git-merge-xxx-合并分支)  
[git reset HEAD^ --hard (取消合并分支)](#git-reset-head---hard-取消合并分支)  
[git rebase xxx (剪贴分支)](#git-rebase-xxx-剪贴分支)  
[HEAD/master的区别](#headmaster的区别)

### 什么是分支
在单人开发项目的时候，当然一条分支就行，也是没什么问题的。但是要是越来越多的人投入开发的话，就不能那么随意的commit了。这时候分支就派上用场了。  

总而言之，分支像一棵树的枝条，有他的主干(爹)。分支的目的是让一个项目的发展方向不受约束，可以多人共同开发，最后的使命都要合并在一起。  

具体来讲，分支就像一个指针，指向一个commit。默认的指针是'master'。当做了一次新的commit的时候，这个新的commit会指向前一个旧的commit，而指针在不干涉情况下会永远指向最新的commit。  
- 当创建了新的分支的时候，俩个分支依旧都指向原来的commit。当你在某个分支下再commit一下的时候，该分支会随着commit而前进，另一个分支则留在原地，还指向原来的commit。  

形象化来说，每次的向一个有名字的路标，这个默认叫'master'的路标指向项目的主线任务(commit)，避免玩家迷路找不到位置。  
当有支线任务时，你可以用其他路标（分支）指向支线任务。而支线任务的目的是对项目或者主线任务有一定的推进。所以支线任务最后还是要与主线任务合并的。    

### git branch （查看分支情况）
使用分支前首先我们先看看我们现在的默认分支。  
在git bash里接着输入：  
```c#
git branch
```
现在我们就看到了我们拥有的分支，目前来说，我们只拥有默认分支，也就是'master'分支。这个分支只是初始分支，叫'master'罢了，没有什么特殊的含义，如果你想，甚至可以改掉名字。这个我们后面会提到。  

- '*'表示现在所处的分支。对，没错！就是高亮的那一个。
### git branch xxx （创建分支）
如果想新增加一个分支，可以在查看分支指令的'branch'后面加上分支的名字。这样我们就新增加了一个分支。如果我们想增加一个dog分支：  
在git bash里接着输入：  
```c#
git branch dog
```
这样我们再次输入'git branch'就可以来查看现在的分支情况了。  
- 这里是从默认分支'master'来新建分支。
- 我们也可以从没有分支的地方新建分支。
  1. 先到某个commit：  
      `git checkout 23d56a3`  
  2. 再用'-b'创建分支：  
    `git branch -b dog`  
  或者直接：  
  `git branch dog 23d56a3`
### git branch -m xxx xxx （更改分支名字）
某游戏商店的改名卡着实惹人不爽。当然，如果想在Git里面改分支的名字是不需要改名卡的。  
o(*￣︶￣*)o  
在git bash里接着输入：  
```c#
git branch -m master cat
```  
即可将'master'分支的名字改为'cat'，同理，其他的分支也可以改。
### git branch -d xxx （删除分支）
当你们看某人不爽的时候，删微信之前可能会犹豫一下。  
当你们看某个分支更不爽时，别犹豫，直接删。  
o(￣ε￣*)o  
在git bash里接着输入：  
```c#
git branch -d dog
```  
这样就把狗东西('dog'分支)删掉了。
- 如果没有被完全合并，Git则会提醒
- 如果想来硬的，把'-d'换成'-D'。哼哼，强删！小子。
- 没有什么分支是不能删除的，~~如果有，把'-d'换成'-D'。~~  
咳咳，总而言之，没有什么分支是不能删除的，如果有，那只能说是是你"脚下"的分支。  
### git checkout （切换分支）
在查完历史版本之后，接下来要做的就是读取存档了。  
在git bash里接着输入：
```c#
git checkout HEAD^
```
Σ( ° △ °|||) ︴  哎等等。不对，这集我看过！  
emmm，神父，换碟！  
各位少侠好眼力。  
`git checkout HEAD^`  
确实是切换到上一个版本。这里的切换分支与上面提到的[git checkout （切换版本）](#git-checkout-切换分支)师出同门，都是用的  
`git checkout `  
只不过要在后面跟上分支的名字。如：切换到dog分支：  
在git bash里接着输入：
```c#
git checkout dog
```
再用'git branch'查看，就能看到分支状态的不同了。
### git merge xxx （合并分支）
欧克，合并分支无非就是俩种情况。  
1. 文件没冲突:你比我多a，我比你多b，咱俩共有的c一样
2. 文件有冲突:你比我多a，我比你多b，咱俩共有的c不一样  

那么开始合并，首先你得先确定你所处的位置。如：现在在'master'分支，另一个分支为'dog'。
在git bash里接着输入：
```c#
git merge dog
```  
先说'没冲突'的情况，这时候，就会顺利合并，'master'分支会直接指向'dog'
- 需要注意的是，这其实是使用了“快传模式”。因为'master'是'dog'分支的“爹”，也就是'dog'是从'master'分出去的。
- 如果现在有一个新的'cat'分支，而我们要将'cat'合并到'dog'分支。那么Git会帮你做一次新的commit，与其他只指向前面的commit不同，这个commit分别指向前俩个commit。'dog'指向这个新的commit，而'cat'还指向原来的commit。  
- 如果不想使用快传模式，那么，在后面加上`--no-ff`即可。如：  
`git merge dog --no-ff`  
- 合并后的分支可以保留，也可以删除。但我个人建议当完成一个完整的工作以后再合并，而合并就删掉这个分支，之后需要的时候再重创一个，这样不容易搞混。  
- 其实“合并分支”并不是合并的分支，而是合并的“commit”  

再说有冲突的情况：
- Git会检测简单的冲突。
- 并不是改到同一个文件就一定会发生冲突，但改到同一行就一定会出现冲突。
- 如果发生冲突，Git会告诉你哪个文件出问题了。如果是文本文件的话，直接改完文本文件具体内容后，先add再commit就行。如果不是文本文件，如图片什么的，使用'--ours'或者'--theirs'来选择用谁的。如，有俩个master的“子分支”，我们要将'cat'合并到'dog'分支。其中apple.jpg有冲突.  
  1. `git checkout --ours apple.jpg`：使用'dog'的'apple.jpg'  
  2. `git checkout --theirs apple.jpg`：使用'cat'的'apple.jpg'
### git reset HEAD^ --hard (取消合并分支)
没啥好说的，就是悔婚。其实本质是删除最后一次commit。  
在git bash里接着输入：
```c#
git reset HEAD^ --hard 
```
### git rebase xxx (剪贴分支)
其实这是另一种分支合并的形式，因为合并形式很像剪贴，所以我个人戏称之为分支剪贴。  
顾名思义，这种合并形式就像把左胳膊砍了接在右手上。但是左手并不是直接被删了，更像是剪贴，只是没指针指向他，逐渐被遗忘，直到某一天被删除。   
还是我们的老朋友，有俩个master的“子分支”，我们要将'cat'合并到'dog'分支。  
在git bash里接着输入：
```c#
git rebase dog
```
- 该操作具有一定的风险，因为相当于改动历史，会对其他人造成困扰。故应当在git push前使用，用作整理比较杂乱的commit。
- 由于该操作具有一定的风险，所以Git会把这种风险操作记录下来。（ORIG_HEAD）
- 取消合并：  
由于`git reset HEAD^ --hard`的本质是删除最后一次commit，故这里不适用。这里使用：  
`git reset ORIG_HEAD --hard`  
- 合并冲突：有点区别，但区别不大。问就是：  
  1. 文本文档：外甥打灯笼--照旧。
  2. 其他：外甥靠着舅舅打灯笼--依旧照旧。  
  (～o￣▽￣)～o ~。。。


### HEAD/master的区别
ok，到这里，大家应该都对分支有了一个简单的认识。我这里再向大家区分一下'HEAD'和'master'的区别。
- 'master'是默认分支的名字。是可以改名的，改成阿猫阿狗都可以。指向一个commit。  
- 'HEAD'是一个指向某个分支的指标，是具体操作的位置，他会跟着分支移动。可以理解为玩家自己或者玩家现在所处的位置。  
- 当创建了新的分支时，你的commit'HEAD'  
- 'HEAD'也可以直接指向某次commit以进行操作，只要你能记住那次commit的[SHA-1码](#sha-1码)。如：  
`git checkout 25a36e1`  
Σ( ° △ °|||) ︴  哎等等。不对，这集我又看过！   
是不是很熟悉？对！[之前挖的坑](#git-checkout-切换版本)现在就填上了。  
之所以提醒'detachde HEAD'就是因为'HEAD'现在指向25a36e1这次的commit，而此时并没有分支指向这里。'HEAD'跳过了指针直接指向了commit。所以才会提示。

## 项目的开发流程规则（Git Flow/GitHub Flow）！！！！
其实开发流程规则是合作开发项目时非常重要的，有很多人忽略了这一点，导致在合作完成项目的时候非常乱。  

我在一开始使用Git的时候就因为没合理的规则，就导致项目非常乱，甚至放弃了使用Git。遵守规则能很好的减少这些问题带来的影响。  

时至今日，我依然感觉这个开发流程规则太需要重视了，为了避免小伙伴重蹈我的覆辙，所以我开了单章介绍一下。  
- Git Folw

  1. Master 分支：主干分支，也就是完整上线版本1.0，2.0之类的。切记不要commit到这个分支上

  2. Feature 分支：功能分支，用于开发功能，其对应的是开发环境。

  3. Develop 分支：开发分支。所有开发分支的爹，所有的功能开发（Feature 分支）都需要从这里划出去。而一旦（Feature 分支）功能开发完成，就必须要向 Develop 分支合并，合并完成后，删除功能分支。

  4. Release 分支：上线前测试。当Develop 分支测试足够成熟时，开出一个 Release 分支来，然后做发布前的准备工作。这个分支对应的是预发环境。
     - 如果 Release 分支上的代码测试合格，那么需要把 Release 分支向 Master 分支和Develop 分支同时合并，以保证代码的一致性。然后再把 Release 分支删除掉。  
  5. Hotfix 分支：是用于处理生产线上代码的紧急发生的bug，每个线上代码的紧急 bug 都需要开一个 Hotfix 分支，完成后，向 Develop 分支和 Master 分支上合并。合并完成后，删除 Hotfix 分支。
- GitHub Flow  
GitHub Flow在GitHub官网里面有详细说明。  
详见[GitHub官方GitHub Flow说明][GitHub官方GitHub Flow说明]    
或者[CSDN博客GitHub Flow说明][CSDN博客GitHub Flow说明]


## GitHub
我们前面简单的介绍了GitHub，大家应该都有了一个简单的印象。上面的指令就可以让你在你的本地中简单的使用Git来完成你的版本管理工作了。而下面的则是让你的本地仓库和远程仓库相互交流的指令。  

- 分支/branch（合作开发）の小目录  
[远程仓库](#远程仓库)  
[git push （将本地仓库更新到远程仓库）](#git-push-将本地仓库更新到远程仓库)  
[git pull  （将远程仓库更新到本地仓库）](#git-pull-将远程仓库更新到本地仓库)  
[git clone （程序员式借鉴：高级复制远程仓库）](#git-pull-将远程仓库更新到本地仓库)  
[如何用GitHub共同开发 ](#如何用github共同开发)



### 远程仓库
想要将本地库和远程库交互，则应该先有一个远程仓库。  
1. 新建一个public仓库供我们操作。  
2. 接下来就看到了指引教程。简单来说，  
   - 空文件夹按照  
`creat a new repository on the command line`提示操作； 
   - 有东西按照  
`push an existing repository from the command line` 提示操作； 
### git push （将本地仓库更新到远程仓库）
接下来就是git push了，在操作提示中我们也能看到git push的痕迹。对，其实在完成操作提示的时候我们已经push了一次了。那么我们仔细说说。  
在git bash里接着输入：
```c#
git push
```  
- 前面提到的操作指令中的`git push -u origin master`，其中，-u（-upstream）是把origin设置成为了master的远端节点，他会指向并跟踪master。通常远端节点是远端的分支，但是设置本地也可以。  
如果没说清楚远端节点则每次push就该说明将哪个交给哪个分支：  
`git push origin master`  
否则，只执行git push的话，git就会因为你没说清而不执行
- `git push origin master:dog`  
如果在远端不想要master这个名字，而想要dog分支，它会起到作用的。  
- 有时候push的时候，push不上去，这是因为远程仓库和你本地仓库不一样啦。在以后的git push前先应当git pull一下。这样不会导致你的东西丢失的，大可放心。  
`git push -f`：强推（覆盖他人的push）
### git pull  （将远程仓库更新到本地仓库）
首先应该说明的是：
`git pull = git fetch + git merge`  
其次大家不用记，git fetch和git merge，可以装作没看见。单纯的显摆一下子罢了。ヾ(≧▽≦*)o  
那么，与git push相对的就是git pull了。
在git bash里接着输入：
```c#
git pull
```  
- 没啥好说的
### git clone （程序员式借鉴：高级复制远程仓库）
如果在GitHub上看到了不错的项目，还想把它历史记录和之前的版本也借鉴过来。好，请使用git clone
```c#
git clone xxxx
```  
- xxxx指的是GitHub项目的HTTPS/SSH  
- git clone与git pull区别：  
  第一次用git clone，之后用git pull

### 如何用GitHub共同开发  
1. 先由项目牵头人创建GitHub远程仓库
2. 开发者再把牵头人Fork到自己GitHub里，并把牵头人的项目设置成上游项目  
3. 开发者push到自己账号
4. 给牵头人发pull Request请求
5. 原作者觉得不错就合会到他终极的的GitHub远程仓库里
跟上游项目同步：

***
- 把牵头人的项目设置成上游项目：
     1. `git remote -v`:获取项目信息
     2. `git remote add upstream HTTPXXXXXXX`或  
     `git remote add dummy-kao HTTPXXXXXXX`：  
     设置上游项目
- 获取原项目内容：  
    `git fetch upstream `或   `git fetch dummy-kao ` 
## SHA-1码
        SHA-1码也就是Sercure Hash Algorithm 1  。他是一种凑值算法，可以理解为通过固定算法压缩为固定长度（40个16进制）的码。这种码在给定内容一样的情况下，会输出同样的数，而在内容不一样的情况下重复的概率很小。我们所知的commit的乱码就是SHA-1码的前七位，这是git用前7位代替他整个SHA-1码。  
咱们之前提到，有四种重要的比较基础的，Blob对象，Tree对象，Commit对象，以及Tag对象。    
- Blob：文件的具体内容。内容一样，SHA-1码就一样。文件的内容都是Blod对象，文件名不归他管。  
- Tree：文件的位置和文件名，类型。也许有另一个Tree对象。可以理解为文件夹，但是文件夹的等级都是同级的。  
  1. Tree对象(可能有)  
  2. Blob对象(可能有)    
- commit：每次commit会生成一个[SHA-1码](#sha-1码)，而这个commit对象包含五个信息：  
  1. Tree对象：
  2. 时间
  3. 作者
  4. commit时候你写的信息
  5. 上一次commit的信息（如果有的话）
- Tag：理解为标签。包含：
  1. 时间
  2. 作者
  3. 标签上你写的信息
  4. commit的信息
## 后言/叠甲
本文是作者学习一段时间Git后的总结或者分享，再闲暇之余帮助一些同学入门一下。  
有些地方理解不正确或者不到位欢迎指正。  
请勿复制或者抄袭或者发表本文的部分或者全部内容。

  











[csdn博客：git下载]: https://blog.csdn.net/mukes/article/details/115693833?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522169173765616800213057451%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fall.%2522%257D&request_id=169173765616800213057451&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_ecpm_v1~hot_rank-1-115693833-null-null.142^v92^koosearch_v1&utm_term=git%E4%B8%8B%E8%BD%BD&spm=1018.2226.3001.4187
[GitHub连不上怎么办]: https://blog.csdn.net/qq_41176055/article/details/128496628?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522169173893516800213039459%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fall.%2522%257D&request_id=169173893516800213039459&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_ecpm_v1~hot_rank-1-128496628-null-null.142^v92^koosearch_v1&utm_term=GitHub%E6%89%93%E4%B8%8D%E5%BC%80&spm=1018.2226.3001.4187
[GitHub官网]: https://GitHub.com/
[GitHub官方GitHub Flow说明]: https://docs.GitHub.com/en/get-started/quickstart/GitHub-flow
[CSDN博客GitHub Flow说明]:https://blog.csdn.net/i6101206007/article/details/108048267?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522169227510716800185868955%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=169227510716800185868955&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-2-108048267-null-null.142^v93^koosearch_v1&utm_term=GitHub%20Flow&spm=1018.2226.3001.4187
