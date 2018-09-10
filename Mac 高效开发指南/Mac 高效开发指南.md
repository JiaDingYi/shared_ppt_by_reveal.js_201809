# Mac 高效开发指南


本书已被字节跳动收录为公司级别的，新员工入职培训的通用基础课程，帮助近千名员工更加深入全面的了解他们最亲密的工作伙伴。


提到 Mac，大家的第一反应是什么？


对我来说，就是吃饭的家伙。
<p class="fragment fade-up">能够提高吃饭的效率对我来说，诱惑力还是蛮大的。</p>
<p class="fragment fade-up">这次分享，也许不会让你每天节省出一顿饭的时间，</p>
<p class="fragment fade-up">但是一杯咖啡的时间，也许可以。</p>


另外，可能不是每一个人都有 Mac，
<p class="fragment fade-up">但是希望这次分享能够给你们一种对于工作效率的启发，</p>
<p class="fragment fade-up">善于发现工具之美。</p>


《荀子·劝学》

吾尝终日而思矣，不如须臾之所学也；

吾尝跂而望矣，不如登高之博见也。

登高而招，臂非加长也，而见者远；

顺风而呼，声非加疾也，而闻者彰。

假舆马者，非利足也，而致千里；

假舟楫者，非能水也，而绝江河。

君子生非异也，善假于物也。



## 第一章
**先从 Mac 系统说起，**虽然大部分程序员都使用 Mac 电脑，但这个系统并不是为程序员量身定制的，为了考虑大多数用户，必然做出妥协。因此我们有必要做一些定制，让 Mac 系统对开发者更加友好。


### 开启三指拖移功能
<img src="https://github.com/JiaDingYi/shared_ppt_by_reveal.js_201809/blob/master/Mac%20高效开发指南/1536465087345.png?raw=true" width="600" height="550">


### 光标移动
这里比较推荐使用 Emacs 系的快捷键而不是传统的 Command + ←/→/Delete之类的。因为后者并不通用，比如在终端中就无法使用，而 Emacs 系的快捷键则在几乎所有系统级别的输入框内都通用。


Emacs:
<img src="https://raw.githubusercontent.com/JiaDingYi/shared_ppt_by_reveal.js_201809/master/resources/Snip20180910_5.png">


常见的几个行级别操作有：
1. Ctrl + A：移动到行首
2. Ctrl + E：移动到行尾
3. Ctrl + K：删除到行尾
4. Ctrl + U：删除到行头
5. Ctrl + N：移动到下一行
6. Ctrl + P：移动到上一行

前三个命令在终端中非常常用，能大幅度提高工作效率。后两个命令则在 Vim 系列中很常见，多用于上下切换列表中的选项。



## 第二章
**会介绍各种神级软件，**比如虽然颜值略低但功能爆表的邮件应用、完全可以替代系统终端的 iTerm2、Mac 上的最强应用（没有之一）Alfred、Chrome 的优秀插件，以及老生常谈的爱国上网最佳实践。


### 邮件规则
无论是公司邮箱还是个人邮箱，经常会收到具备某些固定特征的邮件。比如银行信用卡的邮件，某个网站订阅后的邮件，或者公司内特定部门、发件人的邮件等等。

对于这类具备固定特征的邮件，我们可以利用系统自带的邮件应用，给他们添加分类、过滤规则。


### 终端神器 iTerm2
iTerm2 是一个用来取代系统终端的命令行工具，功能比原生的终端程序强大很多，可以一行命令安装：
```
brew cask install iterm2
```
note:
说一点个人使用心得，iTerm2 与 terminal 相比，说不出哪一点最突出，但是每一个方面都要比 terminal 优秀一点点，所有优势积累起来，强的就不是一星半点了。


#### 快速编辑
有时候，如果上一条命令出现了某个小错误，其实不必重新打一遍，可以使用 ^old^new 的写法进行替换，它表示把原来命令中匹配 old 的部分替换成 new，如下图所示：


<img src="https://raw.githubusercontent.com/JiaDingYi/shared_ppt_by_reveal.js_201809/master/resources/assets--LBLo0eP1FW2IkggnToa--LDvQXj1FAD-kiaMg-4g--LDvQiDgnia_CPL_Dr4H-iterm-edit.gif" width="600" height="550">


