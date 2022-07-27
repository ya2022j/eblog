

# Go 语言运算符
<p>运算符用于在程序运行时执行数学或逻辑运算。</p>
<p>Go 语言内置的运算符有：</p>
<ul>
<li>算术运算符</li>
<li>关系运算符</li>
<li>逻辑运算符</li>
<li>位运算符</li>
<li>赋值运算符</li>
<li>其他运算符</li>
</ul>
<p>接下来让我们来详细看看各个运算符的介绍。</p>
<hr>
<h2>算术运算符</h2>
<p>下表列出了所有Go语言的算术运算符。假定 A 值为 10，B 值为 20。</p>
<table class="reference">
<tbody><tr><th style="width:10%">运算符</th><th style="width:55%;">描述</th><th>实例</th></tr>
<tr><td>+</td><td>相加</td><td> A + B 输出结果 30</td></tr>
<tr><td>-</td><td>相减</td><td> A - B 输出结果 -10</td></tr>
<tr><td>*</td><td>相乘</td><td> A * B 输出结果 200</td></tr>
<tr><td>/</td><td>相除</td><td> B / A 输出结果 2</td></tr>
<tr><td>%</td><td>求余</td><td> B % A 输出结果 0</td></tr>
<tr><td>++</td><td>自增</td><td> A++ 输出结果 11</td></tr>
<tr><td>--</td><td>自减</td><td> A-- 输出结果 9</td></tr>
</tbody></table>
<p>以下实例演示了各个算术运算符的用法：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
<br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> a <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">21</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> b <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">10</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> c <span style="color: #993333;">int</span><br>
<br>
&nbsp; &nbsp;c <span style="color: #339933;">=</span> a <span style="color: #339933;">+</span> b<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第一行 - c 的值为 %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;c <span style="color: #339933;">=</span> a <span style="color: #339933;">-</span> b<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第二行 - c 的值为 %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;c <span style="color: #339933;">=</span> a <span style="color: #339933;">*</span> b<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第三行 - c 的值为 %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;c <span style="color: #339933;">=</span> a <span style="color: #339933;">/</span> b<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第四行 - c 的值为 %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;c <span style="color: #339933;">=</span> a <span style="color: #339933;">%</span> b<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第五行 - c 的值为 %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;a<span style="color: #339933;">++</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第六行 - a 的值为 %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> a <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;a<span style="color: #339933;">=</span><span style="color: #cc66cc;">21</span> &nbsp; <span style="color: #666666; font-style: italic;">// 为了方便测试，a 这里重新赋值为 21</span><br>
&nbsp; &nbsp;a<span style="color: #339933;">--</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第七行 - a 的值为 %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> a <span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>

