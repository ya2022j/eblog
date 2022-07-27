# Go 语言教程
<div class="tutintro">
<p>Go 是一个开源的编程语言，它能让构造简单、可靠且高效的软件变得容易。</p>
<p>Go是从2007年末由Robert Griesemer, Rob Pike, Ken Thompson主持开发，后来还加入了Ian Lance Taylor, Russ Cox等人，并最终于2009年11月开源，在2012年早些时候发布了Go 1稳定版本。现在Go的开发已经是完全开放的，并且拥有一个活跃的社区。</p>

<hr>
<h2>Go 语言特色</h2>

<ul>
<li>简洁、快速、安全</li><li>
并行、有趣、开源</li><li>
内存管理、数组安全、编译迅速</li>
<hr>
<h2>Go 语言用途</h2>
<p>Go 语言被设计成一门应用于搭载 Web 服务器，存储集群或类似用途的巨型中央服务器的系统编程语言。</p><p>对于高性能分布式系统领域而言，Go 语言无疑比大多数其它语言有着更高的开发效率。它提供了海量并行的支持，这对于游戏服务端的开发而言是再好不过了。</p>
<hr>
<h2>第一个 Go 程序</h2>
<p>接下来我们来编写第一个 Go 程序 hello.go（Go 语言源文件的扩展是 .go），代码如下：</p>
<div class="example">
<h2 class="example">hello.go 文件</h2>
<div class="example_code">

<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Println<span style="color: #339933;">(</span><span style="color: #cc66cc;">"Hello, World!"</span><span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>



<p>要执行 Go 语言代码可以使用  <span class="marked">go run</span> 命令。</p>
<p>执行以上代码输出:</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">$ go run hello</span><span class="pun">.</span><span class="pln">go 
</span><span class="typ">Hello</span><span class="pun">,</span><span class="pln"> </span><span class="typ">World</span><span class="pun">!</span></pre>

<p>此外我们还可以使用 <span class="marked">go build</span> 命令来生成二进制文件：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">$ go build hello</span><span class="pun">.</span><span class="pln">go 
$ ls
hello&nbsp;&nbsp;&nbsp;&nbsp;hello</span><span class="pun">.</span><span class="pln">go
$ </span><span class="pun">./</span><span class="pln">hello 
</span><span class="typ">Hello</span><span class="pun">,</span><span class="pln"> </span><span class="typ">World</span><span class="pun">!</span></pre>


