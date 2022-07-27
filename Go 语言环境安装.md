
# Go 语言环境安装
<p>Go 语言支持以下系统：</p>
<ul>
<li>Linux</li>
<li>FreeBSD</li>
<li>Mac OS X（也称为 Darwin）</li>
<li>Windows</li>
</ul><p>
安装包下载地址为：<a target="_blank" href="https://golang.org/dl/" rel="noopener noreferrer">https://golang.org/dl/</a>。</p>
<p>如果打不开可以使用这个地址：<a href="https://golang.google.cn/dl/" rel="noopener noreferrer" target="_blank">https://golang.google.cn/dl/</a>。</p>
<p>各个系统对应的包名：</p>
<table class="reference">
<tbody><tr><th style="width:20%">操作系统</th><th>包名</th></tr>
<tr><td>Windows</td><td>go1.4.windows-amd64.msi</td></tr>
<tr><td>Linux</td><td>go1.4.linux-amd64.tar.gz</td></tr>
<tr><td>Mac</td><td>go1.4.darwin-amd64-osx10.8.pkg</td></tr>
<tr><td>FreeBSD</td><td>go1.4.freebsd-amd64.tar.gz</td></tr>
</tbody></table>

<hr>
<h2>UNIX/Linux/Mac OS X, 和 FreeBSD 安装</h2>
<p>以下介绍了在UNIX/Linux/Mac OS X, 和 FreeBSD系统下使用源码安装方法：</p>
<p>1、下载二进制包：go1.4.linux-amd64.tar.gz。</p>
<p>2、将下载的二进制包解压至 /usr/local目录。</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">tar </span><span class="pun">-</span><span class="pln">C </span><span class="pun">/</span><span class="pln">usr</span><span class="pun">/</span><span class="kwd">local</span><span class="pln"> </span><span class="pun">-</span><span class="pln">xzf go1</span><span class="pun">.</span><span class="lit">4.linux</span><span class="pun">-</span><span class="pln">amd64</span><span class="pun">.</span><span class="pln">tar</span><span class="pun">.</span><span class="pln">gz</span></pre>
<p>3、将 /usr/local/go/bin  目录添加至 PATH 环境变量：</p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">export</span><span class="pln"> PATH</span><span class="pun">=</span><span class="pln">$PATH</span><span class="pun">:</span><span class="str">/usr/</span><span class="kwd">local</span><span class="pun">/</span><span class="pln">go</span><span class="pun">/</span><span class="pln">bin</span></pre>
<p>以上只能暂时添加 PATH，关闭终端下次再登录就没有了。</p>
<p>我们可以编辑 ~/.bash_profile 或者 /etc/profile，并将以下命令添加该文件的末尾，这样就永久生效了：</p>

<pre class="prettyprint prettyprinted" style=""><span class="kwd">export</span><span class="pln"> PATH</span><span class="pun">=</span><span class="pln">$PATH</span><span class="pun">:</span><span class="str">/usr/</span><span class="kwd">local</span><span class="pun">/</span><span class="pln">go</span><span class="pun">/</span><span class="pln">bin</span></pre>
<p>添加后需要执行：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">source </span><span class="pun">~/.</span><span class="pln">bash_profile
</span><span class="pun">或</span><span class="pln">
source </span><span class="pun">/</span><span class="pln">etc</span><span class="pun">/</span><span class="pln">profile</span></pre>
<blockquote><p><strong>注意：</strong>MAC 系统下你可以使用 <strong>.pkg</strong> 结尾的安装包直接双击来完成安装，安装目录在 <strong>/usr/local/go/</strong> 下。</p></blockquote>


<hr>
<h2>Windows 系统下安装</h2>
<p>Windows 下可以使用 .msi 后缀(在下载列表中可以找到该文件，如go1.4.2.windows-amd64.msi)的安装包来安装。</p>
<p>默认情况下 <strong>.msi</strong> 文件会安装在 <strong>c:\Go</strong> 目录下。你可以将 <strong>c:\Go\bin</strong> 目录添加到 <strong>Path</strong> 环境变量中。添加后你需要重启命令窗口才能生效。</p>

<h3>安装测试</h3>
<p>创建工作目录  <strong>C:\&gt;Go_WorkSpace</strong>。</p>

<div class="example"><h2 class="example">test.go 文件代码：</h2><div class="example_code">

<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Println<span style="color: #339933;">(</span><span style="color: #cc66cc;">"Hello, World!"</span><span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>


<p>使用 go 命令执行以上代码输出结果如下：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">C</span><span class="pun">:</span><span class="pln">\Go_WorkSpace</span><span class="pun">&gt;</span><span class="pln">go run test</span><span class="pun">.</span><span class="pln">go

</span><span class="typ">Hello</span><span class="pun">,</span><span class="pln"> </span><span class="typ">World</span><span class="pun">!</span></pre>			<!-- 其他扩展 -->