<p>以上实例运行结果：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pun">第一行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> c </span><span class="pun">的值为</span><span class="pln"> </span><span class="lit">31</span><span class="pln">
</span><span class="pun">第二行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> c </span><span class="pun">的值为</span><span class="pln"> </span><span class="lit">11</span><span class="pln">
</span><span class="pun">第三行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> c </span><span class="pun">的值为</span><span class="pln"> </span><span class="lit">210</span><span class="pln">
</span><span class="pun">第四行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> c </span><span class="pun">的值为</span><span class="pln"> </span><span class="lit">2</span><span class="pln">
</span><span class="pun">第五行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> c </span><span class="pun">的值为</span><span class="pln"> </span><span class="lit">1</span><span class="pln">
</span><span class="pun">第六行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> a </span><span class="pun">的值为</span><span class="pln"> </span><span class="lit">22</span><span class="pln">
</span><span class="pun">第七行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> a </span><span class="pun">的值为</span><span class="pln"> </span><span class="lit">20</span></pre>
<hr>
<h2>关系运算符</h2>
<p>下表列出了所有Go语言的关系运算符。假定 A 值为 10，B 值为 20。</p>
<table class="reference">
<tbody><tr><th style="width:10%">运算符</th><th style="width:55%;">描述</th><th>实例</th></tr>
<tr><td>==</td><td> 检查两个值是否相等，如果相等返回 True 否则返回 False。</td><td> (A == B)  为 False </td></tr>
<tr><td>!=</td><td> 检查两个值是否不相等，如果不相等返回 True 否则返回 False。</td><td> (A != B) 为 True </td></tr>
<tr><td>&gt;</td><td>检查左边值是否大于右边值，如果是返回 True 否则返回 False。</td><td> (A &gt; B) 为 False</td></tr>
<tr><td>&lt;</td><td>检查左边值是否小于右边值，如果是返回 True 否则返回 False。</td><td> (A &lt; B) 为 True </td></tr>
<tr><td>&gt;=</td><td>检查左边值是否大于等于右边值，如果是返回 True 否则返回 False。</td><td> (A &gt;= B) 为 False </td></tr>
<tr><td>&lt;=</td><td> 检查左边值是否小于等于右边值，如果是返回 True 否则返回 False。</td><td> (A &lt;= B) 为 True </td></tr>
</tbody></table>
<p>以下实例演示了关系运算符的用法：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> a <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">21</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> b <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">10</span><br>
<br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">if</span><span style="color: #339933;">(</span> a <span style="color: #339933;">==</span> b <span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第一行 - a 等于 b<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span> <span style="color: #b1b100; font-weight: bold;">else</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第一行 - a 不等于 b<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">if</span> <span style="color: #339933;">(</span> a &lt; b <span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第二行 - a 小于 b<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span> <span style="color: #b1b100; font-weight: bold;">else</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第二行 - a 不小于 b<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span> <br>
&nbsp; &nbsp;<br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">if</span> <span style="color: #339933;">(</span> a &gt; b <span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第三行 - a 大于 b<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span> <span style="color: #b1b100; font-weight: bold;">else</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第三行 - a 不大于 b<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* Lets change value of a and b */</span><br>
&nbsp; &nbsp;a <span style="color: #339933;">=</span> <span style="color: #cc66cc;">5</span><br>
&nbsp; &nbsp;b <span style="color: #339933;">=</span> <span style="color: #cc66cc;">20</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">if</span> <span style="color: #339933;">(</span> a &lt;<span style="color: #339933;">=</span> b <span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第四行 - a 小于等于 b<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">if</span> <span style="color: #339933;">(</span> b &gt;<span style="color: #339933;">=</span> a <span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第五行 - b 大于等于 a<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
<span style="color: #339933;">}</span><br>
</div></div>

<p>以上实例运行结果：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pun">第一行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> a </span><span class="pun">不等于</span><span class="pln"> b
</span><span class="pun">第二行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> a </span><span class="pun">不小于</span><span class="pln"> b
</span><span class="pun">第三行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> a </span><span class="pun">大于</span><span class="pln"> b
</span><span class="pun">第四行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> a </span><span class="pun">小于等于</span><span class="pln"> b
</span><span class="pun">第五行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> b </span><span class="pun">大于等于</span><span class="pln"> a</span></pre>
<hr>
<h2>逻辑运算符</h2>

