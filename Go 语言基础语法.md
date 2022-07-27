
		
# Go 语言基础语法
<p>上一章节我们已经了解了 Go 语言的基本组成结构，本章节我们将学习 Go 语言的基础语法。</p>
<hr>
<h2>Go 标记</h2>

<p>Go 程序可以由多个标记组成，可以是关键字，标识符，常量，字符串，符号。如以下 GO 语句由 6 个标记组成：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">fmt</span><span class="pun">.</span><span class="typ">Println</span><span class="pun">(</span><span class="str">"Hello, World!"</span><span class="pun">)</span></pre>
<p>6 个标记是(每行一个)：</p>
<pre class="prettyprint prettyprinted" style=""><span class="lit">1.</span><span class="pln"> fmt
</span><span class="lit">2.</span><span class="pln"> </span><span class="pun">.</span><span class="pln">
</span><span class="lit">3.</span><span class="pln"> </span><span class="typ">Println</span><span class="pln">
</span><span class="lit">4.</span><span class="pln"> </span><span class="pun">(</span><span class="pln">
</span><span class="lit">5.</span><span class="pln"> </span><span class="str">"Hello, World!"</span><span class="pln">
</span><span class="lit">6.</span><span class="pln"> </span><span class="pun">)</span></pre>
<hr>
<h2>行分隔符</h2>
<p>在 Go 程序中，一行代表一个语句结束。每个语句不需要像 C 家族中的其它语言一样以分号 ; 结尾，因为这些工作都将由 Go 编译器自动完成。</p>
<p>如果你打算将多个语句写在同一行，它们则必须使用 ; 人为区分，但在实际开发中我们并不鼓励这种做法。</p>
<p>以下为两个语句：</p>
<div class="example"><div class="example_code">
fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"Hello, World!"</span><span style="color: #339933;">)</span><br>
fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"菜鸟教程：runoob.com"</span><span style="color: #339933;">)</span><br>
</div></div>
<hr>
<h2>注释</h2>

<p>注释不会被编译，每一个包应该有相关注释。</p>
<p>
单行注释是最常见的注释形式，你可以在任何地方使用以 // 开头的单行注释。多行注释也叫块注释，均已以 /* 开头，并以 */ 结尾。如：
</p>
<pre class="prettyprint prettyprinted" style=""><span class="com">// 单行注释</span><span class="pln">
</span><span class="com">/*
 Author by 菜鸟教程
 我是多行注释
 */</span></pre>
