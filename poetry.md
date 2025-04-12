[返回首页](README.md)     
**本站访问次数/Visitor Count:**

<a href="https://count.getloli.com/"><img src="https://count.getloli.com/get/@:2356360027"></a>

**请勿复制或者抄袭或者发表本文的部分或者全部内容**
# Poetry基本格式

## 目录
- [什么是poetry](#什么是poetry)
- [poetry的使用](#poetry的使用)
- [poetry的安装](#poetry的安装)
- [初始化poetry项目](#初始化poetry项目)
- [管理虚拟环境](#管理虚拟环境)
- [创建虚拟环境](#创建虚拟环境)
- [poetry指令](#poetry指令)
- [修改poetry镜像源](#修改poetry镜像源)

## 什么是poetry
poetry是一种基于python的依赖管理工具，它可以帮助你管理你的python项目中的依赖，并且可以自动安装依赖，并且可以自动更新依赖，并且可以自动处理依赖的版本冲突。


## poetry的使用

### poetry的安装
poetry 是一个命令行工具，安装之后就可以使用 poetry 指令。
可以将其安装全局环境或者是虚拟环境，我推荐安装在全局环境，这样在后面使用时不需要单独激活虚拟环境。
同时 poetry 也依赖了比较多的模块，每个虚拟环境都安装一次也会比较麻烦。你可以使用pip命令来安装poetry，命令如下：
```
pip install poetry
```

### 初始化poetry项目
poetry的初始化也非常简单，只需要在你的项目的根目录下运行poetry init命令即可，命令如下：
```
poetry init
```
然后会跳出来一连串的互动对话，用于创建项目的配置文件，这里我就直接全部一路回车，然后看一下生成的 pyproject.toml 配置文件：
poetry的基本格式如下：
```
[tool.poetry]
name = "myproject"
version = "0.1.0"
description = "My project"
authors = ["Your Name <you@example.com>"]
license = "MIT"
readme = "README.md"
homepage = "https://github.com/yourname/myproject"
repository = "https://github.com/yourname/myproject"
documentation = "https://yourname.github.io/myproject"
keywords = ["python", "myproject"]
classifiers = [
    "Programming Language :: Python :: 3",
    "License :: OSI Approved :: MIT License",
    "Operating System :: OS Independent",
]
[tool.poetry.dependencies]
python = "^3.8"
requests = "^2.25.1"
[tool.poetry.dev-dependencies]
pytest = "^6.2.4"
```
- [tool.poetry]：这是一个poetry的配置文件，所有的配置都在这个文件中。
- name：这是你的项目的名字。
- version：这是你的项目的版本号。
- description：这是你的项目的描述。
- authors：这是你的项目的作者。
- license：这是你的项目的许可证。
- readme：这是你的项目的readme文件。
- homepage：这是你的项目的主页。
- repository：这是你的项目的代码仓库。
- documentation：这是你的项目的文档。
- keywords：这是你的项目的关键词。
- classifiers：这是你的项目的分类器。
- [tool.poetry.dependencies]：这是你的项目的依赖。
- python：这是你的项目的python版本。
- requests：这是你的项目的requests依赖。
- [tool.poetry.dev-dependencies]：这是你的项目的开发依赖。
- pytest：这是你的项目的pytest依赖。

## 管理虚拟环境
poetry预设了很多自己的虚拟环境，这些配置可以通过poetry config进行修改。
Windows 系统下 poetry 预设是将虚拟环境创建在 C:\Users\<用户名>\AppData\Local\pypoetry\Cache\virtualenvs 目录下。
当用户在执行 poetry add 等指令时，poetry 都会自动检查当下是否正在使用虚拟环境：
- 是：直接安装到当前的虚拟环境下
- 否：自动创建并安装模块

如果之前使用过 venv 、 virtualenv 或者其他的虚拟环境，
poetry 默认的虚拟环境跟他们的有一点不一样，
不过后面可以通过 poetry config 修改配置解决这个问题。

### 创建虚拟环境
poetry的创建虚拟环境也非常简单，只需要在你的项目的根目录下运行poetry config virtualenvs.in-project true命令即可，命令如下：
```
poetry config virtualenvs.in-project true
```

或者使用指令 poetry env use python，命令如下：
```
poetry env use python
```
这样就可以在项目的根目录下创建一个虚拟环境了。


### 添加依赖
poetry的添加依赖也非常简单，只需要在你的项目的根目录下运行poetry add命令即可，命令如下：
```
poetry add requests
Creating virtualenv poetry-demo-Ut74gzEx-py3.10 in C:\Users\xxp\AppData\Local\pypoetry\Cache\virtualenvs
Using virtualenv: C:\Users\xxp\AppData\Local\pypoetry\Cache\virtualenvs\poetry-demo-Ut74gzEx-py3.10
```
- poetry add：添加依赖
  - requests：添加的依赖
  - Creating virtualenv poetry-demo-Ut74gzEx-py3.10 in C:\Users\xxp\AppData\Local\pypoetry\Cache\virtualenvs：创建虚拟环境
  - Using virtualenv: C:\Users\xxp\AppData\Local\pypoetry\Cache\virtualenvs\poetry-demo-Ut74gzEx-py3.10：使用虚拟环境
  - poetry env use python 是使用当前命令行下激活的 python 解释器创建虚拟环境
  - poetry config virtualenvs.in-project true 是在项目根目录下创建虚拟环境
  - poetry config virtualenvs.in-project false 是在项目根目录下创建虚拟环境
  - poetry config virtualenvs.path C:\Users\xxp\AppData\Local\pypoetry\Cache\virtualenvs 是设置虚拟环境的路径
  - poetry config virtualenvs.create false 是不创建虚拟环境
- poetry 默认会将虚拟环境统一放在指定目录，例如刚刚创建的项目就放在 C:\Users\xxp\AppData\Local\pypoetry\Cache\virtualenvs\ 目录当中
- 虚拟环境的命名模式为 项目名-随机数-python版本

### 在当前项目下创建虚拟环境
我们可以使用 poetry config --list 指令来查看 poetry 的几个主要设定
```
X:\poetry-demo>poetry config --list
cache-dir = "C:\\Users\\xxp\\AppData\\Local\\pypoetry\\Cache"
experimental.new-installer = true
experimental.system-git-client = false
installer.max-workers = null
installer.modern-installation = true
installer.no-binary = null
installer.parallel = true
virtualenvs.create = true
virtualenvs.in-project = null
virtualenvs.options.always-copy = false
virtualenvs.options.no-pip = false
virtualenvs.options.no-setuptools = false
virtualenvs.options.system-site-packages = false
virtualenvs.path = "C:\\Users\\xxp\\AppData\\Local\\pypoetry\\Cache\\virtualenvs"
virtualenvs.prefer-active-python = false
virtualenvs.prompt = "{project_name}-py{python_version}"
```
- cache-dir：缓存目录
- experimental.new-installer：是否使用新的安装器
- experimental.system-git-client：是否使用系统的 git 客户端
- installer.max-workers：最大工作线程数
- installer.modern-installation：是否使用现代安装方式
- installer.no-binary：是否禁止二进制安装
- installer.parallel：是否并行安装
- virtualenvs.create：是否创建虚拟环境
- virtualenvs.in-project：是否在项目根目录下创建虚拟环境
- virtualenvs.options.always-copy：是否总是复制文件
- virtualenvs.options.no-pip：是否禁止安装 pip
- virtualenvs.options.no-setuptools：是否禁止安装 setuptools
- virtualenvs.options.system-site-packages：是否使用系统站点包
- virtualenvs.path：虚拟环境路径
- virtualenvs.prefer-active-python：是否优先使用活动的 python
- virtualenvs.prompt：虚拟环境提示符
  
其中 virtualenvs.create = true 若改为 false，
则可以停止 poetry 在检查不到虚拟环境是自动创建的行为模式，但是建议不要改动。
而 virtualenvs.in-project = false 就是我们要修改的目标，使用指令：
```
poetry config virtualenvs.in-project true
```
先把之前创建的虚拟环境删除
```
X:\poetry-demo>poetry env remove python
Deleted virtualenv: C:\Users\xxp\AppData\Local\pypoetry\Cache\virtualenvs\poetry-demo-Ut74gzEx-py3.10
```
重新创建虚拟环境，看一下差异：
```
X:\poetry-demo>poetry env use python
Creating virtualenv poetry-demo in X:\poetry-demo\.venv
Using virtualenv: X:\poetry-demo\.venv
```
可以看出：
- virtualenvs.in-project = true 时，虚拟环境会创建在项目根目录下，并且命名为 .venv
- 虚拟环境的路径改为项目的根目录下了
- virtualenvs.in-project = false 时，虚拟环境会创建在 poetry 配置的虚拟环境路径下，并且命名为 项目名-随机数-python版本

### 启动与退出虚拟环境
在项目的根目录下使用 poetry shell 就可以进入到虚拟环境
```
X:\poetry-demo>poetry shell
Spawning shell within X:\poetry-demo\.venv
 
(poetry-demo-py3.10) X:\poetry-demo>
```
poetry shell 指令会检查当前目录或上层目录是否存在 pyproject，
toml 来确定需要启动的虚拟环境，所以如果不移动到项目的目录下，则会出现错误。

退出虚拟环境就更简单了，只要输入 exit 就可以了。
```
(poetry-demo-py3.10) X:\poetry-demo>exit
 
X:\poetry-demo>
```
## poetry 指令
poetry 是一个独立的命令行工具，他有自己的指令，需要花费额外的时间与精力学习，
相较 pip 更加复杂，这个能是使用 poetry 的一道关卡。好在常用指令其实不超过 10 个，
下面就来一一介绍。



<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Poetry vs Pip</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: left;
        }
        th {
            background-color: #f2f2f2;
        }
    </style>
</head>
<body>
    <h1>Poetry vs Pip</h1>
    <table>
        <thead>
            <tr>
                <th>功能</th>
                <th>Poetry</th>
                <th>Pip</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>创建项目配置文件</td>
                <td>在项目的根目录下创建一个名为pyproject.toml的文件</td>
                <td>无</td>
            </tr>
            <tr>
                <td>添加依赖</td>
                <td>使用poetry add命令添加你的项目的依赖</td>
                <td>使用pip install命令安装你的项目的依赖</td>
            </tr>
            <tr>
                <td>移除依赖</td>
                <td>使用poetry remove命令移除你的项目的依赖</td>
                <td>使用pip uninstall命令移除你的项目的依赖</td>
            </tr>
            <tr>
                <td>更新依赖</td>
                <td>使用poetry update命令更新你的项目的依赖</td>
                <td>使用pip install --upgrade命令更新你的项目的依赖</td>
            </tr>
            <tr>
                <td>安装依赖</td>
                <td>使用poetry install命令安装你的项目的依赖</td>
                <td>使用pip install命令安装你的项目的依赖</td>
            </tr>
            <tr>
                <td>查看依赖</td>
                <td>无</td>
                <td>使用pip freeze命令查看你的项目的依赖</td>
            </tr>
            <tr>
                <td>运行项目</td>
                <td>使用poetry run命令运行你的项目的依赖</td>
                <td>使用pip install命令安装你的项目的依赖后，直接运行脚本</td>
            </tr>
            <tr>
                <td>进入虚拟环境</td>
                <td>使用poetry shell命令进入你的项目的虚拟环境</td>
                <td>使用pip install命令安装你的项目的依赖后，进入虚拟环境（需要手动激活）</td>
            </tr>
            <tr>
                <td>退出虚拟环境</td>
                <td>使用exit命令退出你的项目的虚拟环境</td>
                <td>使用deactivate命令退出虚拟环境</td>
            </tr>
        </tbody>
    </table>

### 安装模块
poetry add 指令用于安装模块，并且会自动更新 pyproject.toml 文件。
```c++
poetry add 
```
相较于 pip install，我们试试安装 flask 看看会有什么样的变化
```
(poetry-demo-py3.10) X:\poetry-demo>poetry add flask
Using version ^2.3.2 for flask
 
Updating dependencies
Resolving dependencies...
 
Writing lock file
 
Package operations: 8 installs, 0 updates, 0 removals
 
  • Installing colorama (0.4.6)
  • Installing markupsafe (2.1.3)
  • Installing blinker (1.6.2)
  • Installing click (8.1.6)
  • Installing itsdangerous (2.1.2)
  • Installing jinja2 (3.1.2)
  • Installing werkzeug (2.3.6)
```
可以看到 poetry 会将所有的信息全部列出来，并且清楚的告知了新增了那些第三方模块。

此时项目中的 pyproject.toml 也发生了变化
```
[tool.poetry.dependencies]
python = "^3.10"
flask = "^2.3.2"  # 新增部分
```
这里要说明，安装 flask ，
则 pyproject.toml 只会新增 flask = "^2.3.2" 这个字段的第三方模块，
其余依赖不会出现在 toml 文件中。

这里是一个非常大的优点，以便区分那些是用户安装的第三方模块，
那些是第三方模块一并安装的依赖。
### poetry.lock 与更新顺序
除了更新 pyproject.toml ，此时项目中还会新增一个文件，名为 poetry.lock ，它实际上就相当于 pip 的 requirements.txt ，详细记录了所有安装的模块与版本。

当使用 poetry add 指令时，poetry 会自动依序帮你做完这三件事：
-> 更新 pyproject.toml
-> 依照 pyproject.toml 的内容，更新 poetry.lock
-> 依照 poetry.lock 的内容，更新虚拟环境

由此可见， poetry.lock 的内容是取决于 pyproject.toml ，但两者并不会自己连动，一定要基于特定指令才会进行同步与更新， poetry add 就是一个典型案例。

此时项目目录结构如下：
```
poetry-demo
├── poetry.lock
└── pyproject.toml
 
0 directories, 2 files
```
### poetry lock ：更新 poetry.lock
poetry lock 指令用于更新 poetry.lock 文件，它会根据 pyproject.toml 中的内容，重新生成 poetry.lock 文件。

当你自行修改了 pyproject.toml 内容，比如变更特定模块的版本（这是有可能的，尤其在手动处理版本冲突的时候），
此时 poetry.lock 的内容与 pyproject.toml 出现了脱钩，必须让它依照新的 pyproject.toml 内容更新、同步，使用指令：
```
poetry lock
```
如此一来，才能确保手动修改的内容，也更新到 poetry.lock 中，毕竟虚拟环境如果要重新建立，是基于 poetry.lock 的内容来安装模块，而非 pyproject.toml 。

poetry.lock 相当于 Poetry 的 requirements.txt


但要特别注意的是， poetry lock 指令，仅会更新 poetry.lock ，不会同时安装模块至虚拟环境

因此，在执行完 poetry lock 指令后，必须再使用 poetry install 来安装模块。否则就会出现 poetry.lock 和虚拟环境不一致的状况。

更多 poetry lock 细节可参考 官方文件，其中特别值得注意的是 --no-update 参数。

### 新增模块至 dev-dependencies
有些模块，比如 pytest 、 black 等等，只会在开发环境中使用，产品的部署环境并不需要。

Poetry 允许你区分这两者，将上述的模块安装至 dev-dependencies 区块，方便让你轻松建立一份「不包含」 dev-dependencies 开发模块的安装清单。

在此以 Black 为例，安装方式如下：
```
poetry add black --group dev
```
结果的区别显示在 pyproject.toml 里：
```
[tool.poetry.dependencies]
python = "^3.10"
flask = "^2.3.2"
 
 
[tool.poetry.group.dev.dependencies]
black = "^23.7.0"
```
可以看到 black 被列在不同区块： tool.poetry.dev-dependencies 。
善用 --group dev 参数，明确区分开发环境，我认为非常必要。

### Poetry 更新模块
poetry update 指令用于更新模块，它会根据 pyproject.toml 中的内容，更新虚拟环境中的模块。
```
poetry update
```
上面指令会更新全部可能可以更新的模块，也可以仅指定特定模块，比如：
```
poetry update requests toml
```
还一件重要的事，那就是关于模块版本的升级限制规则，取决于你在 pyproject.toml 中的设定。
### 列出全部模块清单
类似 pip list ，这里要使用 poetry show

特别提醒的是，这里的清单内容并不是来自于虚拟环境，这点和 pip 不同，而是来自于 poetry.lock 的内容。

你可能会想，来自于 poetry.lock 或虚拟环境，有差吗？两者不是应该要一致？

没错，理论上是，但也有不一致的时候，比如你使用了 pip install 指令安装模块，就不会记载在 poetry.lock 中，那 poetry show 自然也不会显示。

树状显示模块依赖层级:
```
poetry show --tree
```
让主要模块与其依赖模块的关系与层次，一目了然。

而且很贴心的是，它也可以只显示指定模块的依赖层级，以 celery 为例：
```
poetry show --tree celery
```
### Poetry 移除模块
使用 poetry remove 指令。和 poetry add 一样，可以加上 -D 参数来移除置于开发区的模块。

而移除模块时的依赖解析能力，正是 Poetry 远优于 pip 的主要环节，因为 pip 没有嘛！也是我提议改用 Poetry 的关键理由——为了顺利移除模块与依赖。

前面已经提过，pip 的 pip uninstall 只会移除你所指定的模块，而不会连同依赖模块一起移除。

这是基于安全考量，因为 pip 没有依赖解析功能。如果贸然移除所有安装时一并安装的依赖模块，可能会造成巨大灾难，让别的模块失去效用。

所以，使用 pip 时，我们鲜少会去移除已经不再使用的模块。毕竟依赖关系错综复杂，移除模块可能造成许多副作用，实在是太麻烦了。

```
poetry remove flask
```

### 输出 Poetry 虚拟环境的 requirements.txt
理论上，全面改用 Poetry 后，项目中是不需要存在 requirements.txt ，因为它的角色已经完全被 poetry.lock 所取代。

但事实是，你可能还是需要它，甚至希望它随着 poetry.lock 的内容更新！至少对我而言就是如此，我在 Docker 部署环境中并不使用 Poetry，所以我需要一份完全等价于 poetry.lock 的 requirements.txt ，用于 Docker 部署。

你可能想说，那我就在 Poetry 的虚拟环境下，使用以往熟悉的指令 pip freeze > requirements.txt 来产生一份就可以了吧？我本来也是这么想，但实际的产出却是如此：（提醒：目前 poetry-demo 专案中仅剩下 Black 和它的依赖模块）
```
black @ file:///Users/kyo/Library/Caches/pypoetry/artifacts/11/4c/fc/cd6d885e9f5be135b161e365b11312cff5920d7574c8446833d7a9b1a3/black-22.3.0-cp38-cp38-macosx_10_9_x86_64.whl
click @ file:///Users/kyo/Library/Caches/pypoetry/artifacts/f0/23/09/b13d61d1fa8b3cd7c26f67505638d55002e7105849de4c4432c28e1c0d/click-8.1.2-py3-none-any.whl
mypy-extensions @ file:///Users/kyo/Library/Caches/pypoetry/artifacts/b6/a0/b0/a5dc9acd6fd12aba308634f21bb7cf0571448f20848797d7ecb327aa12/mypy_extensions-0.4.3-py2.py3-none-any.whl
...
```
这呈现好像不是我们以前熟悉的那样：
```
black==22.3.0
click==8.1.2
...
```
没错，只要是使用 poetry add 安装的模块，在 pip freeze 就会变成这样。此时想输出类似 requirements.txt 的格式，需要使用 poetry export 。
```
poetry export -f requirements.txt -o requirements.txt --without-hashes
```
我们再看一下输出结果，虽然不尽相同，但也相去不远了……吗？等等，怎么是空白？

因为 poetry export 预设只会输出 toml 中的 [tool.poetry.dependencies] 区块的模块！还记得上面我们把 Black 安装到 [tool.poetry.dev-dependencies] 了吗？

这倒是没错，不过基于演示需求，我们必须输出 [tool.poetry.dev-dependencies] 的模块，才能看到 Black。
```
poetry export -f requirements.txt -o requirements.txt --without-hashes --dev
```
现在，我们终于看到我们熟悉的格式了，而且也包含了 Black 模块，这正是我们想要的。
输出的 requirements.txt 内容：
```
black==22.3.0; python_full_version >= "3.6.2"
click==8.1.2; python_version >= "3.7" and python_full_version >= "3.6.2"
colorama==0.4.4; python_version >= "3.7" and python_full_version >= "3.6.2" and platform_system == "Windows"
...
```
虽然长得有点不一样，但这个档案确实是可以 pip install 的。

从这里也可以看出先前一再提及区分开发、部署依赖的价值——大部分时候我们并不需要输出开发用模块。

## 修改 poetry 镜像源
Poetry 的虚拟环境，默认使用的是 Python 官方的 PyPI 镜像源，如果你在国内，可能会因为网络问题，导致安装模块的速度奇慢无比。
修改为清华镜像源
```
poetry source add tsinghua https://pypi.tuna.tsinghua.edu.cn/simple
```