<p>下表列出了所有Go语言的逻辑运算符。假定 A 值为 True，B 值为 False。</p>
<table class="reference">
<tbody><tr><th style="width:10%">运算符</th><th style="width:55%;">描述</th><th>实例</th></tr>
<tr><td>&amp;&amp;</td><td> 逻辑 AND 运算符。 如果两边的操作数都是 True，则条件 True，否则为 False。 </td><td> (A &amp;&amp; B) 为 False</td></tr>
<tr><td>||</td><td>逻辑 OR 运算符。 如果两边的操作数有一个 True，则条件 True，否则为 False。</td><td> (A || B) 为 True </td></tr>
<tr><td>!</td><td>逻辑 NOT 运算符。 如果条件为 True，则逻辑 NOT 条件 False，否则为 True。</td><td> !(A &amp;&amp; B) 为 True </td></tr>
</tbody></table>
<p>以下实例演示了逻辑运算符的用法：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> a <span style="color: #993333;">bool</span> <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">true</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> b <span style="color: #993333;">bool</span> <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">false</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">if</span> <span style="color: #339933;">(</span> a &amp;&amp; b <span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第一行 - 条件为 true<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">if</span> <span style="color: #339933;">(</span> a <span style="color: #339933;">||</span> b <span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第二行 - 条件为 true<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 修改 a 和 b 的值 */</span><br>
&nbsp; &nbsp;a <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">false</span><br>
&nbsp; &nbsp;b <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">true</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">if</span> <span style="color: #339933;">(</span> a &amp;&amp; b <span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第三行 - 条件为 true<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span> <span style="color: #b1b100; font-weight: bold;">else</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第三行 - 条件为 false<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">if</span> <span style="color: #339933;">(</span> <span style="color: #339933;">!</span><span style="color: #339933;">(</span>a &amp;&amp; b<span style="color: #339933;">)</span> <span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第四行 - 条件为 true<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
<span style="color: #339933;">}</span><br>
</div></div>
<p>以上实例运行结果：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pun">第二行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> </span><span class="pun">条件为</span><span class="pln"> </span><span class="kwd">true</span><span class="pln">
</span><span class="pun">第三行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> </span><span class="pun">条件为</span><span class="pln"> </span><span class="kwd">false</span><span class="pln">
</span><span class="pun">第四行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> </span><span class="pun">条件为</span><span class="pln"> </span><span class="kwd">true</span></pre>
<hr>
<h2>位运算符</h2>
<p>位运算符对整数在内存中的二进制位进行操作。</p>
<p>下表列出了位运算符 &amp;, |, 和 ^ 的计算：</p>
<table class="reference">
<tbody><tr><th style="width:20%">p</th><th style="width:20%">q</th><th style="width:20%">p &amp; q</th><th style="width:20%">p | q</th><th style="width:20%">p ^ q</th></tr>
<tr><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr>
<tr><td>0</td><td>1</td><td>0</td><td>1</td><td>1</td></tr>
<tr><td>1</td><td>1</td><td>1</td><td>1</td><td>0</td></tr>
<tr><td>1</td><td>0</td><td>0</td><td>1</td><td>1</td></tr>
</tbody></table>
<p>假定 A = 60;  B = 13; 其二进制数转换为：
</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">A </span><span class="pun">=</span><span class="pln"> </span><span class="lit">0011</span><span class="pln"> </span><span class="lit">1100</span><span class="pln">

B </span><span class="pun">=</span><span class="pln"> </span><span class="lit">0000</span><span class="pln"> </span><span class="lit">1101</span><span class="pln">

</span><span class="pun">-----------------</span><span class="pln">

A</span><span class="pun">&amp;</span><span class="pln">B </span><span class="pun">=</span><span class="pln"> </span><span class="lit">0000</span><span class="pln"> </span><span class="lit">1100</span><span class="pln">

A</span><span class="pun">|</span><span class="pln">B </span><span class="pun">=</span><span class="pln"> </span><span class="lit">0011</span><span class="pln"> </span><span class="lit">1101</span><span class="pln">

A</span><span class="pun">^</span><span class="pln">B </span><span class="pun">=</span><span class="pln"> </span><span class="lit">0011</span><span class="pln"> </span><span class="lit">0001</span></pre>
<p>
</p><p>Go 语言支持的位运算符如下表所示。假定 A 为60，B 为13：</p>
<table class="reference">
<tbody><tr><th style="width:10%">运算符</th><th style="width:55%;">描述</th><th>实例</th></tr>
<tr><td>&amp;</td><td> 按位与运算符"&amp;"是双目运算符。 其功能是参与运算的两数各对应的二进位相与。 </td><td> (A &amp; B) 结果为 12,  二进制为 0000 1100</td></tr>
<tr><td>|</td><td>按位或运算符"|"是双目运算符。 其功能是参与运算的两数各对应的二进位相或</td><td> (A | B) 结果为 61, 二进制为 0011 1101</td></tr>
<tr><td>^</td><td> 按位异或运算符"^"是双目运算符。 其功能是参与运算的两数各对应的二进位相异或，当两对应的二进位相异时，结果为1。</td><td> (A ^ B) 结果为 49, 二进制为 0011 0001</td></tr>
<tr><td>&lt;&lt;</td><td> 左移运算符"&lt;&lt;"是双目运算符。左移n位就是乘以2的n次方。 其功能把"&lt;&lt;"左边的运算数的各二进位全部左移若干位，由"&lt;&lt;"右边的数指定移动的位数，高位丢弃，低位补0。 </td><td> A &lt;&lt; 2 结果为 240 ，二进制为 1111 0000</td></tr>
<tr><td>&gt;&gt;</td><td> 右移运算符"&gt;&gt;"是双目运算符。右移n位就是除以2的n次方。
其功能是把"&gt;&gt;"左边的运算数的各二进位全部右移若干位，"&gt;&gt;"右边的数指定移动的位数。 </td><td> A &gt;&gt; 2 结果为 15 ，二进制为 0000 1111</td></tr>
</tbody></table>
<p>以下实例演示了位运算符的用法：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
<br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> a <span style="color: #993333;">uint</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">60</span>&nbsp; &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">/* 60 = 0011 1100 */</span> &nbsp;<br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> b <span style="color: #993333;">uint</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">13</span>&nbsp; &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">/* 13 = 0000 1101 */</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> c <span style="color: #993333;">uint</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">0</span> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<br>
<br>
&nbsp; &nbsp;c <span style="color: #339933;">=</span> a &amp; b &nbsp; &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">/* 12 = 0000 1100 */</span> <br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第一行 - c 的值为 %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;c <span style="color: #339933;">=</span> a <span style="color: #339933;">|</span> b &nbsp; &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">/* 61 = 0011 1101 */</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第二行 - c 的值为 %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;c <span style="color: #339933;">=</span> a <span style="color: #339933;">^</span> b &nbsp; &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">/* 49 = 0011 0001 */</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第三行 - c 的值为 %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;c <span style="color: #339933;">=</span> a &lt;&lt; <span style="color: #cc66cc;">2</span> &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">/* 240 = 1111 0000 */</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第四行 - c 的值为 %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;c <span style="color: #339933;">=</span> a &gt;&gt; <span style="color: #cc66cc;">2</span> &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">/* 15 = 0000 1111 */</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第五行 - c 的值为 %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>


