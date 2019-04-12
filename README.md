# cheatsheet

> cheatsheet for efficiency and some other tricks

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
	- [GitHub](#github)
		- [search something in certain path in repo](#search-something-in-certain-path-in-repo)
	- [Electron](#electron)
		- [prevent redirect when drop files into electron window](#prevent-redirect-when-drop-files-into-electron-window)
		- [can't find module xxx after packaging](#cant-find-module-xxx-after-packaging)
		- [launch at login](#launch-at-login)
	- [JavaScript Snippets](#javascript-snippets)
		- [how to slice arguments without leaking them](#how-to-slice-arguments-without-leaking-them)
		- [fast bind](#fast-bind)
		- [play sound from arraybuffer](#play-sound-from-arraybuffer)
		- [escape regexp](#escape-regexp)
		- [log some variables in format](#log-some-variables-in-format)
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
Command + Option + F 在所有源码中查找
```

### Atom

```
ctrl + shift + \ 在treeview中找到当前文件
ctrl + \ 切换treeview
ctrl + alt + I 打开Devtools
ctrl + D 选中下一个内容相同的选区
A 新建文件(选中treeview中的某个目录后)
shift + A 新建文件夹(选中treeview中的某个目录后)
D 复制当前文件到当前目录
ctrl + P 模糊查找
ctrl + shift + P atom中所有的命令
ctrl + , 打开setting
ctrl + G 跳转到指定行&列
ctrl + alt + Q 合并成一行
ctrl + shift + F2 清除所有书签
```

以下是自行覆盖的快捷键，请无视

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

### force delete files in node_modules

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

## chrome

### chrome offline dinosaur game

chrome://dino/

## yrm

### install yrm

```bash
$ npm i -g yrm
```

### list

```bash
$ yrm ls
```

### use

```bash
$ yrm use taobao # use taobao registry
$ yrm use npm # use npm registry
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
$ npm i <packageName> [-S/-D]
```

### show detail during installation

```bash
$ npm i <packageName> -d
```

### package searching strategy in npm scripts

e.g.
```json
{
	"scripts": {
		"dev": "onchange ..."
	}
}
```
npm adds `node_modules/.bin` for searching `onchange` package, it means you don't have to write the `node_modules/.bin` prefix

> In addition to the shell's pre-existing PATH, npm run adds node_modules/.bin to the PATH provided to scripts. Any binaries provided by locally-installed dependencies can be used without the node_modules/.bin prefix

参考：https://docs.npmjs.com/cli/run-script

### custom arguments when executing npm scripts

```bash
$ npm run test -- --grep="pattern"
```

> As of npm@2.0.0, you can use custom arguments when executing scripts. The special option -- is used by getopt to delimit the end of the options. npm will pass all the arguments after the -- directly to your script

> The arguments will only be passed to the script specified after npm run and not to any pre or post script

参考：https://docs.npmjs.com/cli/run-script

### install from local folder as dependency

npm 2.0.0 [supports specifying local dependencies in your package.json](https://docs.npmjs.com/files/package.json#local-paths):

> npm install --save ../apple
> cat package.json
{
  "name": "bowl",
  "version": "1.0.0",
  "dependencies": {
    "apple": "file:../apple"
  }
}
npm install will copy (and npm install) the package into the target's node_module's hierarchy.

This is not an ideal workflow during development: any time you modify your local dependency, you must reinstall it in every location that depends on it. If you do not update all copies, you will have different versions of the same code, probably under the same version number.

本地有两个npm packages，A和B存在依赖关系，假设A依赖B，可以A中require B的本地代码，这样在安装B的时候，npm就会通过指定的本地路径将B安装到A的node_modules中

具体使用参考：[eslint-plugin-import](https://github.com/benmosher/eslint-plugin-import/blob/001b8de7fb067167ee1d53252cff914e9b93464c/package.json#L59)

devDependencies和dependencies中都声明了`eslint-import-resolver-node`的依赖，但devDependencies中用的是本地代码，调试通过后再发布当前仓库和`eslint-import-resolver-node`到npm

参考：https://github.com/timoxley/linklocal#about

### npm t

short for `npm test`

### npm.im

https://npm.im/pure-ui

### npm cdn

https://unpkg.com/pure-ui/dist/

### npm search

https://npms.io/

### scoped-packages

@开头的npm包

参考：[scoped-packages](https://docs.npmjs.com/getting-started/scoped-packages)

### avoid installing devDependencies

```bash
$ npm install --production
```

### view package versions or tags

```bash
$ npm view «package-name» versions
$ npm view «package-name» dist-tags
```

### publish with tag

```bash
$ npm publish --tag beta
```

默认会发布到latest的tag上，tag相当于是一个别名，作为一个特殊的发布通道，和chrome的canary、firefox的nightly是类似的

注意：不要把tag名字用数字或v开头，可能会和semver版本号冲突

参考：
http://www.2ality.com/2015/12/npm-install-tag-version.html
https://docs.npmjs.com/getting-started/using-tags

### modify npm tag

```bash
$ npm dist-tag add packagename@1.1.0 latest
```

### clean npm cache

```bash
$ npm cache clean
```

### add package collaborators

```bash
$ npm owner add <user> <package name>
```

### get global node_modules path

```bash
$ npm config get prefix
```

### register git subcommand with npm package

```json
{
    "git-jira": "bin/jira.js"
}
```

`git-jira` and `git jira` both work

参考：https://github.com/commitizen/cz-cli

### npm help scripts

```bash
$ npm help scripts
```

### transfer package ownership to others

```bash
$ npm owner add <username> <packagename>
```

### more npm tricks

[...more npm tricks](https://gist.github.com/AvnerCohen/4051934)

## yarn

### install all dependencies

```bash
$ yarn
```

### install

```bash
$ yarn add <packageName>
```

### uninstall

```bash
$ yarn remove <packageName>
```

### add devDependencies

```bash
$ yarn add <packageName> --dev
```

### add peerDependencies

```bash
$ yarn add <packageName> --peer
```

### global install

```bash
$ yarn global add <packageName>
```

note: There are some issues with `global add` in windows OS

### set registry

```bash
$ yarn config set registry https://registry.npm.taobao.org
```

### list all config

```bash
$ yarn config list
```

## Koa

### get params

```js
ctx.request.body // your POST params
ctx.params // URL params, like :id
ctx.query // params from querystring
```

## Node

### clear command line console

```js
process.stdout.write( '\x1bc' );
```

参考：[friendly-errors-webpack-plugin](https://github.com/geowarin/friendly-errors-webpack-plugin/blob/db5d5c9a48228e31ad429755f2304d9be57b96ba/src/output.js#L60)

### run global package from command line -> No such file or directory

line-ending为CRLF，改成LF可以解决

> 可以在atom的core packages里面找到line-ending-selectoring，在setting里面修改新建文件时的默认换行符为LF

其他可能的原因在这里有提到 https://github.com/nodejs/node-v0.x-archive/issues/3911#issuecomment-218380292

### change working directory

```js
process.chdir( 'path/to/directory' );
```

### debug with chrome devtools

```bash
node --inspect --debug-brk index.js
```

for node v7+

```bash
$ node --inspect-brk index.js
```

参考：https://medium.com/@paul_irish/debugging-node-js-nightlies-with-chrome-devtools-7c4a1b95ae27

### node REPL for multiline support

type ".editor" in your node REPL for multiline support, and hit ^D to execute

参考：https://twitter.com/atticoos/status/893496002933657600

### delete require cache

```js
delete require.cache[ require.resolve( '../../runners.json' ) ]
```

## Atom

### solve conflicts with emmet-atom and autocomplete-plus

overwrite enter in keymap.cson

```
'atom-text-editor:not(mini).autocomplete-active':
    'enter': 'autocomplete-plus:confirm'
```

参考：https://github.com/emmetio/emmet-atom/issues/146#issuecomment-103475628

### highlight according to file types

```cson
core:
   customFileTypes:
      'text.html.basic': [
        'rgl'
      ]
```

参考：[Customizing Language Recognition](http://flight-manual.atom.io/using-atom/sections/basic-customization/#customizing-language-recognition)

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

### get current file scope type

```js
atom.workspace.getActiveTextEditor().getRootScopeDescriptor()
```

### how to find grammar scopes

http://flight-manual.atom.io/behind-atom/sections/scoped-settings-scopes-and-scope-descriptors/

## Package.json

### dependencies version

>指定版本：比如1.2.2，遵循“大版本.次要版本.小版本”的格式规定，安装时只安装指定版本。

>波浪号（tilde）+指定版本：比如~1.2.2，表示安装1.2.x的最新版本（不低于1.2.2），但是不安装1.3.x，也就是说安装时不改变大版本号和次要版本号。

>插入号（caret）+指定版本：比如ˆ1.2.2，表示安装1.x.x的最新版本（不低于1.2.2），但是不安装2.x.x，也就是说安装时不改变大版本号。需要注意的是，如果大版本号为0，则插入号的行为与波浪号相同，这是因为此时处于开发阶段，即使是次要版本号变动，也可能带来程序的不兼容。

>latest：安装最新版本。

> 摘自[package.json文件](http://javascript.ruanyifeng.com/nodejs/packagejson.html#toc2)

### prepublish

```json
{
    "scripts": {
        "prepublish": "..."
    }
}
```

execute some commands before publishing to npm

### "gulp-babel": "babel/gulp-babel#d8c67b"

```json
{
    "devDependencies": {
        "gulp-babel": "babel/gulp-babel#d8c67b"
    }
}
```

This will pick a specific commit

参考：https://github.com/babel/babel/pull/6056/files#r137702263

## Webpack

### dynamic require all modules from directory

```js
const load = requireContext => {
	return requireContext.keys().map(requireContext)
}

const modules = load(require.context('./', true, /.js$/))
```

> requireContext.keys()会返回当前上下文下的所有路径，requireContext本身是一个函数，可以当作require来用(基于某个上下文的)

> 参考：[webpack文档](https://webpack.github.io/docs/context.html#context-module-api)

### make webpack output colorful when using webpack-dev-middleware

Add `colors: true`

```js
webpackDevMiddleware( compiler, {
	stats: {
		colors: true
	}
} );
```

### hide extra info when bundling with webpack-dev-middleware

```js
webpackDevMiddleware( compiler, {
	stats: {
		modules: false,
		children: false,
		chunks: false,
		chunkModules: false,
	}
} );
```

### webpack doesn't looking up for peerDependencies in parent node_modules when in soft-linked node_modules

e.g. When using lerna

```js
resolve: {
  // 由于软链接后peerDependencies不会主动查找上层node_modules，指定fallback
  fallback: _.cwd( 'node_modules' ),
},
```

## Babel

### babel6 always export a default to exports.default

workaround: [babel-plugin-add-module-exports](https://github.com/59naga/babel-plugin-add-module-exports)

参考：http://stackoverflow.com/questions/34736771/webpack-umd-library-return-object-default

## Lerna

### lerna init

初始化一个monorepo

### lerna bootstrap

packages中的包不需要发布到npm，但是如果没有发布的话需要自己手动在package.json中添加类似^0.1.0的依赖

## Command line

### back to previous directory

```bash
$ cd -
```

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

### checkout to previous branch

```bash
$ git checkout -
```

### make git case-sensitive

```bash
$ git config core.ignorecase false
```

### git pull -> error: unable to resolve reference refs/remotes/origin/xxx

```bash
rm .git/refs/remotes/origin/xxx
git fetch
```

it works for me

### show all global config

```bash
$ git config --global -l
```

### discard unstaged changes

#### a specific file

```bash
$ git checkout path/to/file
```

#### all unstaged files

```bash
$ git checkout -- .
```

参考：https://stackoverflow.com/questions/52704/how-do-i-discard-unstaged-changes-in-git/52713#52713

## GitHub

### search in certain path in github repo

```
<keyword> path:<path>
```

### readme

<kbd>Ctrl</kbd> + <kbd>C</kbd>

```diff
- "build": "react-scripts build"
+ "build": "react-scripts build && react-snapshot"
```

| foo | bar |
| :---: | :---: |

☑☐

⚠️

⇗

⬡

### badges

[![](https://img.shields.io/badge/made%20with-%e2%9d%a4-ff69b4.svg?style=flat-square)]()

```
[![](https://img.shields.io/badge/made%20with-%e2%9d%a4-ff69b4.svg?style=flat-square)]()
```

from: https://github.com/vinta/pangu.js/

[![license](https://img.shields.io/badge/license-MIT-000000.svg?style=flat-square)](LICENSE)


```
[![license](https://img.shields.io/badge/license-MIT-000000.svg?style=flat-square)](LICENSE)
```

### rawgit cdn

e.g. https://cdn.rawgit.com/Marak/faker.js/master/examples/browser/index.html

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

### launch at login

> electron added built-in support for launching at login using app.setLoginItemSettings. One drawback is that it only works for macOS and Windows at the moment, whereas the auto-launch npm package works on Linux too

参考：https://github.com/muan/mojibar/issues/67

### ready-to-show

在ready-to-show触发后再显示主窗口，可以有更好的体验

## JavaScript

### const is block-scoped

Constants are block-scoped, much like variables defined using the let statement

参考：[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)

### es6 解构 + 别名

```js
const { types: t } = babel;
```

等价于

```
const t = babel.types;
```

### Promise.race([]) returns a forever pending promise

https://twitter.com/jdalton/status/790263748732661760

### for ... in

for in 循环的顺序和书写的顺序有关
比如遍历
```js
{
	a: 1,
	b: 1,
	c: 1
}
```
和
```js
{
	c: 1,
	b: 1,
	a: 1
}
```
的顺序是不一样的

### use yield with an array in co

```js
const [ rst0, rst1 ] = yield [ promise0, promise1 ];
```

### filter out falsy values

```js
// filter out falsy values
[].filter(Boolean)
```

参考：https://github.com/babel/babel/blob/53ed4e5eb86902cf577e990bfe4f7d917a66ea65/packages/babel-preset-es2015/src/index.js#L72

### comment

```js
/* ---------------- 8< -------- 8< ---------------- */
```

from [proselint](https://github.com/sapegin/proselint/blob/23227be2448518b6003902187ebb27db63d657cf/src/index.js#L32)

```js
// Backbone.sync
// -------------
```

from [backbone](https://github.com/jashkenas/backbone/blob/3141352b83e78a41c524fb69c39219550a056e0d/backbone.js#L1469-L1470)

```js
// ===================== //
// _nativeFunctionObject //
// ===================== //
```

from [otto](https://github.com/robertkrimen/otto/blob/master/type_function.go#L28-L30)

### Array.prototype.includes

[ NaN ].indexOf( NaN ) === -1
[ NaN ].includes( NaN ) === true

### a.splice(i >>> 0, 1) === if (i !== -1) a.splice(i, 1)

因为-1 >>> 0 === 0xFFFFFFFF, max possible array length
所以上面两者是等价的

参考：https://github.com/ai/nanoevents/blob/f445d5fe7beccdb5ae0c57858444fe9a8b7c38e7/index.js#L66

### add font-family via js

```js
const iconfont = new FontFace(fontFamily, 'url(' + uri + ')');
document.fonts.add(iconfont);
```

参考：[rax-icon](https://github.com/alibaba/rax/blob/fd216de80df3910c7c0f4108d254d985e1b4dd79/packages/rax-icon/src/index.js#L33-L35)

### 8 immutable arrays operations you should know

![](https://i.loli.net/2017/12/12/5a2f9eb4c9749.png)

参考：https://twitter.com/lukejacksonn/status/928244319760220160

### 9 get language in browser

```js
navigator.language // "zh-CN"
```

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

### log string in format

```js
console.log('new: %s, old: %s', new, old);
```

### neat way to chain promises

```js
const ArrarOfFunctionsReturnPromise = [ ... ];
ArrarOfFunctionsReturnPromise.reduce( function ( total, current ) {
    return total.then( current );
}, Promise.resolve() ).then( ... );
```

### find function definition in Source panel in console

```js
inspect( fn )
```

### measure text in canvas context

```js
ctx.measureText( 'text' )
```

### get network status

```js
navigator.onLine
```

### network events

```js
window.addEventListener('online', whenOnline)
window.addEventListener('offline', whenOffline)
```

## CSS Snippets

### auto fit content width

```css
/* 宽度自适应内容 */
width: -webkit-fit-content
```

### @supports

```css
@supports( display: grid ) {
	/* ... */
}
```

### repeating-linear-gradient

```css
background-color: #eee;
background-image: repeating-linear-gradient(-45deg,transparent,transparent 5px,rgba(255,255,255,.5) 5px,rgba(255,255,255,.5) 10px), repeating-linear-gradient(45deg,transparent,transparent 5px,rgba(255,255,255,.5) 5px,rgba(255,255,255,.5) 10px);
```

### grid-like

```css
background-color: rgba(0, 0, 0, 0.05);
background-image: repeating-linear-gradient(0deg, transparent, transparent 7px, rgba(0, 0, 0, 0.2) 1px, transparent 8px), repeating-linear-gradient(90deg, transparent, transparent 7px, rgba(0, 0, 0, 0.2) 1px, transparent 8px);
background-size: 8px 8px;
```

### text gradient

```css
background: -webkit-linear-gradient(left,#00c0f9, #4d8cff, #9f72ff);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
```

参考：https://atomiks.github.io/tippyjs/

## Others

### Don’t write “flexible” modules

> Don’t write “flexible” modules. No matter how you plan, you’ll miss some future requirements. Write modules that are easy to delete.

> This is why composition is better than inheritance. Inheritance = trying to anticipate all future cases. Composition = replaceable units.

https://twitter.com/dan_abramov/status/793124347573665796

### lovely symbols

˗ˏˋ text ˎˊ˗

### try it on codepen

<img src="http://blog.codepen.io/wp-content/uploads/2012/06/TryItOn-CodePen.png" height="50" />

### Open in gitpod

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/firefox-devtools/profiler)

### 暗中观察

> ┻┳|  
> ┳┻| _  
> ┻┳| •.•) 💬 *"Tip: Use [pikapkg.com](https://www.pikapkg.com) to find modern, web-ready packages on npm :)"*  
> ┳┻|⊂ﾉ     
> ┻┳|  

from: https://github.com/pikapkg/web
