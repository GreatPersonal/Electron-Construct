# 利用jenkins持续集成构建electron桌面应用

---

# [关于 Electron](https://electronjs.org/docs/tutorial/about#关于-electron) {#关于-electron}

* [Electron](https://electronjs.org/)是由Github开发，用HTML，CSS和JavaScript来构建跨平台桌面应用程序的一个开源库。 Electron通过将[Chromium](https://www.chromium.org/Home)和[Node.js](https://nodejs.org/)合并到同一个运行时环境中，并将其打包为Mac，Windows和Linux系统下的应用来实现这一目的。

  Electron于2013年作为构建Github上可编程的文本编辑器[Atom](https://atom.io/)的框架而被开发出来。这两个项目在2014春季开源。

  目前它已成为开源开发者、初创企业和老牌公司常用的开发工具。官网[看看谁在使用Electron](https://electronjs.org/apps)。

  继续往下阅读可以了解Electron的贡献者们和已经发布的版本，或者直接阅读官网的[快速开始指引](https://electronjs.org/docs/tutorial/quick-start)来开始用Electron来构建应用。

## [核心理念](https://electronjs.org/docs/tutorial/about#核心理念) {#核心理念}

* 为了保持Electron的小 \(文件体积\) 和可持续性 \(依赖和API的扩展\) ，Electron限制了使用的核心项目的范围。比如Electron只用了Chromium的渲染库而不是全部。 这使得容易升级Chromium，但也意味着Electron缺少Google Chrome里的一些浏览器特性。

* Electron所添加的的新特性应主要用于原生API。 如果一个特性能够成为一个Node.js模块，那它就应该成为。 参见[社区构建的Electron工具](https://electronjs.org/community)。

# [Electron 版本管理](https://electronjs.org/docs/tutorial/electron-versioning#electron-版本管理) {#electron-版本管理}

> 详细查看我们的版本控制策略和实现。

从版本 2.0.0, Electron遵循[semver](https://electronjs.org/docs/tutorial/electron-versioning#semver)。以下命令将安装Electron最新稳定的版本:

```
npm install --save-dev electron
```

现有项目更新到最新的稳定版本:

```
npm install --save-dev electron@latest
```

# 构建前准备 {#关于-electron}

> 构建electron应用依赖于nodeJs，所以我们在构建之前需要在本地安装nodeJs.下面介绍一下nodeJs的安装配置和使用Node.js

# Node 使用介绍

简单的说 Node.js 就是运行在服务端的 JavaScript。

Node.js 是一个基于Chrome JavaScript 运行时建立的一个平台。

Node.js是一个事件驱动I/O服务端JavaScript环境，基于Google的V8引擎，V8引擎执行Javascript的速度非常快，性能非常好。

> node的具体使用方法详见官网：[http://nodejs.cn/api/](http://nodejs.cn/api/)

Node.js安装包及源码下载地址为：[http://nodejs.cn/download/](http://nodejs.cn/download/)

```
检测PATH环境变量是否配置了Node.js，点击开始=》运行=》输入"cmd" => 输入命令"path"，输出结果找到这一行：
```

```
PATH=C:\Program Files\nodejs\;
```

我们可以看到环境变量中已经包含了：

```
C:\ProgramFiles\nodejs\
```

安装成功，我们可以在命令行使用node命令了，例如：

> node -v    //检查node安装版本号，看到版本号说明node安装成功

![](/assets/lALPBbCc1U9LQZwSzQEW_278_18.png)



node依赖于npm包，所以npm也需要在本地安装，下面介绍一下npm包管理器的使用和安装:

# NPM 使用介绍

NPM是随同NodeJS一起安装的包管理工具，能解决NodeJS代码部署上的很多问题，常见的使用场景有以下几种：

* 允许用户从NPM服务器下载别人编写的第三方包到本地使用。
* 允许用户从NPM服务器下载并安装别人编写的命令行程序到本地使用。
* 允许用户将自己编写的包或命令行程序上传到NPM服务器供别人使用。

由于新版的nodejs已经集成了npm，所以之前npm也一并安装好了。同样可以通过输入**"npm -v"**来测试是否成功安装。命令如下，出现版本提示表示安装成功:

```
$ npm -v

2.3.0
```

如果是 Window 系统使用以下命令全局安装即可：

```
npm install npm -g
```

> 使用淘宝镜像的命令：

```
cnpm install npm -g
```

> 在官网上我们可以查找我们项目中用到的依赖包，使用以下命令安装：

```
npm install 包名
```

> 在一个项目中会生成一个node\_modules的文件夹，所有的依赖包下载都会在这个目录里，还有就是在我们上传代码到源码管理仓库时，会把node\_modules 写入到ignore,只需要写入到项目的package.json配置中dependencies中，我们不需要手动写入，只要在安装依赖包时的命令中加入--save,在包安装 时就会自动写入依赖项。

```
npm install 包名 --save
```

还可以在npm上开源自己写的代码，支持各种语言，具体使用方法，详见官网：[https://www.npmjs.com/](https://www.npmjs.com/)

