<p>以上实例运行结果：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pun">第一行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> c </span><span class="pun">的值为</span><span class="pln"> </span><span class="lit">12</span><span class="pln">
</span><span class="pun">第二行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> c </span><span class="pun">的值为</span><span class="pln"> </span><span class="lit">61</span><span class="pln">
</span><span class="pun">第三行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> c </span><span class="pun">的值为</span><span class="pln"> </span><span class="lit">49</span><span class="pln">
</span><span class="pun">第四行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> c </span><span class="pun">的值为</span><span class="pln"> </span><span class="lit">240</span><span class="pln">
</span><span class="pun">第五行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> c </span><span class="pun">的值为</span><span class="pln"> </span><span class="lit">15</span></pre>
<hr>
<h2>赋值运算符</h2>
<p>下表列出了所有Go语言的赋值运算符。</p>
<table class="reference">
<tbody><tr><th style="width:10%">运算符</th><th style="width:55%;">描述</th><th>实例</th></tr>
<tr><td>=</td><td>简单的赋值运算符，将一个表达式的值赋给一个左值</td><td> C = A + B 将 A + B 表达式结果赋值给 C</td></tr>
<tr><td>+=</td><td>相加后再赋值</td><td> C += A 等于 C = C + A</td></tr>
<tr><td>-=</td><td>相减后再赋值</td><td> C -= A 等于 C = C - A</td></tr>
<tr><td>*=</td><td>相乘后再赋值</td><td> C *= A 等于 C = C * A</td></tr>
<tr><td>/=</td><td>相除后再赋值</td><td> C /= A 等于 C = C / A</td></tr>
<tr><td>%=</td><td>求余后再赋值</td><td> C %= A 等于 C = C % A</td></tr>
<tr><td>&lt;&lt;=</td><td>左移后赋值 </td><td> C &lt;&lt;= 2 等于  C = C &lt;&lt; 2</td></tr>
<tr><td>&gt;&gt;=</td><td>右移后赋值 </td><td> C &gt;&gt;= 2 等于  C = C &gt;&gt; 2</td></tr>
<tr><td>&amp;=</td><td>按位与后赋值</td><td> C &amp;= 2 等于  C = C &amp; 2</td></tr>
<tr><td>^=</td><td>按位异或后赋值</td><td> C ^= 2 等于  C = C ^ 2</td></tr>
<tr><td>|=</td><td>按位或后赋值</td><td> C |= 2 等于  C = C | 2</td></tr>
</tbody></table>
<p>以下实例演示了赋值运算符的用法：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> a <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">21</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> c <span style="color: #993333;">int</span><br>
<br>
&nbsp; &nbsp;c <span style="color: #339933;">=</span> &nbsp;a<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第 1 行 - = &nbsp;运算符实例，c 值为 = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;c <span style="color: #339933;">+=</span> &nbsp;a<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第 2 行 - += 运算符实例，c 值为 = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;c <span style="color: #339933;">-=</span> &nbsp;a<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第 3 行 - -= 运算符实例，c 值为 = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;c <span style="color: #339933;">*=</span> &nbsp;a<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第 4 行 - *= 运算符实例，c 值为 = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;c <span style="color: #339933;">/=</span> &nbsp;a<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第 5 行 - /= 运算符实例，c 值为 = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;c &nbsp;<span style="color: #339933;">=</span> <span style="color: #cc66cc;">200</span><span style="color: #339933;">;</span> <br>
<br>
&nbsp; &nbsp;c &lt;&lt;<span style="color: #339933;">=</span> &nbsp;<span style="color: #cc66cc;">2</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第 6行 &nbsp;- &lt;&lt;= 运算符实例，c 值为 = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;c &gt;&gt;<span style="color: #339933;">=</span> &nbsp;<span style="color: #cc66cc;">2</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第 7 行 - &gt;&gt;= 运算符实例，c 值为 = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;c &amp;<span style="color: #339933;">=</span> &nbsp;<span style="color: #cc66cc;">2</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第 8 行 - &amp;= 运算符实例，c 值为 = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;c <span style="color: #339933;">^=</span> &nbsp;<span style="color: #cc66cc;">2</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第 9 行 - ^= 运算符实例，c 值为 = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;c <span style="color: #339933;">|=</span> &nbsp;<span style="color: #cc66cc;">2</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"第 10 行 - |= 运算符实例，c 值为 = %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">)</span><br>
<br>
<span style="color: #339933;">}</span><br>
</div></div>
<p>以上实例运行结果：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pun">第</span><span class="pln"> </span><span class="lit">1</span><span class="pln"> </span><span class="pun">行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> </span><span class="pun">=</span><span class="pln">  </span><span class="pun">运算符实例，</span><span class="pln">c </span><span class="pun">值为</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">21</span><span class="pln">
</span><span class="pun">第</span><span class="pln"> </span><span class="lit">2</span><span class="pln"> </span><span class="pun">行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> </span><span class="pun">+=</span><span class="pln"> </span><span class="pun">运算符实例，</span><span class="pln">c </span><span class="pun">值为</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">42</span><span class="pln">
</span><span class="pun">第</span><span class="pln"> </span><span class="lit">3</span><span class="pln"> </span><span class="pun">行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> </span><span class="pun">-=</span><span class="pln"> </span><span class="pun">运算符实例，</span><span class="pln">c </span><span class="pun">值为</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">21</span><span class="pln">
</span><span class="pun">第</span><span class="pln"> </span><span class="lit">4</span><span class="pln"> </span><span class="pun">行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> </span><span class="pun">*=</span><span class="pln"> </span><span class="pun">运算符实例，</span><span class="pln">c </span><span class="pun">值为</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">441</span><span class="pln">
</span><span class="pun">第</span><span class="pln"> </span><span class="lit">5</span><span class="pln"> </span><span class="pun">行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> </span><span class="pun">/=</span><span class="pln"> </span><span class="pun">运算符实例，</span><span class="pln">c </span><span class="pun">值为</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">21</span><span class="pln">
</span><span class="pun">第</span><span class="pln"> </span><span class="lit">6</span><span class="pun">行</span><span class="pln">  </span><span class="pun">-</span><span class="pln"> </span><span class="pun">&lt;&lt;=</span><span class="pln"> </span><span class="pun">运算符实例，</span><span class="pln">c </span><span class="pun">值为</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">800</span><span class="pln">
</span><span class="pun">第</span><span class="pln"> </span><span class="lit">7</span><span class="pln"> </span><span class="pun">行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> </span><span class="pun">&gt;&gt;=</span><span class="pln"> </span><span class="pun">运算符实例，</span><span class="pln">c </span><span class="pun">值为</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">200</span><span class="pln">
</span><span class="pun">第</span><span class="pln"> </span><span class="lit">8</span><span class="pln"> </span><span class="pun">行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> </span><span class="pun">&amp;=</span><span class="pln"> </span><span class="pun">运算符实例，</span><span class="pln">c </span><span class="pun">值为</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">0</span><span class="pln">
</span><span class="pun">第</span><span class="pln"> </span><span class="lit">9</span><span class="pln"> </span><span class="pun">行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> </span><span class="pun">^=</span><span class="pln"> </span><span class="pun">运算符实例，</span><span class="pln">c </span><span class="pun">值为</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">2</span><span class="pln">
</span><span class="pun">第</span><span class="pln"> </span><span class="lit">10</span><span class="pln"> </span><span class="pun">行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> </span><span class="pun">|=</span><span class="pln"> </span><span class="pun">运算符实例，</span><span class="pln">c </span><span class="pun">值为</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">2</span></pre>
<hr>
<h2>其他运算符</h2>
<p>下表列出了Go语言的其他运算符。</p>

