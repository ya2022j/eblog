
# Go 语言常量
<p>
常量是一个简单值的标识符，在程序运行时，不会被修改的量。</p>
<p>常量中的数据类型只可以是布尔型、数字型（整数型、浮点型和复数）和字符串型。</p>
<p>常量的定义格式：</p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">const</span><span class="pln"> identifier </span><span class="pun">[</span><span class="pln">type</span><span class="pun">]</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> value</span></pre>
<p>你可以省略类型说明符 [type]，因为编译器可以根据变量的值来推断其类型。</p>
<ul>
<li>显式类型定义： <code>const b string = "abc"</code><br></li>
<li>隐式类型定义： <code>const b = "abc"</code></li>
</ul>
<p>多个相同类型的声明可以简写为：</p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">const</span><span class="pln"> c_name1</span><span class="pun">,</span><span class="pln"> c_name2 </span><span class="pun">=</span><span class="pln"> value1</span><span class="pun">,</span><span class="pln"> value2</span></pre>

<p>以下实例演示了常量的应用：
</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">const</span> LENGTH <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">10</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">const</span> WIDTH <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">5</span> &nbsp; <br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> area <span style="color: #993333;">int</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">const</span> a<span style="color: #339933;">,</span> b<span style="color: #339933;">,</span> c <span style="color: #339933;">=</span> <span style="color: #cc66cc;">1</span><span style="color: #339933;">,</span> <span style="color: #000000; font-weight: bold;">false</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">"str"</span> <span style="color: #666666; font-style: italic;">//多重赋值</span><br>
<br>
&nbsp; &nbsp;area <span style="color: #339933;">=</span> LENGTH <span style="color: #339933;">*</span> WIDTH<br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"面积为 : %d"</span><span style="color: #339933;">,</span> area<span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #000066;">println</span><span style="color: #339933;">()</span><br>
&nbsp; &nbsp;<span style="color: #000066;">println</span><span style="color: #339933;">(</span>a<span style="color: #339933;">,</span> b<span style="color: #339933;">,</span> c<span style="color: #339933;">)</span> &nbsp; <br>
<span style="color: #339933;">}</span><br>
</div></div>

<p>以上实例运行结果为：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pun">面积为</span><span class="pln"> </span><span class="pun">:</span><span class="pln"> </span><span class="lit">50</span><span class="pln">
</span><span class="lit">1</span><span class="pln"> </span><span class="kwd">false</span><span class="pln"> str</span></pre>
<p>常量还可以用作枚举：
</p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">const</span><span class="pln"> </span><span class="pun">(</span><span class="pln">
    </span><span class="typ">Unknown</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">0</span><span class="pln">
    </span><span class="typ">Female</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">1</span><span class="pln">
    </span><span class="typ">Male</span><span class="pln"> </span><span class="pun">=</span><span class="pln"> </span><span class="lit">2</span><span class="pln">
</span><span class="pun">)</span></pre>
<p>数字 0、1 和 2 分别代表未知性别、女性和男性。</p>
<p>常量可以用len(), cap(), unsafe.Sizeof()函数计算表达式的值。常量表达式中，函数必须是内置函数，否则编译不过：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"unsafe"</span><br>
<span style="color: #b1b100; font-weight: bold;">const</span> <span style="color: #339933;">(</span><br>
&nbsp; &nbsp; a <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"abc"</span><br>
&nbsp; &nbsp; b <span style="color: #339933;">=</span> <span style="color: #000066;">len</span><span style="color: #339933;">(</span>a<span style="color: #339933;">)</span><br>
&nbsp; &nbsp; c <span style="color: #339933;">=</span> unsafe<span style="color: #339933;">.</span>Sizeof<span style="color: #339933;">(</span>a<span style="color: #339933;">)</span><br>
<span style="color: #339933;">)</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">(){</span><br>
&nbsp; &nbsp; <span style="color: #000066;">println</span><span style="color: #339933;">(</span>a<span style="color: #339933;">,</span> b<span style="color: #339933;">,</span> c<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>
<p>以上实例运行结果为：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">abc </span><span class="lit">3</span><span class="pln"> </span><span class="lit">16</span></pre>
<hr>
<h2>iota</h2>
<p>iota，特殊常量，可以认为是一个可以被编译器修改的常量。</p>

<p>iota 在 const关键字出现时将被重置为 0(const 内部的第一行之前)，const 中每新增一行常量声明将使 iota 计数一次(iota 可理解为 const 语句块中的行索引)。</p>
<p>iota 可以被用作枚举值：</p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">const</span><span class="pln"> </span><span class="pun">(</span><span class="pln">
    a </span><span class="pun">=</span><span class="pln"> iota
    b </span><span class="pun">=</span><span class="pln"> iota
    c </span><span class="pun">=</span><span class="pln"> iota
</span><span class="pun">)</span></pre>
<p>第一个 iota 等于 0，每当 iota 在新的一行被使用时，它的值都会自动加 1；所以 a=0, b=1, c=2 可以简写为如下形式：</p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">const</span><span class="pln"> </span><span class="pun">(</span><span class="pln">
    a </span><span class="pun">=</span><span class="pln"> iota
    b
    c
