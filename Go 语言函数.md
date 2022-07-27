# Go 语言函数

<p>函数是基本的代码块，用于执行一个任务。</p>

<p>Go 语言最少有个 main() 函数。</p>

<p>你可以通过函数来划分不同功能，逻辑上每个函数执行的是指定的任务。</p>

<p>函数声明告诉了编译器函数的名称，返回类型，和参数。</p>

<p>Go 语言标准库提供了多种可动用的内置的函数。例如，len() 函数可以接受不同类型参数并返回该类型的长度。如果我们传入的是字符串则返回字符串的长度，如果传入的是数组，则返回数组中包含的元素个数。</p>

<hr>

<h2>函数定义</h2>

<p>Go 语言函数定义格式如下：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">func function_name</span><span class="pun">(</span><span class="pln"> </span><span class="pun">[</span><span class="pln">parameter list</span><span class="pun">]</span><span class="pln"> </span><span class="pun">)</span><span class="pln"> </span><span class="pun">[</span><span class="pln">return_types</span><span class="pun">]</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
   </span><span class="pun">函数体</span><span class="pln">
</span><span class="pun">}</span></pre>

<p>函数定义解析：</p>

<ul>
<li>func：函数由 func 开始声明</li>
<li>function_name：函数名称，参数列表和返回值类型构成了函数签名。</li>
<li>parameter list：参数列表，参数就像一个占位符，当函数被调用时，你可以将值传递给参数，这个值被称为实际参数。参数列表指定的是参数类型、顺序、及参数个数。参数是可选的，也就是说函数也可以不包含参数。</li>
<li>return_types：返回类型，函数返回一列值。return_types 是该列值的数据类型。有些功能不需要返回值，这种情况下 return_types 不是必须的。</li>
<li>函数体：函数定义的代码集合。</li>
</ul>


<h3>实例</h3>

<p>以下实例为 max() 函数的代码，该函数传入两个整型参数 num1 和 num2，并返回这两个参数的最大值：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #666666; font-style: italic;">/* 函数返回两个数的最大值 */</span><br>
<span style="color: #993333;">func</span> max<span style="color: #339933;">(</span>num1<span style="color: #339933;">,</span> num2 <span style="color: #993333;">int</span><span style="color: #339933;">)</span> <span style="color: #993333;">int</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 声明局部变量 */</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> result <span style="color: #993333;">int</span><br>
<br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">if</span> <span style="color: #339933;">(</span>num1 &gt; num2<span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; result <span style="color: #339933;">=</span> num1<br>
&nbsp; &nbsp;<span style="color: #339933;">}</span> <span style="color: #b1b100; font-weight: bold;">else</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; result <span style="color: #339933;">=</span> num2<br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">return</span> result <br>
<span style="color: #339933;">}</span><br>
</div></div>

<h2>函数调用</h2>

<p>当创建函数时，你定义了函数需要做什么，通过调用该函数来执行指定任务。</p>

<p>调用函数，向函数传递参数，并返回值，例如：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 定义局部变量 */</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> a <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">100</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> b <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">200</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> ret <span style="color: #993333;">int</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 调用函数并返回最大值 */</span><br>
&nbsp; &nbsp;ret <span style="color: #339933;">=</span> max<span style="color: #339933;">(</span>a<span style="color: #339933;">,</span> b<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span> <span style="color: #cc66cc;">"最大值是 : %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> ret <span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
<br>
<span style="color: #666666; font-style: italic;">/* 函数返回两个数的最大值 */</span><br>
<span style="color: #993333;">func</span> max<span style="color: #339933;">(</span>num1<span style="color: #339933;">,</span> num2 <span style="color: #993333;">int</span><span style="color: #339933;">)</span> <span style="color: #993333;">int</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 定义局部变量 */</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> result <span style="color: #993333;">int</span><br>
<br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">if</span> <span style="color: #339933;">(</span>num1 &gt; num2<span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; result <span style="color: #339933;">=</span> num1<br>
&nbsp; &nbsp;<span style="color: #339933;">}</span> <span style="color: #b1b100; font-weight: bold;">else</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; result <span style="color: #339933;">=</span> num2<br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">return</span> result <br>
<span style="color: #339933;">}</span><br>
</div></div>

<p>以上实例在 main() 函数中调用 max（）函数，执行结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pun">最大值是</span><span class="pln"> </span><span class="pun">:</span><span class="pln"> </span><span class="lit">200</span></pre>
<hr>
<h2>函数返回多个值</h2>

<p>Go 函数可以返回多个值，例如：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> swap<span style="color: #339933;">(</span>x<span style="color: #339933;">,</span> y <span style="color: #993333;">string</span><span style="color: #339933;">)</span> <span style="color: #339933;">(</span><span style="color: #993333;">string</span><span style="color: #339933;">,</span> <span style="color: #993333;">string</span><span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">return</span> y<span style="color: #339933;">,</span> x<br>
<span style="color: #339933;">}</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;a<span style="color: #339933;">,</span> b <span style="color: #339933;">:=</span> swap<span style="color: #339933;">(</span><span style="color: #cc66cc;">"Google"</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">"Runoob"</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span>a<span style="color: #339933;">,</span> b<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>

<p>以上实例执行结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="typ">Runoob</span><span class="pln"> </span><span class="typ">Google</span></pre>
<hr>
<h2>函数参数</h2>

<p>函数如果使用参数，该变量可称为函数的形参。</p>

<p>形参就像定义在函数体内的局部变量。</p>

<p>调用函数，可以通过两种方式来传递参数：</p>

<table class="reference">
<thead>
<tr>
<th>传递类型   </th>
<th> 描述</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href="go-function-call-by-value.html">值传递</a> </td>
<td>值传递是指在调用函数时将实际参数复制一份传递到函数中，这样在函数中如果对参数进行修改，将不会影响到实际参数。</td>
</tr>
<tr>
<td><a href="go-function-call-by-reference.html">引用传递</a></td>
<td>引用传递是指在调用函数时将实际参数的地址传递到函数中，那么在函数中对参数所进行的修改，将影响到实际参数。</td>
</tr>
</tbody>
</table>


<p>默认情况下，Go 语言使用的是值传递，即在调用过程中不会影响到实际参数。</p>
<hr>
<h2>函数用法</h2>

<table class="reference">
<thead>
<tr>
<th>函数用法 </th>
<th> 描述</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href="go-function-as-values.html">函数作为另外一个函数的实参</a></td>
<td> 函数定义后可作为另外一个函数的实参数传入</td>
</tr>
<tr>
<td><a href="go-function-closures.html">闭包</a></td>
<td> 闭包是匿名函数，可在动态编程中使用</td>
</tr>
<tr>
<td><a href="go-method.html">方法</a> </td>
<td> 方法就是一个包含了接受者的函数</td>
</tr>
</tbody>
</table>	