<hr>
<h2>标识符</h2>
<p>标识符用来命名变量、类型等程序实体。一个标识符实际上就是一个或是多个字母(A~Z和a~z)数字(0~9)、下划线_组成的序列，但是第一个字符必须是字母或下划线而不能是数字。</p>
<p>以下是有效的标识符：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">mahesh   kumar   abc   move_name   a_123
myname50   _temp   j   a23b9   retVal</span></pre>
<p>以下是无效的标识符：</p>
<ul>
<li>1ab（以数字开头）</li>
<li>case（Go 语言的关键字）</li>
<li>a+b（运算符是不允许的）</li>
</ul>
<hr><h2>字符串连接</h2>
<p>Go 语言的字符串连接可以通过 <span class="marked">+</span> 实现：</p>
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Println<span style="color: #339933;">(</span><span style="color: #cc66cc;">"Google"</span> <span style="color: #339933;">+</span> <span style="color: #cc66cc;">"Runoob"</span><span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>
<p>以上实例输出结果为：</p>
<pre class="prettyprint prettyprinted" style=""><span class="typ">GoogleRunoob</span></pre>
<hr>
<h2>关键字</h2>
<p>下面列举了 Go 代码中会使用到的 25 个关键字或保留字：</p>


<table class="reference">
<tbody><tr>
<td style="width:25%">break</td><td style="width:25%">default</td><td style="width:25%">func</td><td style="width:25%">interface</td><td style="width:25%">select</td></tr>
<tr><td>case</td><td>defer</td><td>go</td><td>map</td><td>struct</td></tr>
<tr><td>chan</td><td>else</td><td>goto</td><td>package</td><td>switch</td></tr>
<tr><td>const</td><td>fallthrough</td><td>if</td><td>range</td><td>type</td></tr>
<tr><td>continue</td><td>for</td><td>import</td><td>return</td><td>var</td></tr>
</tbody></table>

<p>除了以上介绍的这些关键字，Go 语言还有 36 个预定义标识符：</p>
<table class="reference">
  <tbody><tr>
    <td>append</td>
    <td>bool</td>
    <td>byte</td>
    <td>cap</td>
    <td>close</td>
    <td>complex</td>
    <td>complex64</td>
    <td>complex128</td>
    <td>uint16</td>
  </tr>
  <tr>
    <td>copy</td>
    <td>false</td>
    <td>float32</td>
    <td>float64</td>
    <td>imag</td>
    <td>int</td>
    <td>int8</td>
    <td>int16</td>
    <td>uint32</td>
  </tr>
  <tr>
    <td>int32</td>
    <td>int64</td>
    <td>iota</td>
    <td>len</td>
    <td>make</td>
    <td>new</td>
    <td>nil</td>
    <td>panic</td>
    <td>uint64</td>
  </tr>
  <tr>
    <td>print</td>
    <td>println</td>
    <td>real</td>
    <td>recover</td>
    <td>string</td>
    <td>true</td>
    <td>uint</td>
    <td>uint8</td>
    <td>uintptr</td>
  </tr>
</tbody></table>
<p>
程序一般由关键字、常量、变量、运算符、类型和函数组成。
</p><p>
程序中可能会使用到这些分隔符：括号 ()，中括号 [] 和大括号 {}。
</p><p>
程序中可能会使用到这些标点符号：.、,、;、: 和 …。</p>
<hr>
<h2>Go 语言的空格</h2>
<p>Go 语言中变量的声明必须使用空格隔开，如：</p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> age </span><span class="kwd">int</span><span class="pun">;</span></pre>

<p>语句中适当使用空格能让程序更易阅读。</p>
<p>无空格：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">fruit</span><span class="pun">=</span><span class="pln">apples</span><span class="pun">+</span><span class="pln">oranges</span><span class="pun">;</span></pre>
<p>在变量与运算符间加入空格，程序看起来更加美观，如：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">fruit </span><span class="pun">=</span><span class="pln"> apples </span><span class="pun">+</span><span class="pln"> oranges</span><span class="pun">;</span><span class="pln"> </span></pre>
<hr>
<h2>格式化字符串</h2>
<p>Go 语言中使用 <span class="marked">fmt.Sprintf</span> 格式化字符串并赋值给新串：</p>
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #339933;">(</span><br>
&nbsp; &nbsp; <span style="color: #cc66cc;">"fmt"</span><br>
<span style="color: #339933;">)</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">// %d 表示整型数字，%s 表示字符串</span><br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">var</span> stockcode<span style="color: #339933;">=</span><span style="color: #cc66cc;">123</span><br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">var</span> enddate<span style="color: #339933;">=</span><span style="color: #cc66cc;">"2020-12-31"</span><br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">var</span> url<span style="color: #339933;">=</span><span style="color: #cc66cc;">"Code=%d&amp;endDate=%s"</span><br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">var</span> target_url<span style="color: #339933;">=</span>fmt<span style="color: #339933;">.</span>Sprintf<span style="color: #339933;">(</span>url<span style="color: #339933;">,</span>stockcode<span style="color: #339933;">,</span>enddate<span style="color: #339933;">)</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Println<span style="color: #339933;">(</span>target_url<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>
<p>输出结果为：</p>
<pre class="prettyprint prettyprinted" style=""><span class="typ">Code</span><span class="pun">=</span><span class="lit">123</span><span class="pun">&amp;</span><span class="pln">endDate</span><span class="pun">=</span><span class="lit">2020</span><span class="pun">-</span><span class="lit">12</span><span class="pun">-</span><span class="lit">31</span></pre>

