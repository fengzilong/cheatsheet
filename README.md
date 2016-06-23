# cheatsheet
cheatsheet for efficiency and some tricks

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [cheatsheet](#cheatsheet)
	- [Shortcuts](#shortcuts)
		- [Chrome](#chrome)
		- [Atom](#atom)
		- [Photoshop](#photoshop)
		- [Windows Explorer](#windows-explorer)
	- [Windows Tricks](#windows-tricks)
		- [在当前目录打开命令行窗口](#在当前目录打开命令行窗口)
		- [node_modules中模块路径太深，无法删除](#nodemodules中模块路径太深无法删除)
	- [NPM](#npm)
		- [auth](#auth)
		- [release new version](#release-new-version)
		- [install](#install)
	- [Atom Package](#atom-package)
		- [auth](#auth)
		- [release new version](#release-new-version)
	- [Snippets](#snippets)
		- [js](#js)
		- [css](#css)

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
ctrl + shift + T 恢复标签页
ctrl + shift + I 切换Elements面板
ctrl + shift + J 切换Console面板
ctrl + [ 切换至上一个面板(开发者工具打开)
ctrl + ] 切换至下一个面板(开发者工具打开)
ctrl + shift + M 切换手机模式(开发者工具打开)
ctrl + shift + C 选择页面元素(开发者工具打开)
```

### Atom

```
ctrl + shift + \ 在treeview中找到当前文件
ctrl + \ 切换treeview
ctrl + alt + I 打开Devtools
ctrl + D 选中下一个内容相同的选区
A 新建文件(选中treeview中的某个目录后)
shift + A 新建文件夹(选中treeview中的某个目录后)
ctrl + P 模糊查找
ctrl + shift + P atom中所有的命令
ctrl + , 打开setting
ctrl + G 跳转到指定行&列
```

### Photoshop

```
C 裁剪
V 选择
M 选区
Space 移动
ctrl + shift + alt + S 保存png等格式
ctrl + G 分组
ctrl + shift + I 反选选区
ctrl + shift + V 原位置粘贴
ctrl + T 形变
ctrl + 鼠标点击图层 选中当前图层像素对应的选区
alt + 鼠标点击蒙版 编辑蒙版
```

### Windows Explorer

```
ctrl + L 聚焦地址栏
ctrl + W 关闭当前窗口
ctrl + shift + N 新建文件夹
ctrl + shift + R 在当前目录打开cmd
win + E 打开一个新的资源管理器
```

## Windows Tricks

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

## Snippets

### js

- How to slice arguments without leaking them

> https://gist.github.com/WebReflection/4327762cb87a8c634a29

```js
// Andrea Giammarchi, WTFPL
function slice() {'use strict';
  for (var
    o = +this,                // offset
    i = o,                    // start index
    l = arguments.length,     // length
    n = l - o,                // new length
    a = Array(n < 0 ? 0 : n); // new Array
    i < l; i++
  ) a[i - o] = arguments[i];
  return a;
}

/**
 * @example
(function () {
  slice.apply(0, arguments); // [1,2,3]
  slice.apply(1, arguments); // [2,3]
  slice.apply(6, arguments); // []
}(1,2,3));
 */
```

- fast bind

> https://gist.github.com/WebReflection/40e68a4f603ef788121a

```js
(function (FunctionPrototype) {
  'use strict';
  var originalBind = FunctionPrototype.bind;
  if (!originalBind.patched) {
    Object.defineProperty(
      FunctionPrototype,
      'bind',
      {
        configurable: true,
        value: function bind(context) {
          var callback = this;
          return arguments.length === 1 ?
              function () { return callback.apply(context, arguments); } :
              originalBind.apply(callback, arguments);
        }
      }
    );
    FunctionPrototype.bind.patched = true;
  }
}(Function.prototype));
```

### css

```css
/* 宽度自适应内容 */
width: -webkit-fit-content
```