对于特别长的命令，可以使用 zsh 提供的快捷键 Ctrl-x + Ctrl-e 进入 vim 编辑：


<img src="https://raw.githubusercontent.com/JiaDingYi/shared_ppt_by_reveal.js_201809/master/resources/assets--LBLo0eP1FW2IkggnToa--LDvQXj1FAD-kiaMg-4g--LDvQjoj8MWI4S_5beyR-iterm-vim.gif" width="600" height="550">


### Alfred
Alfred 绝对是让 Mac 更加好用的神器之一，如果 Mac 上只能安装一款三方软件，那非 Alfred 莫选。我把 Alfred 拔高到如此地位绝非是为了捧杀它，而是确实实至名归，本文主要会介绍 Alfred 原生的用法。

除了 Alfred 软件自带的功能外，它还允许用户自己开发 workflow 并分享出来，正是这些 workflow，彻底奠定了 Alfred 的神器地位.


#### 文件/程序搜索
文件搜索是 Alfred 最基础的功能，类似于系统的 Spotlight，快捷键打开 Alfred 的窗口，然后输入文件名即可。
这也是为什么我会设置 Dock 栏隐藏的原因，毕竟有了 Alfred，谁会去 Dock 里面找 App 呢。

关于文件的搜索，我们还可以配置搜索的范围，搜索哪些类型的文件等等，可以在 Features -> Default Results 中配置。


#### 网络搜索
如果我们想通过 Google 搜索东西，常规步骤是：

1. 打开 Chrome
2. 在地址栏输入 google.com
3. 打开谷歌主页，输入搜索内容
然而有了 Alfred，搜索步骤变成了：

1. 唤起 Alfred（显然比打开 Chrome 再进入 google.com 快得多）
2. 输入搜索内容，回车


#### 自己平时使用的一些小插件/app


- shadowsocks 的终端翻墙技巧


<img src="https://raw.githubusercontent.com/JiaDingYi/shared_ppt_by_reveal.js_201809/master/resources/Snip20180909_3.png">


<img src="https://raw.githubusercontent.com/JiaDingYi/shared_ppt_by_reveal.js_201809/master/resources/Snip20180909_4.png">


<img src="https://raw.githubusercontent.com/JiaDingYi/shared_ppt_by_reveal.js_201809/master/resources/Snip20180909_7.png">


- Go2Shell


- tree
   
<img src="https://raw.githubusercontent.com/JiaDingYi/shared_ppt_by_reveal.js_201809/master/resources/Snip20180909_8.png">


- markdown here

使用 markdown 语法编辑邮件



## 第三章
**会介绍 VSCode 和 Vim 的使用，**包括 Vim 的基本操作，快到超乎你想象的光标移动方式，让写代码变成一种享受的编辑技巧，以及各种 Life-Chaging 系列的插件。最后会介绍 VSCode + Vim 的最佳实践，从此忘掉老旧的 Sublime，抛弃慢到爆炸的 Atom 并且卸载掉 JetBrains 全家桶。


### 编辑器之神 vim
Vim 是纯键盘操作，因此在本书开头就描述过的误区同样适用于 Vim：

<h6>一些极端的人不够了解 Vim，感受不到 Vim 的价值，因此拒绝学习 Vim。</h6>

<h6> 另一些极端的人过于沉迷于 Vim，想把 Vim 从编辑器打造成 IDE。因此在本章开头我就想强调的是：</h6>

<h6> Vim 就是个编辑器，用来输入、标记文本的，编程相关的东西交给 IDE 就好了.</h6>


学习 vim 是一项耗时巨大，操作繁琐的工程，这里不做详细介绍。
本人也在摸索学习当中。


这里介绍一下作者的编辑器选型：
1. 前端/Node/其它脚本开发：VSCode + Vim 插件
2. iOS 开发：Xcode，没有选择 XVim 是因为经常遇到诡异问题，而且不支持 Vim 插件根本没法用
3. Android 开发：Android Studio + Vim 插件

客户端开发其实没什么选择的，因为暂时没有能完全替代官方 IDE 的东西。


###  VSCode 最佳实践


#### 通用插件
- Beautify：代码格式化插件，可以将 JS、CSS 和 HTML 代码格式化
- Code Outline ：支持多种语言的 outline 提取
- Code Runner：可以运行多种语言，我配置的快捷键为 Command + R。注意新的文本文件因为没 有后缀名，要用快捷键 Command + K + M 手动切换语言类型。
- Dash：使用快捷键 Ctrl + h 快速打开 Dash 查找当前单词
- MarkdownLint：Markdown 语法检查，帮助你写出标准的 Markdown