<table class="reference">
<tbody><tr><th style="width:10%">运算符</th><th style="width:55%;">描述</th><th>实例</th></tr>
<tr>
<td>&amp;</td><td>返回变量存储地址</td><td>&amp;a; 将给出变量的实际地址。</td>
</tr>
<tr>
<td>*</td><td>指针变量。</td><td>*a; 是一个指针变量</td>
</tr>
</tbody></table>
<p>以下实例演示了其他运算符的用法：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> a <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">4</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> b <span style="color: #993333;">int32</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> c <span style="color: #993333;">float32</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> ptr <span style="color: #339933;">*</span><span style="color: #993333;">int</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 运算符实例 */</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第 1 行 - a 变量类型为 = %T<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> a <span style="color: #339933;">);</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第 2 行 - b 变量类型为 = %T<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> b <span style="color: #339933;">);</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"第 3 行 - c 变量类型为 = %T<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> c <span style="color: #339933;">);</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* &nbsp;&amp; 和 * 运算符实例 */</span><br>
&nbsp; &nbsp;ptr <span style="color: #339933;">=</span> <span style="color: #339933;">&amp;</span>a &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">/* 'ptr' 包含了 'a' 变量的地址 */</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"a 的值为 &nbsp;%d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> a<span style="color: #339933;">);</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"*ptr 为 %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> <span style="color: #339933;">*</span>ptr<span style="color: #339933;">);</span><br>
<span style="color: #339933;">}</span><br>
</div></div>
<p>以上实例运行结果：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pun">第</span><span class="pln"> </span><span class="lit">1</span><span class="pln"> </span><span class="pun">行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> a </span><span class="pun">变量类型为</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="kwd">int</span><span class="pln">
</span><span class="pun">第</span><span class="pln"> </span><span class="lit">2</span><span class="pln"> </span><span class="pun">行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> b </span><span class="pun">变量类型为</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> int32
</span><span class="pun">第</span><span class="pln"> </span><span class="lit">3</span><span class="pln"> </span><span class="pun">行</span><span class="pln"> </span><span class="pun">-</span><span class="pln"> c </span><span class="pun">变量类型为</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> float32
a </span><span class="pun">的值为</span><span class="pln">  </span><span class="lit">4</span><span class="pln">
</span><span class="pun">*</span><span class="pln">ptr </span><span class="pun">为</span><span class="pln"> </span><span class="lit">4</span></pre>
<hr>
<h2>运算符优先级</h2>
<p>有些运算符拥有较高的优先级，二元运算符的运算方向均是从左至右。下表列出了所有运算符以及它们的优先级，由上至下代表优先级由高到低：</p>
<table class="reference">
<tbody><tr><th>
优先级</th><th>运算符</th></tr><tr><td>
 5  </td><td>    *  /  %  &lt;&lt;  &gt;&gt;  &amp;  &amp;^</td></tr><tr><td>

 4   </td><td>   +  -  |  ^</td></tr><tr><td>
 3  </td><td>    ==  !=  &lt;  &lt;=  &gt;  &gt;=</td></tr><tr><td>
 2  </td><td>    &amp;&amp;</td></tr><tr><td>
 1  </td><td>    ||</td></tr></tbody></table>
