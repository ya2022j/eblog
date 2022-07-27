
		
# Go 语言结构

<p>
在我们开始学习 Go 编程语言的基础构建模块前，让我们先来了解 Go 语言最简单程序的结构。</p>
<hr>
<h2>
Go Hello World 实例</h2>
<p>Go 语言的基础组成有以下几个部分：</p>
<ul>
<li>包声明</li>
<li>引入包</li>
<li>函数</li>
<li>变量</li>
<li>语句 &amp; 表达式</li>
<li>注释</li>
</ul> 
<p>
接下来让我们来看下简单的代码，该代码输出了"Hello World!":</p>

<div class="example"><h2 class="example">实例</h2><div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 这是我的第一个简单的程序 */</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"Hello, World!"</span><span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>


<p>让我们来看下以上程序的各个部分：</p>

<ol class="list">
<li><p>第一行代码 <i>package main</i> 定义了包名。你必须在源文件中非注释的第一行指明这个文件属于哪个包，如：package main。package main表示一个可独立执行的程序，每个 Go 应用程序都包含一个名为 main 的包。</p></li>
<li><p>下一行 <i>import "fmt"</i> 告诉 Go 编译器这个程序需要使用 fmt 包（的函数，或其他元素），fmt 包实现了格式化 IO（输入/输出）的函数。</p></li>
<li><p>下一行 <i>func main()</i> 是程序开始执行的函数。main 函数是每一个可执行程序所必须包含的，一般来说都是在启动后第一个执行的函数（如果有 init() 函数则会先执行该函数）。</p></li>
<li><p>下一行 /*...*/ 是注释，在程序执行时将被忽略。单行注释是最常见的注释形式，你可以在任何地方使用以 // 开头的单行注释。多行注释也叫块注释，均已以 /* 开头，并以 */ 结尾，且不可以嵌套使用，多行注释一般用于包的文档描述或注释成块的代码片段。 </p></li>
<li><p>下一行 <i>fmt.Println(...)</i> 可以将字符串输出到控制台，并在最后自动增加换行字符 \n。
<br>使用 fmt.Print("hello, world\n") 可以得到相同的结果。
<br>
Print 和 Println 这两个函数也支持使用变量，如：fmt.Println(arr)。如果没有特别指定，它们会以默认的打印格式将变量 arr 输出到控制台。
</p></li>
<li><p>当标识符（包括常量、变量、类型、函数名、结构字段等等）以一个大写字母开头，如：Group1，那么使用这种形式的标识符的对象就可以被外部包的代码所使用（客户端程序需要先导入这个包），这被称为导出（像面向对象语言中的 public）；标识符如果以小写字母开头，则对包外是不可见的，但是他们在整个包的内部是可见并且可用的（像面向对象语言中的 protected ）。</p></li>
</ol>
<hr>
<h2>执行 Go 程序</h2>
<p>
让我们来看下如何编写 Go 代码并执行它。步骤如下：</p>

<ol>
<li><p>打开编辑器如Sublime2，将以上代码添加到编辑器中。</p></li>
<li><p>将以上代码保存为 <i>hello.go</i></p></li>
<li><p>打开命令行，并进入程序文件保存的目录中。</p></li>
<li><p>输入命令 <i>go run hello.go</i> 并按回车执行代码。 </p></li>
<li><p>如果操作正确你将在屏幕上看到 <i>"Hello World!"</i> 字样的输出。</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">$ go run hello</span><span class="pun">.</span><span class="pln">go
</span><span class="typ">Hello</span><span class="pun">,</span><span class="pln"> </span><span class="typ">World</span><span class="pun">!</span></pre>
</li>

<li>
<p>我们还可以使用 <span class="marked">go build</span> 命令来生成二进制文件：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">$ go build hello</span><span class="pun">.</span><span class="pln">go 
$ ls
hello&nbsp;&nbsp;&nbsp;&nbsp;hello</span><span class="pun">.</span><span class="pln">go
$ </span><span class="pun">./</span><span class="pln">hello 
</span><span class="typ">Hello</span><span class="pun">,</span><span class="pln"> </span><span class="typ">World</span><span class="pun">!</span></pre>
</li>
</ol>


<h3>注意</h3>
<p>需要注意的是 <span class="marked">{</span> 不能单独放在一行，所以以下代码在运行时会产生错误：</p>
<div class="example"><h2 class="example">实例</h2><div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> &nbsp;<br>
<span style="color: #339933;">{</span> &nbsp;<span style="color: #666666; font-style: italic;">// 错误，{ 不能在单独的行上</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"Hello, World!"</span><span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>


		