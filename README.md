# 利用jenkins持续集成构建electron桌面应用

---

# [关于 Electron](https://electronjs.org/docs/tutorial/about#%E5%85%B3%E4%BA%8E-electron) {#关于-electron}

* [Electron](https://electronjs.org/)是由Github开发，用HTML，CSS和JavaScript来构建跨平台桌面应用程序的一个开源库。 Electron通过将[Chromium](https://www.chromium.org/Home)和[Node.js](https://nodejs.org/)合并到同一个运行时环境中，并将其打包为Mac，Windows和Linux系统下的应用来实现这一目的。

  Electron于2013年作为构建Github上可编程的文本编辑器[Atom](https://atom.io/)的框架而被开发出来。这两个项目在2014春季开源。

  目前它已成为开源开发者、初创企业和老牌公司常用的开发工具。官网[看看谁在使用Electron](https://electronjs.org/apps)。

  继续往下阅读可以了解Electron的贡献者们和已经发布的版本，或者直接阅读官网的[快速开始指引](https://electronjs.org/docs/tutorial/quick-start)来开始用Electron来构建应用。

* ## [核心理念](https://electronjs.org/docs/tutorial/about#%E6%A0%B8%E5%BF%83%E7%90%86%E5%BF%B5) {#核心理念}

  为了保持Electron的小 \(文件体积\) 和可持续性 \(依赖和API的扩展\) ，Electron限制了使用的核心项目的范围。

  比如Electron只用了Chromium的渲染库而不是全部。 这使得容易升级Chromium，但也意味着Electron缺少Google Chrome里的一些浏览器特性。

  Electron所添加的的新特性应主要用于原生API。 如果一个特性能够成为一个Node.js模块，那它就应该成为。 参见[社区构建的Electron工具](https://electronjs.org/community)。

* # [Electron 版本管理](https://electronjs.org/docs/tutorial/electron-versioning#electron-%E7%89%88%E6%9C%AC%E7%AE%A1%E7%90%86) {#electron-版本管理}

  > 详细查看我们的版本控制策略和实现。

  从版本 2.0.0, Electron遵循[semver](https://electronjs.org/docs/tutorial/electron-versioning#semver)。以下命令将安装Electron最新稳定的版本:

  ```
  npm install --save-dev electron
  ```

  现有项目更新到最新的稳定版本:

  ```
  npm install --save-dev electron@latest
  ```

# [关于 Electron](https://electronjs.org/docs/tutorial/about#%E5%85%B3%E4%BA%8E-electron) {#关于-electron}