<p>当然，你可以通过使用括号来临时提升某个表达式的整体运算优先级。</p><p>以上实例运行结果：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> a <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">20</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> b <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">10</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> c <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">15</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> d <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">5</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> e <span style="color: #993333;">int</span><span style="color: #339933;">;</span><br>
<br>
&nbsp; &nbsp;e <span style="color: #339933;">=</span> <span style="color: #339933;">(</span>a <span style="color: #339933;">+</span> b<span style="color: #339933;">)</span> <span style="color: #339933;">*</span> c <span style="color: #339933;">/</span> d<span style="color: #339933;">;</span> &nbsp; &nbsp; &nbsp;<span style="color: #666666; font-style: italic;">// ( 30 * 15 ) / 5</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"(a + b) * c / d 的值为 : %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> &nbsp;e <span style="color: #339933;">);</span><br>
<br>
&nbsp; &nbsp;e <span style="color: #339933;">=</span> <span style="color: #339933;">((</span>a <span style="color: #339933;">+</span> b<span style="color: #339933;">)</span> <span style="color: #339933;">*</span> c<span style="color: #339933;">)</span> <span style="color: #339933;">/</span> d<span style="color: #339933;">;</span> &nbsp; &nbsp;<span style="color: #666666; font-style: italic;">// (30 * 15 ) / 5</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"((a + b) * c) / d 的值为 &nbsp;: %d<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: #339933;">,</span> &nbsp;e <span style="color: #339933;">);</span><br>
<br>
&nbsp; &nbsp;e <span style="color: #339933;">=</span> <span style="color: #339933;">(</span>a <span style="color: #339933;">+</span> b<span style="color: #339933;">)</span> <span style="color: #339933;">*</span> <span style="color: #339933;">(</span>c <span style="color: #339933;">/</span> d<span style="color: #339933;">);</span> &nbsp; <span style="color: #666666; font-style: italic;">// (30) * (15/5)</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"(a + b) * (c / d) 的值为 &nbsp;: %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> &nbsp;e <span style="color: #339933;">);</span><br>
<br>
&nbsp; &nbsp;e <span style="color: #339933;">=</span> a <span style="color: #339933;">+</span> <span style="color: #339933;">(</span>b <span style="color: #339933;">*</span> c<span style="color: #339933;">)</span> <span style="color: #339933;">/</span> d<span style="color: #339933;">;</span> &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// &nbsp;20 + (150/5)</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"a + (b * c) / d 的值为 &nbsp;: %d<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: #339933;">,</span> &nbsp;e <span style="color: #339933;">);</span> &nbsp;<br>
<span style="color: #339933;">}</span><br>
</div></div>
<p>以上实例运行结果：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pun">(</span><span class="pln">a </span><span class="pun">+</span><span class="pln"> b</span><span class="pun">)</span><span class="pln"> </span><span class="pun">*</span><span class="pln"> c </span><span class="pun">/</span><span class="pln"> d </span><span class="pun">的值为</span><span class="pln"> </span><span class="pun">:</span><span class="pln"> </span><span class="lit">90</span><span class="pln">
</span><span class="pun">((</span><span class="pln">a </span><span class="pun">+</span><span class="pln"> b</span><span class="pun">)</span><span class="pln"> </span><span class="pun">*</span><span class="pln"> c</span><span class="pun">)</span><span class="pln"> </span><span class="pun">/</span><span class="pln"> d </span><span class="pun">的值为</span><span class="pln">  </span><span class="pun">:</span><span class="pln"> </span><span class="lit">90</span><span class="pln">
</span><span class="pun">(</span><span class="pln">a </span><span class="pun">+</span><span class="pln"> b</span><span class="pun">)</span><span class="pln"> </span><span class="pun">*</span><span class="pln"> </span><span class="pun">(</span><span class="pln">c </span><span class="pun">/</span><span class="pln"> d</span><span class="pun">)</span><span class="pln"> </span><span class="pun">的值为</span><span class="pln">  </span><span class="pun">:</span><span class="pln"> </span><span class="lit">90</span><span class="pln">
a </span><span class="pun">+</span><span class="pln"> </span><span class="pun">(</span><span class="pln">b </span><span class="pun">*</span><span class="pln"> c</span><span class="pun">)</span><span class="pln"> </span><span class="pun">/</span><span class="pln"> d </span><span class="pun">的值为</span><span class="pln">  </span><span class="pun">:</span><span class="pln"> </span><span class="lit">50</span></pre>			<!-- 其他扩展 -->


		