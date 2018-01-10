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



















































