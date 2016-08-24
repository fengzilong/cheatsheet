# cheatsheet

> cheatsheet for efficiency and some tricks

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [cheatsheet](#cheatsheet)
	- [Shortcuts](#shortcuts)
		- [Chrome](#chrome)
		- [Atom](#atom)
		- [Photoshop](#photoshop)
		- [Windows Explorer](#windows-explorer)
	- [Windows Tricks](#windows-tricks)
		- [open cmd in current folder](#open-cmd-in-current-folder)
		- [files in node modules can not be deleted](#files-in-node-modules-can-not-be-deleted)
		- [create .xxx file](#create-xxx-file)
	- [NVM](#nvm)
		- [list all available node versions](#list-all-available-node-versions)
		- [use specific node version](#use-specific-node-version)
	- [NPM](#npm)
		- [auth](#auth)
		- [release new version](#release-new-version)
		- [check for outdated dependencies](#check-for-outdated-dependencies)
		- [install](#install)
		- [show detail during installation](#show-detail-during-installation)
	- [Atom Package](#atom-package)
		- [auth](#auth)
		- [release new version](#release-new-version)
		- [install your starred packages](#install-your-starred-packages)
		- [install other user's starred packages](#install-other-users-starred-packages)
	- [Package.json](#packagejson)
		- [dependencies version](#dependencies-version)
	- [Git](#git)
		- [push local folder to github](#push-local-folder-to-github)
		- [push and set upstream](#push-and-set-upstream)
	- [Electron](#electron)
		- [prevent redirect when drop files into electron window](#prevent-redirect-when-drop-files-into-electron-window)
		- [can't find module xxx after packaging](#cant-find-module-xxx-after-packaging)
	- [JavaScript Snippets](#javascript-snippets)
		- [how to slice arguments without leaking them](#how-to-slice-arguments-without-leaking-them)
		- [fast bind](#fast-bind)
		- [play sound from arraybuffer](#play-sound-from-arraybuffer)
		- [escape regexp](#escape-regexp)
	- [CSS Snippets](#css-snippets)
		- [auto fit content width](#auto-fit-content-width)

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
Shift + 点击Elements面板侧边栏中的某个色值，切换颜色格式
Ctrl + 点击Elements面板侧边栏的某个样式，寻找样式所在文件位置
Alt + <- 后退
Alt + -> 前进
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
ctrl + alt + Q 合并成一行
ctrl + shift + F2 清除所有书签
```

自行覆盖的快捷键，请无视

```
ctrl + F2 toogle书签
F2 下一个书签
shift + F2 上一个书签
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
ctrl + E 合并选中的图层(如果合并后的图层有问题，请先尝试栅格化待合并的图层)
ctrl + 鼠标点击图层 选中当前图层像素对应的选区
alt + 鼠标点击图层左侧的`眼睛` solo当前图层
alt + 鼠标点击蒙版 编辑蒙版
```

### Windows Explorer

```
ctrl + L 聚焦地址栏
ctrl + W 关闭当前窗口
ctrl + shift + N 新建文件夹
win + E 打开一个新的资源管理器
```

## Windows Tricks

### open cmd in current folder

- ctrl + shift + R(需要安装Listary)
- 在资源管理器的地址栏输入cmd并回车
- 按住shift，在文件夹空白处右键，右键菜单中会出现“在此处打开命令行窗口”

### files in node modules can not be deleted

- 最笨的办法，进入目录里面，剪切至路径较浅的目录再删除
- mkdir tmp && robocopy tmp node_modules /purge
- `npm i nmd-cli -g`，在node_modules所在文件夹执行nmd即可

### create .xxx file

- 假如你要输入的文件名是`.dev`，输入文件名`.dev.`，回车即可

## NVM

### list all available node versions

```bash
$ nvm list
```

### use specific node version

```bash
$ nvm use <version>
```

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

### check for outdated dependencies

```bash
$ npm outdated
```

### install

```bash
$ npm i <moduleName> [-S/-D]
```

### show detail during installation

```bash
$ npm i <packageName> -d
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

### install your starred packages

```bash
$ apm stars --install
```

### install other user's starred packages

```bash
$ apm stars --user thedaniel --install
```

## Package.json

### dependencies version

>指定版本：比如1.2.2，遵循“大版本.次要版本.小版本”的格式规定，安装时只安装指定版本。

>波浪号（tilde）+指定版本：比如~1.2.2，表示安装1.2.x的最新版本（不低于1.2.2），但是不安装1.3.x，也就是说安装时不改变大版本号和次要版本号。

>插入号（caret）+指定版本：比如ˆ1.2.2，表示安装1.x.x的最新版本（不低于1.2.2），但是不安装2.x.x，也就是说安装时不改变大版本号。需要注意的是，如果大版本号为0，则插入号的行为与波浪号相同，这是因为此时处于开发阶段，即使是次要版本号变动，也可能带来程序的不兼容。

>latest：安装最新版本。

> 摘自[package.json文件](http://javascript.ruanyifeng.com/nodejs/packagejson.html#toc2)

## Git

### push local folder to github

```bash
$ git init
$ git add -A
$ git commit -m "init"
$ git remote add origin git@github.com:<your_username>/<your_repo_name>.git
$ git push -u origin master
```

### push and set upstream

```bash
$ git push -u origin branchName
```

## Electron

### prevent redirect when drop files into electron window

```js
win.webContents.on('will-navigate', event => {
	event.preventDefault();
	return false;
});
```

```js
document.addEventListener('dragover', function( event ) {
	event.preventDefault();
	return false;
}, false);

document.addEventListener('drop', function( event ) {
	event.preventDefault();
	// let files = event.dataTransfer.files;
	return false;
}, false);
```

参考：https://github.com/electron/electron/issues/5919

### can't find module xxx after packaging

打包前正常，打包后报`can't find module xxx`的错误，之前一次遇到是因为安装titlebar的时候没有保存到package.json的依赖列表中，重新用npm i titlebar -S安装，再打包，没有出现报错

## JavaScript Snippets

### how to slice arguments without leaking them

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

### fast bind

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

### play sound from arraybuffer

```js
const context = new AudioContext();

function playSound( buffer ) {
	const source = context.createBufferSource();
	source.buffer = buffer;
	source.connect( context.destination );
	source.start( 0 );
}

fetch( `https://dict.youdao.com/dictvoice?type=2&audio=word` )
	.then(response => response.arrayBuffer())
	.then(buffer => {
		try {
			context.decodeAudioData(buffer, b => {
				playSound( b );
			});
		} catch( e ) {

		}
	});
```

### escape regexp

```js
function escapeRegExp(string){
	return string.replace(/([.*+?^=!:${}()|[\]\/\\])/g, "\\$&"); //$&表示被匹配的字符串
}
```

比如这样一个字符串

```
~!@#$%^&*()_+{}|:"<>?[];',./-=！￥…（）—：“《》？【】、；‘，。·～＠＃％＆×＋｛｝｜”＼’－＝
```

转义其中需要转义的部分

```js
escapeRegExp(`~!@#$%^&*()_+{}|:"<>?[];',./-=！￥…（）—：“《》？【】、；‘，。·～＠＃％＆×＋｛｝｜”＼’－＝`)
```

结果

```
~\!@#\$%\^&\*\(\)_\+\{\}\|\:"<>\?\[\];',\.\/-\=！￥…（）—：“《》？【】、；‘，。·～＠＃％＆×＋｛｝｜”＼’－＝
```

这样就能直接放到正则中使用了

```js
/^[~\!@#\$%\^&\*\(\)_\+\{\}\|\:"<>\?\[\];',\.\/-\=！￥…（）—：“《》？【】、；‘，。·～＠＃％＆×＋｛｝｜”＼’－＝]+$/.test( '#' );
```

参考：[MDN](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Regular_Expressions)


## CSS Snippets

### auto fit content width

```css
/* 宽度自适应内容 */
width: -webkit-fit-content
```
