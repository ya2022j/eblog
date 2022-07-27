
		
# Go 语言数组


<p>Go 语言提供了数组类型的数据结构。</p>

<p>数组是具有相同唯一类型的一组已编号且长度固定的数据项序列，这种类型可以是任意的原始类型例如整型、字符串或者自定义类型。</p>

<p>相对于去声明 <strong>number0, number1, ..., number99</strong> 的变量，使用数组形式 <strong>numbers[0], numbers[1] ..., numbers[99]</strong> 更加方便且易于扩展。</p>

<p>数组元素可以通过索引（位置）来读取（或者修改），索引从 0 开始，第一个元素索引为 0，第二个索引为 1，以此类推。</p>



<hr>

<h2>声明数组</h2>

<p>Go 语言数组声明需要指定元素类型及元素个数，语法格式如下：</p>

<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> variable_name </span><span class="pun">[</span><span class="pln">SIZE</span><span class="pun">]</span><span class="pln"> variable_type</span></pre>

<p>以上为一维数组的定义方式。例如以下定义了数组 balance 长度为 10 类型为 float32：</p>

<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> balance </span><span class="pun">[</span><span class="lit">10</span><span class="pun">]</span><span class="pln"> float32</span></pre>

<hr>

<h2>初始化数组</h2>

<p>以下演示了数组初始化：</p>

<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> balance </span><span class="pun">=</span><span class="pln"> </span><span class="pun">[</span><span class="lit">5</span><span class="pun">]</span><span class="pln">float32</span><span class="pun">{</span><span class="lit">1000.0</span><span class="pun">,</span><span class="pln"> </span><span class="lit">2.0</span><span class="pun">,</span><span class="pln"> </span><span class="lit">3.4</span><span class="pun">,</span><span class="pln"> </span><span class="lit">7.0</span><span class="pun">,</span><span class="pln"> </span><span class="lit">50.0</span><span class="pun">}</span></pre>
<p>我们也可以通过字面量在声明数组的同时快速初始化数组：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">balance </span><span class="pun">:=</span><span class="pln"> </span><span class="pun">[</span><span class="lit">5</span><span class="pun">]</span><span class="pln">float32</span><span class="pun">{</span><span class="lit">1000.0</span><span class="pun">,</span><span class="pln"> </span><span class="lit">2.0</span><span class="pun">,</span><span class="pln"> </span><span class="lit">3.4</span><span class="pun">,</span><span class="pln"> </span><span class="lit">7.0</span><span class="pun">,</span><span class="pln"> </span><span class="lit">50.0</span><span class="pun">}</span></pre>
<p>如果数组长度不确定，可以使用 <span class="marked">...</span> 代替数组的长度，编译器会根据元素个数自行推断数组的长度：</p>

<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> balance </span><span class="pun">=</span><span class="pln"> </span><span class="pun">[...]</span><span class="pln">float32</span><span class="pun">{</span><span class="lit">1000.0</span><span class="pun">,</span><span class="pln"> </span><span class="lit">2.0</span><span class="pun">,</span><span class="pln"> </span><span class="lit">3.4</span><span class="pun">,</span><span class="pln"> </span><span class="lit">7.0</span><span class="pun">,</span><span class="pln"> </span><span class="lit">50.0</span><span class="pun">}</span><span class="pln">
</span><span class="pun">或</span><span class="pln">
balance </span><span class="pun">:=</span><span class="pln"> </span><span class="pun">[...]</span><span class="pln">float32</span><span class="pun">{</span><span class="lit">1000.0</span><span class="pun">,</span><span class="pln"> </span><span class="lit">2.0</span><span class="pun">,</span><span class="pln"> </span><span class="lit">3.4</span><span class="pun">,</span><span class="pln"> </span><span class="lit">7.0</span><span class="pun">,</span><span class="pln"> </span><span class="lit">50.0</span><span class="pun">}</span></pre>
<p>如果设置了数组的长度，我们还可以通过指定下标来初始化元素：</p>

<pre class="prettyprint prettyprinted" style=""><span class="com">//  将索引为 1 和 3 的元素初始化</span><span class="pln">
balance </span><span class="pun">:=</span><span class="pln"> </span><span class="pun">[</span><span class="lit">5</span><span class="pun">]</span><span class="pln">float32</span><span class="pun">{</span><span class="lit">1</span><span class="pun">:</span><span class="lit">2.0</span><span class="pun">,</span><span class="lit">3</span><span class="pun">:</span><span class="lit">7.0</span><span class="pun">}</span></pre>
<p> 初始化数组中 <span class="marked">{}</span> 中的元素个数不能大于 <span class="marked">[]</span> 中的数字。</p>

<p> 如果忽略 <span class="marked">[]</span> 中的数字不设置数组大小，Go 语言会根据元素的个数来设置数组的大小：</p>




