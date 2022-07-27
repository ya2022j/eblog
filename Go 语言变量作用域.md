
		
# Go 语言变量作用域

<p>作用域为已声明标识符所表示的常量、类型、变量、函数或包在源代码中的作用范围。</p>

<p>Go 语言中变量可以在三个地方声明：</p>

<ul>
<li>函数内定义的变量称为局部变量</li>
<li>函数外定义的变量称为全局变量</li>
<li>函数定义中的变量称为形式参数</li>
</ul>


<p>接下来让我们具体了解局部变量、全局变量和形式参数。</p>

<hr>

<h2>局部变量</h2>

<p>在函数体内声明的变量称之为局部变量，它们的作用域只在函数体内，参数和返回值变量也是局部变量。</p>

<p>以下实例中 main() 函数使用了局部变量 a, b, c：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 声明局部变量 */</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> a<span style="color: #339933;">,</span> b<span style="color: #339933;">,</span> c <span style="color: #993333;">int</span> <br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 初始化参数 */</span><br>
&nbsp; &nbsp;a <span style="color: #339933;">=</span> <span style="color: #cc66cc;">10</span><br>
&nbsp; &nbsp;b <span style="color: #339933;">=</span> <span style="color: #cc66cc;">20</span><br>
&nbsp; &nbsp;c <span style="color: #339933;">=</span> a <span style="color: #339933;">+</span> b<br>
<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf <span style="color: #339933;">(</span><span style="color: #cc66cc;">"结果： a = %d, b = %d and c = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> a<span style="color: #339933;">,</span> b<span style="color: #339933;">,</span> c<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>


<p>以上实例执行输出结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pun">结果：</span><span class="pln"> a </span><span class="pun">=</span><span class="pln"> </span><span class="lit">10</span><span class="pun">,</span><span class="pln"> b </span><span class="pun">=</span><span class="pln"> </span><span class="lit">20</span><span class="pln"> </span><span class="kwd">and</span><span class="pln"> c </span><span class="pun">=</span><span class="pln"> </span><span class="lit">30</span></pre>

<hr>

<h2>全局变量</h2>

<p>在函数体外声明的变量称之为全局变量，全局变量可以在整个包甚至外部包（被导出后）使用。</p>

<p>全局变量可以在任何函数中使用，以下实例演示了如何使用全局变量：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #666666; font-style: italic;">/* 声明全局变量 */</span><br>
<span style="color: #b1b100; font-weight: bold;">var</span> g <span style="color: #993333;">int</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 声明局部变量 */</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> a<span style="color: #339933;">,</span> b <span style="color: #993333;">int</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 初始化参数 */</span><br>
&nbsp; &nbsp;a <span style="color: #339933;">=</span> <span style="color: #cc66cc;">10</span><br>
&nbsp; &nbsp;b <span style="color: #339933;">=</span> <span style="color: #cc66cc;">20</span><br>
&nbsp; &nbsp;g <span style="color: #339933;">=</span> a <span style="color: #339933;">+</span> b<br>
<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"结果： a = %d, b = %d and g = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> a<span style="color: #339933;">,</span> b<span style="color: #339933;">,</span> g<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>

<p>以上实例执行输出结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pun">结果：</span><span class="pln"> a </span><span class="pun">=</span><span class="pln"> </span><span class="lit">10</span><span class="pun">,</span><span class="pln"> b </span><span class="pun">=</span><span class="pln"> </span><span class="lit">20</span><span class="pln"> </span><span class="kwd">and</span><span class="pln"> g </span><span class="pun">=</span><span class="pln"> </span><span class="lit">30</span></pre>

<p>Go 语言程序中全局变量与局部变量名称可以相同，但是函数内的局部变量会被优先考虑。实例如下：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #666666; font-style: italic;">/* 声明全局变量 */</span><br>
<span style="color: #b1b100; font-weight: bold;">var</span> g <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">20</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 声明局部变量 */</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> g <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">10</span><br>
<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf <span style="color: #339933;">(</span><span style="color: #cc66cc;">"结果： g = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> &nbsp;g<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>


<p>以上实例执行输出结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pun">结果：</span><span class="pln"> g </span><span class="pun">=</span><span class="pln"> </span><span class="lit">10</span></pre>

<hr>

<h2>形式参数</h2>

<p>形式参数会作为函数的局部变量来使用。实例如下：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #666666; font-style: italic;">/* 声明全局变量 */</span><br>
<span style="color: #b1b100; font-weight: bold;">var</span> a <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">20</span><span style="color: #339933;">;</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* main 函数中声明局部变量 */</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> a <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">10</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> b <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">20</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> c <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">0</span><br>
<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"main()函数中 a = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> &nbsp;a<span style="color: #339933;">);</span><br>
&nbsp; &nbsp;c <span style="color: #339933;">=</span> sum<span style="color: #339933;">(</span> a<span style="color: #339933;">,</span> b<span style="color: #339933;">);</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"main()函数中 c = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> &nbsp;c<span style="color: #339933;">);</span><br>
<span style="color: #339933;">}</span><br>
<br>
<span style="color: #666666; font-style: italic;">/* 函数定义-两数相加 */</span><br>
<span style="color: #993333;">func</span> sum<span style="color: #339933;">(</span>a<span style="color: #339933;">,</span> b <span style="color: #993333;">int</span><span style="color: #339933;">)</span> <span style="color: #993333;">int</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"sum() 函数中 a = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> &nbsp;a<span style="color: #339933;">);</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"sum() 函数中 b = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> &nbsp;b<span style="color: #339933;">);</span><br>
<br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">return</span> a <span style="color: #339933;">+</span> b<span style="color: #339933;">;</span><br>
<span style="color: #339933;">}</span><br>
</div></div>


<p>以上实例执行输出结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">main</span><span class="pun">()函数中</span><span class="pln"> a </span><span class="pun">=</span><span class="pln"> </span><span class="lit">10</span><span class="pln">
sum</span><span class="pun">()</span><span class="pln"> </span><span class="pun">函数中</span><span class="pln"> a </span><span class="pun">=</span><span class="pln"> </span><span class="lit">10</span><span class="pln">
sum</span><span class="pun">()</span><span class="pln"> </span><span class="pun">函数中</span><span class="pln"> b </span><span class="pun">=</span><span class="pln"> </span><span class="lit">20</span><span class="pln">
main</span><span class="pun">()函数中</span><span class="pln"> c </span><span class="pun">=</span><span class="pln"> </span><span class="lit">30</span></pre>

<hr>

<h2>初始化局部和全局变量</h2>

<p>不同类型的局部和全局变量默认值为：</p>

<table class="reference">
<thead>
<tr>
<th>数据类型 </th>
<th> 初始化默认值</th>
</tr>
</thead>
<tbody>
<tr>
<td>int </td>
<td> 0</td>
</tr>
<tr>
<td>float32 </td>
<td> 0</td>
</tr>
<tr>
<td>pointer </td>
<td> nil</td>
</tr>
</tbody>
</table>
			

		