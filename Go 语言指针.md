
		
# Go 语言指针

<p>Go 语言中指针是很容易学习的，Go 语言中使用指针可以更简单的执行一些任务。</p>

<p>接下来让我们来一步步学习 Go 语言指针。</p>

<p>我们都知道，变量是一种使用方便的占位符，用于引用计算机内存地址。</p>

<p>Go 语言的取地址符是 &amp;，放到一个变量前使用就会返回相应变量的内存地址。</p>

<p>以下实例演示了变量在内存中地址：</p>

<div class="example"><h2 class="example">实例</h2><div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> a <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">10</span> &nbsp; <br>
<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"变量的地址: %x<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> <span style="color: #339933;">&amp;</span>a &nbsp;<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>

<p>执行以上代码输出结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pun">变量的地址:</span><span class="pln"> </span><span class="lit">20818a220</span></pre>

<p>现在我们已经了解了什么是内存地址和如何去访问它。接下来我们将具体介绍指针。</p>

<hr>

<h2>什么是指针</h2>

<p>一个指针变量指向了一个值的内存地址。</p>

<p>类似于变量和常量，在使用指针前你需要声明指针。指针声明格式如下：</p>

<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> var_name </span><span class="pun">*</span><span class="kwd">var</span><span class="pun">-</span><span class="pln">type</span></pre>

<p>var-type 为指针类型，var_name 为指针变量名，* 号用于指定变量是作为一个指针。以下是有效的指针声明：</p>

<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> ip </span><span class="pun">*</span><span class="kwd">int</span><span class="pln">        </span><span class="com">/* 指向整型*/</span><span class="pln">
</span><span class="kwd">var</span><span class="pln"> fp </span><span class="pun">*</span><span class="pln">float32    </span><span class="com">/* 指向浮点型 */</span></pre>

<p>本例中这是一个指向 int 和 float32 的指针。</p>

<hr>

<h2>如何使用指针</h2>

<p>指针使用流程：</p>

<ul>
<li>定义指针变量。</li>
<li>为指针变量赋值。</li>
<li>访问指针变量中指向地址的值。</li>
</ul>


<p>在指针类型前面加上 * 号（前缀）来获取指针所指向的内容。</p>
<div class="example"><h2 class="example">实例</h2><div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> a <span style="color: #993333;">int</span><span style="color: #339933;">=</span> <span style="color: #cc66cc;">20</span> &nbsp; <span style="color: #666666; font-style: italic;">/* 声明实际变量 */</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> ip <span style="color: #339933;">*</span><span style="color: #993333;">int</span> &nbsp; &nbsp; &nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 声明指针变量 */</span><br>
<br>
&nbsp; &nbsp;ip <span style="color: #339933;">=</span> <span style="color: #339933;">&amp;</span>a &nbsp;<span style="color: #666666; font-style: italic;">/* 指针变量的存储地址 */</span><br>
<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"a 变量的地址是: %x<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> <span style="color: #339933;">&amp;</span>a &nbsp;<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 指针变量的存储地址 */</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"ip 变量储存的指针地址: %x<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> ip <span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 使用指针访问值 */</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"*ip 变量的值: %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> <span style="color: #339933;">*</span>ip <span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>

<p>以上实例执行输出结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">a </span><span class="pun">变量的地址是:</span><span class="pln"> </span><span class="lit">20818a220</span><span class="pln">
ip </span><span class="pun">变量储存的指针地址:</span><span class="pln"> </span><span class="lit">20818a220</span><span class="pln">
</span><span class="pun">*</span><span class="pln">ip </span><span class="pun">变量的值:</span><span class="pln"> </span><span class="lit">20</span></pre>

<hr>

<h2>Go 空指针</h2>

<p>当一个指针被定义后没有分配到任何变量时，它的值为 nil。</p>

<p>nil 指针也称为空指针。</p>

<p>nil在概念上和其它语言的null、None、nil、NULL一样，都指代零值或空值。</p>

<p>一个指针变量通常缩写为 ptr。</p>

<p>查看以下实例：</p>
<div class="example"><h2 class="example">实例</h2><div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> &nbsp;ptr <span style="color: #339933;">*</span><span style="color: #993333;">int</span><br>
<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"ptr 的值为 : %x<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> ptr &nbsp;<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>


<p>以上实例输出结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">ptr </span><span class="pun">的值为</span><span class="pln"> </span><span class="pun">:</span><span class="pln"> </span><span class="lit">0</span></pre>

<p>空指针判断：</p>

<pre class="prettyprint prettyprinted" style=""><span class="kwd">if</span><span class="pun">(</span><span class="pln">ptr </span><span class="pun">!=</span><span class="pln"> </span><span class="kwd">nil</span><span class="pun">)</span><span class="pln">     </span><span class="com">/* ptr 不是空指针 */</span><span class="pln">
</span><span class="kwd">if</span><span class="pun">(</span><span class="pln">ptr </span><span class="pun">==</span><span class="pln"> </span><span class="kwd">nil</span><span class="pun">)</span><span class="pln">    </span><span class="com">/* ptr 是空指针 */</span></pre>

<hr>

<h2>Go指针更多内容</h2>

<p>接下来我们将为大家介绍Go语言中更多的指针应用：</p>

<table class="reference">
<thead>
<tr>
<th>内容 </th>
<th> 描述</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href="go-array-of-pointers.html">Go 指针数组</a> </td>
<td> 你可以定义一个指针数组来存储地址</td>
</tr>
<tr>
<td><a href="go-pointer-to-pointer.html">Go 指向指针的指针</a></td>
<td> Go 支持指向指针的指针</td>
</tr>
<tr>
<td><a href="go-passing-pointers-to-functions.html">Go 向函数传递指针参数</a> </td>
<td>通过引用或地址传参，在函数调用时可以改变其值</td>
</tr>
</tbody>
</table>	