<pre class="prettyprint prettyprinted" style=""><span class="pln"> balance</span><span class="pun">[</span><span class="lit">4</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">50.0</span></pre>

<p>以上实例读取了第五个元素。数组元素可以通过索引（位置）来读取（或者修改），索引从 0 开始，第一个元素索引为 0，第二个索引为 1，以此类推。</p>

<p> <img src="//www.runoob.com/wp-content/uploads/2015/06/array_presentation.jpg" alt=""></p>

<hr>

<h2>访问数组元素</h2>

<p>数组元素可以通过索引（位置）来读取。格式为数组名后加中括号，中括号中为索引的值。例如：</p>

<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> salary float32 </span><span class="pun">=</span><span class="pln"> balance</span><span class="pun">[</span><span class="lit">9</span><span class="pun">]</span></pre>

<p>以上实例读取了数组 balance 第 10 个元素的值。</p>

<p>以下演示了数组完整操作（声明、赋值、访问）的实例：</p>

<div class="example"><h2 class="example">实例 1</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> n <span style="color: #339933;">[</span><span style="color: #cc66cc;">10</span><span style="color: #339933;">]</span><span style="color: #993333;">int</span> <span style="color: #666666; font-style: italic;">/* n 是一个长度为 10 的数组 */</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> <span style="">i</span><span style="color: #339933;">,</span>j <span style="color: #993333;">int</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 为数组 n 初始化元素 */</span> &nbsp; &nbsp; &nbsp; &nbsp; <br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">for</span> <span style="">i</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">0</span><span style="color: #339933;">;</span> <span style="">i</span> &lt; <span style="color: #cc66cc;">10</span><span style="color: #339933;">;</span> <span style="">i</span><span style="color: #339933;">++</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; n<span style="color: #339933;">[</span><span style="">i</span><span style="color: #339933;">]</span> <span style="color: #339933;">=</span> <span style="">i</span> <span style="color: #339933;">+</span> <span style="color: #cc66cc;">100</span> <span style="color: #666666; font-style: italic;">/* 设置元素为 i + 100 */</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 输出每个数组元素的值 */</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">for</span> j <span style="color: #339933;">=</span> <span style="color: #cc66cc;">0</span><span style="color: #339933;">;</span> j &lt; <span style="color: #cc66cc;">10</span><span style="color: #339933;">;</span> j<span style="color: #339933;">++</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"Element[%d] = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> j<span style="color: #339933;">,</span> n<span style="color: #339933;">[</span>j<span style="color: #339933;">]</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
<span style="color: #339933;">}</span><br>
</div></div>


<p>以上实例执行结果如下：</p>

