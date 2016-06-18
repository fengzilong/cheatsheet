# cheatsheet
cheatsheet for efficiency and some tricks

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [cheatsheet](#cheatsheet)
	- [Shortcut](#shortcut)
		- [Browser](#browser)
		- [Windows Explorer](#windows-explorer)
	- [Windows](#windows)
		- [在当前目录打开命令行窗口](#在当前目录打开命令行窗口)
		- [node_modules中模块路径太深，无法删除](#nodemodules中模块路径太深无法删除)
	- [NPM](#npm)
		- [auth](#auth)
		- [release new version](#release-new-version)
		- [install](#install)
	- [Atom Package](#atom-package)
		- [auth](#auth)
		- [release new version](#release-new-version)
	- [CSS](#css)

<!-- /TOC -->

## Shortcuts

### Chrome

```
ctrl + L 聚焦地址栏
ctrl + T 打开一个新的标签页
ctrl + D 收藏当前页面至书签
ctrl + J 打开下载
ctrl + H 打开浏览历史
ctrl + P 打印当前页面，可保存pdf
ctrl + N 打开新的窗口
ctrl + shift + N 打开隐身模式窗口
ctrl + shift + Tab 切换至上一个标签页
ctrl + Tab 切换至下一个标签页
ctrl + W 关闭当前标签页
ctrl + shift + W 关闭所有标签页
ctrl + shift + I 切换Elements面板
ctrl + shift + J 切换Console面板
ctrl + [ 切换至上一个面板(开发者工具打开)
ctrl + ] 切换至下一个面板(开发者工具打开)
ctrl + shift + M 切换手机模式(开发者工具打开)
ctrl + shift + C 选择页面元素(开发者工具打开)
```

### Windows Explorer

```
ctrl + L 聚焦地址栏
ctrl + W 关闭当前窗口
ctrl + shift + N 新建文件夹
ctrl + shift + R 在当前目录打开cmd
win + E 打开一个新的资源管理器
```

## Windows

### 在当前目录打开命令行窗口

- ctrl + shift + R
- 在资源管理器的地址栏输入cmd并回车
- 按住shift，在文件夹空白处右键，右键菜单中会出现“在此处打开命令行窗口”

### node_modules中模块路径太深，无法删除

- 最笨的办法，进入目录里面，剪切至路径较浅的目录再删除
- robocopy empty_dir delete_dir /purge

## NPM

### auth

```bash
$ npm whoami
$ npm login # or npm adduser
```

### release new version

```bash
$ npm version patch/minor/major
$ npm publish
```

### install

```bash
$ npm i <moduleName> -S/-D -d
```

## Atom Package

### auth

```bash
$ apm login
```

### release new version

```bash
$ apm publish patch/minor/major
```

## CSS

- width: -webkit-fit-content; 宽度自适应内容
