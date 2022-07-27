
		
# Go 语言开发工具
<hr>
<h2>VSCode</h2>
<p>VScode 安装教程参见：<a href="https://www.runoob.com/w3cnote/vscode-tutorial.html" rel="noopener" target="_blank">https://www.runoob.com/w3cnote/vscode-tutorial.html</a></p>
<p>然后我们打开 VSCode 的扩展（<span class="marked">Ctrl+Shift+P</span>）：</p>
<p><img width="50%" src="https://www.runoob.com/wp-content/uploads/2015/06/go-vscode-1.jpeg"></p>
<p>搜索 <span class="marked">go</span>：</p>
<p><img width="70%" src="https://www.runoob.com/wp-content/uploads/2015/06/go-vscode-2.jpeg"></p>
<p>点击安装，安装完成后我们就可以使用代码提示、测试、调试等功能了。</p>
<p><img src="https://static.runoob.com/images/mix/completion-signature-help.gif"></p>
<hr>
<h2>GoLand</h2>
<p>GoLand 是 Jetbrains 家族的 Go 语言 IDE，有 30 天的免费试用期。</p>
<p>安装也很简单访问 <a href="https://www.jetbrains.com/go/" rel="noopener noreferrer" target="_blank">Gogland 的下载页面</a>，根据你当期的系统环境三大平台（Mac、Linux、Windows）下载对应的软件。</p>
<p><img src="https://www.runoob.com/wp-content/uploads/2015/06/GoLand-01.jpg"></p>
<hr>
<h2>LiteIDE</h2>
<p>LiteIDE 是一款开源、跨平台的轻量级 Go 语言集成开发环境（IDE）。</p>
<h3>支持的 操作系统</h3>
<ul><li>
Windows x86 (32-bit or 64-bit)</li><li>
Linux x86 (32-bit or 64-bit)</li></ul>
<p>
下载地址 ：<a target="_blank" href="http://sourceforge.net/projects/liteide/files/" rel="noopener noreferrer">http://sourceforge.net/projects/liteide/files/</a></p><p>
源码地址 ：<a target="_blank" href="https://github.com/visualfc/liteide" rel="noopener noreferrer">https://github.com/visualfc/liteide</a></p>

<img src="//www.runoob.com/wp-content/uploads/2015/06/1.4.liteide.png">
<hr>
<h2>Eclipse</h2>
<p>Eclipse 也是非常常用的开发利器，以下介绍如何使用 Eclipse 来编写 Go 程序。
</p><img class="attachment-full" src="//www.runoob.com/wp-content/uploads/2015/06/1.4.eclipse1.pngrawtrue" alt="1.4.eclipse1">

<p>Eclipse 编辑 Go 的主界面</p>
<ol>
	<li>首先下载并安装好 <a href="http://www.eclipse.org/">Eclipse</a></li>
	<li>下载 <a href="http://goclipse.github.io/" target="_blank" rel="noopener noreferrer">goclipse</a> 插件

<a href="https://github.com/GoClipse/goclipse/blob/latest/documentation/Installation.md#installation" target="_blank" rel="noopener noreferrer">https://github.com/GoClipse/goclipse/blob/latest/documentation/Installation.md#installation</a></li>
	<li><p>下载 gocode，用于 go 的代码补全提示
</p><p>
gocode 的 github 地址：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">https</span><span class="pun">:</span><span class="com">//github.com/nsf/gocode</span></pre>
<p>
在 Windows下要安装 git，通常用 <a href="https://gitforwindows.org/">msysgit</a>。
</p><p>
再在 cmd 下安装：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">go </span><span class="kwd">get</span><span class="pln"> </span><span class="pun">-</span><span class="pln">u github</span><span class="pun">.</span><span class="pln">com</span><span class="pun">/</span><span class="pln">nsf</span><span class="pun">/</span><span class="pln">gocode</span></pre>
<p>
也可以下载代码，直接用 go build 来编译，会生成 gocode.exe</p></li>
	<li>下载 <a href="http://sourceforge.net/projects/mingw/files/MinGW/">MinGW</a> 并按要求装好</li>
	<li>配置插件
<p>
Windows-&gt;Reference-&gt;Go
</p><p>
(1)、配置 Go 的编译器</p><p>
<img class="attachment-full" src="//www.runoob.com/wp-content/uploads/2015/06/1.4.eclipse2.pngrawtrue" alt="1.4.eclipse2">
</p><p>
设置 Go 的一些基础信息</p><p>

(2)、配置 Gocode（可选，代码补全），设置 Gocode 路径为之前生成的 gocode.exe 文件</p><p>
<img class="attachment-full" src="//www.runoob.com/wp-content/uploads/2015/06/1.4.eclipse3.pngrawtrue" alt="1.4.eclipse3"></p><p>
设置 gocode 信息</p><p>
(3)、配置 GDB（可选，做调试用），设置 GDB 路径为 MingW 安装目录下的 gdb.exe 文件</p><p><img class="attachment-full" src="//www.runoob.com/wp-content/uploads/2015/06/1.4.eclipse4.pngrawtrue" alt="1.4.eclipse4"></p><p>设置 GDB 信息</p></li>
	<li><p>测试是否成功
</p><p>
新建一个 go 工程，再建立一个 hello.go。如下图：
</p><p><img class="attachment-full" src="//www.runoob.com/wp-content/uploads/2015/06/1.4.eclipse5.pngrawtrue" alt="1.4.eclipse5"></p><p>

新建项目编辑文件
</p><p>

调试如下（要在 console 中用输入命令来调试）：
</p><p>
<img class="attachment-full" src="//www.runoob.com/wp-content/uploads/2015/06/1.4.eclipse6.pngrawtrue" alt="1.4.eclipse6"></p><p>
图 1.16 调试 Go 程序</p></li>
</ol>	