- Project Manager：帮助你管理项目，在多个项目间切换，快捷键 Option + P（首先要添加进项目列表）
- TODO Highlight：高亮显示 TODO
- VSCode Icons：根据文件和文件夹名称展示恰当的图标
-  Bracket Pair Colorizer：给成对的括号配上颜色，方便区分
-  File Size：在底部 bar 中显示文件大小
-  Path Intellisense：自动补全文件路径


#### 前端插件


- Auto Close Tag：自动补全另一侧的 Tag
- Auto Rename Tag：修改一个 Tag 时，另一侧的 Tag 自动修改
- Color Highlight：遇到颜色字符串，自动在旁边显示颜色，方便预览
- CSS Peek：
- ESLint：代码格式化，支持实时监测和保存时自动修改


- HTML Snippets：HTML 语法片段，方便快速输入
- IntelliSense for CSS class：CSS 自动补全
- JavaScript code snippets：JS 的语法片段，方便快速输入
- Modern JavaScript Snippets：补充了一些更新的语法片段
- HTML CSS Support：方便在 HTML 中插入 CSS 代码
- SASS：sass 格式文件的代码补全和高亮
- Vetur：Vue 开发必备的插件，提供代码补全、高亮等功能
- Vue 2 Snippets：Vue 2 的代码片段
- Vue peek：快速跳转定义


#### 语法插件

一般用什么语言就装什么插件就行了。比如 Node、Bash、Python、Go、Ruby 等。



## 第四章
**重点介绍 git 的进阶使用，**首先会深入浅出的科普 git 的底层原理，让读者能对 git 有正确的认识，彻底摆脱只会 pull/add/commit/push 的小白状态。本章会对几乎所有常用的 git 命令做介绍，包括进阶命令的使用，以及常用参数的解释，结合 log 和 diff 两大工具，充分发挥 git 的版本控制能力。


### scmpuff
scmpuff 是一个 git 拓展，支持数字快捷键的操作，如图所示：

<img src="https://raw.githubusercontent.com/JiaDingYi/shared_ppt_by_reveal.js_201809/master/resources/assets--LBLo0eP1FW2IkggnToa--LDuHND1oS1WGQ-lzuGt--LDuHeZoy8d96wRwe_qY-image.png" width="800" height="350">

<font size=4>尤其是当文件路径较长时，我们可以用数字来代替文件，同时也支持 1-3 这种写法，表示多个文件。</font>


### log

<img src="https://raw.githubusercontent.com/JiaDingYi/shared_ppt_by_reveal.js_201809/master/resources/Snip20180909_9.png">


### 交互式 Rebase
对于已经存在但还没有推送到远程的提交记录，我们可以使用 rebase -i 去编辑他们。假设我们想修改最近三次提交，可以输入 gri head~3，它是完整写法是：
```
git rebase -i head~3
```
这个命令会展示出最近的三次提交，最老的提交在最上面，最新的提交在最下面，这是因为 git 会按照从旧到新的顺序编辑这些提交。展示的格式如下：


<img src="https://raw.githubusercontent.com/JiaDingYi/shared_ppt_by_reveal.js_201809/master/resources/Snip20180909_10.png">


### git pull --rebase upstream master
一个有争议的命令，仁者见仁，智者见智。


### git bisect



## 第五章
**是本书的精华所在，**从实用角度出发，结合我近三年的 shell 经验，向读者展示一个奇妙的 shell 世界，挖掘前人大牛们留下来的宝藏。包含了 shell 模型的科普，系统常用命令的介绍，sed/awk 等进阶命令的使用，以及用大量用 shell 提高研发效率的例子。


Shell 是一个非常庞大的话题，它的学习路线和普通的编程语言不一致，使用场景在很多人看来也不多。但其实 Shell 是非常强大的胶水语言，能把其它各个模块和系统很好的串联起来，同时由于 shell 非常底层，更加接近操作系统，所以非常用来和系统的软硬件生态打交道。


oh-my-zsh


fastlane


shell 的学习是持之以恒的过程，由于时间关系，所以这里不做介绍了。
大家私下多多交流。