</span><span class="pun">)</span></pre>
<h3>iota 用法</h3>
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">const</span> <span style="color: #339933;">(</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; a <span style="color: #339933;">=</span> iota &nbsp; <span style="color: #666666; font-style: italic;">//0</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; b &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<span style="color: #666666; font-style: italic;">//1</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; c &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<span style="color: #666666; font-style: italic;">//2</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; d <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"ha"</span> &nbsp; <span style="color: #666666; font-style: italic;">//独立值，iota += 1</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; e &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<span style="color: #666666; font-style: italic;">//"ha" &nbsp; iota += 1</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; f <span style="color: #339933;">=</span> <span style="color: #cc66cc;">100</span> &nbsp; &nbsp;<span style="color: #666666; font-style: italic;">//iota +=1</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; g &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<span style="color: #666666; font-style: italic;">//100 &nbsp;iota +=1</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; h <span style="color: #339933;">=</span> iota &nbsp; <span style="color: #666666; font-style: italic;">//7,恢复计数</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; i &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<span style="color: #666666; font-style: italic;">//8</span><br>
&nbsp; &nbsp; <span style="color: #339933;">)</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span>a<span style="color: #339933;">,</span>b<span style="color: #339933;">,</span>c<span style="color: #339933;">,</span>d<span style="color: #339933;">,</span>e<span style="color: #339933;">,</span>f<span style="color: #339933;">,</span>g<span style="color: #339933;">,</span>h<span style="color: #339933;">,</span>i<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>

<p>以上实例运行结果为：</p>
<pre class="prettyprint prettyprinted" style=""><span class="lit">0</span><span class="pln"> </span><span class="lit">1</span><span class="pln"> </span><span class="lit">2</span><span class="pln"> ha ha </span><span class="lit">100</span><span class="pln"> </span><span class="lit">100</span><span class="pln"> </span><span class="lit">7</span><span class="pln"> </span><span class="lit">8</span></pre>
<p>再看个有趣的的 iota 实例：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<span style="color: #b1b100; font-weight: bold;">const</span> <span style="color: #339933;">(</span><br>
&nbsp; &nbsp; <span style="">i</span><span style="color: #339933;">=</span><span style="color: #cc66cc;">1</span>&lt;&lt;iota<br>
&nbsp; &nbsp; j<span style="color: #339933;">=</span><span style="color: #cc66cc;">3</span>&lt;&lt;iota<br>
&nbsp; &nbsp; k<br>
&nbsp; &nbsp; l<br>
<span style="color: #339933;">)</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Println<span style="color: #339933;">(</span><span style="color: #cc66cc;">"i="</span><span style="color: #339933;">,</span>i<span style="color: #339933;">)</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"j="</span><span style="color: #339933;">,</span>j<span style="color: #339933;">)</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"k="</span><span style="color: #339933;">,</span>k<span style="color: #339933;">)</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"l="</span><span style="color: #339933;">,</span>l<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>
<p>以上实例运行结果为：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">i</span><span class="pun">=</span><span class="pln"> </span><span class="lit">1</span><span class="pln">
j</span><span class="pun">=</span><span class="pln"> </span><span class="lit">6</span><span class="pln">
k</span><span class="pun">=</span><span class="pln"> </span><span class="lit">12</span><span class="pln">
l</span><span class="pun">=</span><span class="pln"> </span><span class="lit">24</span></pre>
<p>iota 表示从 0 开始自动加 1，所以 <span class="marked">i=1&lt;&lt;0</span>, <span class="marked">j=3&lt;&lt;1</span>（<strong>&lt;&lt;</strong> 表示左移的意思），即：i=1, j=6，这没问题，关键在 k 和 l，从输出结果看 <span class="marked">k=3&lt;&lt;2</span>，<span class="marked">l=3&lt;&lt;3</span>。</p>
<p>简单表述:</p>
<ul><li>
<strong>i=1</strong>：左移 0 位，不变仍为 1。</li><li>
<strong>j=3</strong>：左移 1 位，变为二进制 <strong>110</strong>，即 6。
</li><li>
<strong>k=3</strong>：左移 2 位，变为二进制 <strong>1100</strong>，即 12。
</li><li>
<strong>l=3</strong>：左移 3 位，变为二进制 <strong>11000</strong>，即 24。</li></ul>


<p>注：<span class="marked">&lt;&lt;n==*(2^n)</span>