<pre class="prettyprint prettyprinted" style=""><span class="typ">Element</span><span class="pun">[</span><span class="lit">0</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">100</span><span class="pln">
</span><span class="typ">Element</span><span class="pun">[</span><span class="lit">1</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">101</span><span class="pln">
</span><span class="typ">Element</span><span class="pun">[</span><span class="lit">2</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">102</span><span class="pln">
</span><span class="typ">Element</span><span class="pun">[</span><span class="lit">3</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">103</span><span class="pln">
</span><span class="typ">Element</span><span class="pun">[</span><span class="lit">4</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">104</span><span class="pln">
</span><span class="typ">Element</span><span class="pun">[</span><span class="lit">5</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">105</span><span class="pln">
</span><span class="typ">Element</span><span class="pun">[</span><span class="lit">6</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">106</span><span class="pln">
</span><span class="typ">Element</span><span class="pun">[</span><span class="lit">7</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">107</span><span class="pln">
</span><span class="typ">Element</span><span class="pun">[</span><span class="lit">8</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">108</span><span class="pln">
</span><span class="typ">Element</span><span class="pun">[</span><span class="lit">9</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">109</span></pre>
<div class="example"><h2 class="example">实例 2</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> <span style="">i</span><span style="color: #339933;">,</span>j<span style="color: #339933;">,</span>k <span style="color: #993333;">int</span><br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">// 声明数组的同时快速初始化数组</span><br>
&nbsp; &nbsp;balance <span style="color: #339933;">:=</span> <span style="color: #339933;">[</span><span style="color: #cc66cc;">5</span><span style="color: #339933;">]</span><span style="color: #993333;">float32</span><span style="color: #339933;">{</span><span style="color: #cc66cc;">1000</span><span style="color: #339933;">.</span><span style="color: #cc66cc;">0</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">2</span><span style="color: #339933;">.</span><span style="color: #cc66cc;">0</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">3</span><span style="color: #339933;">.</span><span style="color: #cc66cc;">4</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">7</span><span style="color: #339933;">.</span><span style="color: #cc66cc;">0</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">50</span><span style="color: #339933;">.</span><span style="color: #cc66cc;">0</span><span style="color: #339933;">}</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 输出数组元素 */</span> &nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #000000; font-weight: bold;">...</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">for</span> <span style="">i</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">0</span><span style="color: #339933;">;</span> <span style="">i</span> &lt; <span style="color: #cc66cc;">5</span><span style="color: #339933;">;</span> <span style="">i</span><span style="color: #339933;">++</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"balance[%d] = %f<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> <span style="">i</span><span style="color: #339933;">,</span> balance<span style="color: #339933;">[</span><span style="">i</span><span style="color: #339933;">]</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
&nbsp; &nbsp;<br>
&nbsp; &nbsp;balance2 <span style="color: #339933;">:=</span> <span style="color: #339933;">[</span><span style="color: #000000; font-weight: bold;">...</span><span style="color: #339933;">]</span><span style="color: #993333;">float32</span><span style="color: #339933;">{</span><span style="color: #cc66cc;">1000</span><span style="color: #339933;">.</span><span style="color: #cc66cc;">0</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">2</span><span style="color: #339933;">.</span><span style="color: #cc66cc;">0</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">3</span><span style="color: #339933;">.</span><span style="color: #cc66cc;">4</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">7</span><span style="color: #339933;">.</span><span style="color: #cc66cc;">0</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">50</span><span style="color: #339933;">.</span><span style="color: #cc66cc;">0</span><span style="color: #339933;">}</span><br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 输出每个数组元素的值 */</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">for</span> j <span style="color: #339933;">=</span> <span style="color: #cc66cc;">0</span><span style="color: #339933;">;</span> j &lt; <span style="color: #cc66cc;">5</span><span style="color: #339933;">;</span> j<span style="color: #339933;">++</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"balance2[%d] = %f<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> j<span style="color: #339933;">,</span> balance2<span style="color: #339933;">[</span>j<span style="color: #339933;">]</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">// &nbsp;将索引为 1 和 3 的元素初始化</span><br>
&nbsp; &nbsp;balance3 <span style="color: #339933;">:=</span> <span style="color: #339933;">[</span><span style="color: #cc66cc;">5</span><span style="color: #339933;">]</span><span style="color: #993333;">float32</span><span style="color: #339933;">{</span><span style="color: #cc66cc;">1</span><span style="color: #339933;">:</span><span style="color: #cc66cc;">2</span><span style="color: #339933;">.</span><span style="color: #cc66cc;">0</span><span style="color: #339933;">,</span><span style="color: #cc66cc;">3</span><span style="color: #339933;">:</span><span style="color: #cc66cc;">7</span><span style="color: #339933;">.</span><span style="color: #cc66cc;">0</span><span style="color: #339933;">}</span> &nbsp;<br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">for</span> k <span style="color: #339933;">=</span> <span style="color: #cc66cc;">0</span><span style="color: #339933;">;</span> k &lt; <span style="color: #cc66cc;">5</span><span style="color: #339933;">;</span> k<span style="color: #339933;">++</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"balance3[%d] = %f<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> k<span style="color: #339933;">,</span> balance3<span style="color: #339933;">[</span>k<span style="color: #339933;">]</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
<span style="color: #339933;">}</span><br>
</div></div>
<p>以上实例执行结果如下：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">balance</span><span class="pun">[</span><span class="lit">0</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">1000.000000</span><span class="pln">
balance</span><span class="pun">[</span><span class="lit">1</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">2.000000</span><span class="pln">
balance</span><span class="pun">[</span><span class="lit">2</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">3.400000</span><span class="pln">
balance</span><span class="pun">[</span><span class="lit">3</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">7.000000</span><span class="pln">
balance</span><span class="pun">[</span><span class="lit">4</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">50.000000</span><span class="pln">
balance2</span><span class="pun">[</span><span class="lit">0</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">1000.000000</span><span class="pln">
balance2</span><span class="pun">[</span><span class="lit">1</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">2.000000</span><span class="pln">
balance2</span><span class="pun">[</span><span class="lit">2</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">3.400000</span><span class="pln">
balance2</span><span class="pun">[</span><span class="lit">3</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">7.000000</span><span class="pln">
balance2</span><span class="pun">[</span><span class="lit">4</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">50.000000</span><span class="pln">
balance3</span><span class="pun">[</span><span class="lit">0</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">0.000000</span><span class="pln">
balance3</span><span class="pun">[</span><span class="lit">1</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">2.000000</span><span class="pln">
balance3</span><span class="pun">[</span><span class="lit">2</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">0.000000</span><span class="pln">
balance3</span><span class="pun">[</span><span class="lit">3</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">7.000000</span><span class="pln">
balance3</span><span class="pun">[</span><span class="lit">4</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">0.000000</span></pre>
<hr>

<h2>更多内容</h2>

<p>数组对 Go 语言来说是非常重要的，以下我们将介绍数组更多的内容：</p>

<table class="reference">
<thead>
<tr>
<th>内容 </th>
<th> 描述</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href="go-multi-dimensional-arrays.html">多维数组</a></td>
<td>Go 语言支持多维数组，最简单的多维数组是二维数组</td>
</tr>
<tr>
<td><a href="go-passing-arrays-to-functions.html">向函数传递数组</a></td>
<td>你可以向函数传递数组参数</td>
</tr>
</tbody>
</table>		
