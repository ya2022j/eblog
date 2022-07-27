
# Go 语言切片(Slice)

<p>Go 语言切片是对数组的抽象。</p>

<p>Go 数组的长度不可改变，在特定场景中这样的集合就不太适用，Go 中提供了一种灵活，功能强悍的内置类型切片("动态数组")，与数组相比切片的长度是不固定的，可以追加元素，在追加时可能使切片的容量增大。</p>

<hr>

<h2>定义切片</h2>

<p>你可以声明一个未指定大小的数组来定义切片：</p>

<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> identifier </span><span class="pun">[]</span><span class="pln">type</span></pre>

<p>切片不需要说明长度。</p>

<p>或使用 <strong>make()</strong> 函数来创建切片:</p>

<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> slice1 </span><span class="pun">[]</span><span class="pln">type </span><span class="pun">=</span><span class="pln"> make</span><span class="pun">([]</span><span class="pln">type</span><span class="pun">,</span><span class="pln"> len</span><span class="pun">)</span><span class="pln">

</span><span class="pun">也可以简写为</span><span class="pln">

slice1 </span><span class="pun">:=</span><span class="pln"> make</span><span class="pun">([]</span><span class="pln">type</span><span class="pun">,</span><span class="pln"> len</span><span class="pun">)</span></pre>

<p>也可以指定容量，其中 <strong>capacity</strong> 为可选参数。</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">make</span><span class="pun">([]</span><span class="pln">T</span><span class="pun">,</span><span class="pln"> length</span><span class="pun">,</span><span class="pln"> capacity</span><span class="pun">)</span></pre>

<p>这里 len 是数组的长度并且也是切片的初始长度。</p>

<h3>切片初始化</h3>

<pre class="prettyprint prettyprinted" style=""><span class="pln">s </span><span class="pun">:=[]</span><span class="pln"> </span><span class="kwd">int</span><span class="pln"> </span><span class="pun">{</span><span class="lit">1</span><span class="pun">,</span><span class="lit">2</span><span class="pun">,</span><span class="lit">3</span><span class="pln"> </span><span class="pun">}</span><span class="pln"> </span></pre>

<p>直接初始化切片，<span class="marked">[]</span> 表示是切片类型，<strong>{1,2,3}</strong> 初始化值依次是 <span class="marked">1,2,3</span>，其 <strong>cap=len=3</strong>。</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">s </span><span class="pun">:=</span><span class="pln"> arr</span><span class="pun">[:]</span><span class="pln"> </span></pre>

<p>初始化切片 <strong>s</strong>，是数组 arr 的引用。</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">s </span><span class="pun">:=</span><span class="pln"> arr</span><span class="pun">[</span><span class="pln">startIndex</span><span class="pun">:</span><span class="pln">endIndex</span><span class="pun">]</span><span class="pln"> </span></pre>

<p>将 arr 中从下标 startIndex 到 endIndex-1 下的元素创建为一个新的切片。</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">s </span><span class="pun">:=</span><span class="pln"> arr</span><span class="pun">[</span><span class="pln">startIndex</span><span class="pun">:]</span><span class="pln"> </span></pre>

<p>默认 endIndex 时将表示一直到arr的最后一个元素。</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">s </span><span class="pun">:=</span><span class="pln"> arr</span><span class="pun">[:</span><span class="pln">endIndex</span><span class="pun">]</span><span class="pln"> </span></pre>

<p>默认 startIndex 时将表示从 arr 的第一个元素开始。</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">s1 </span><span class="pun">:=</span><span class="pln"> s</span><span class="pun">[</span><span class="pln">startIndex</span><span class="pun">:</span><span class="pln">endIndex</span><span class="pun">]</span><span class="pln"> </span></pre>

<p>通过切片 s 初始化切片 s1。</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">s </span><span class="pun">:=</span><span class="pln">make</span><span class="pun">([]</span><span class="kwd">int</span><span class="pun">,</span><span class="pln">len</span><span class="pun">,</span><span class="pln">cap</span><span class="pun">)</span><span class="pln"> </span></pre>

<p>通过内置函数 <strong>make()</strong> 初始化切片<strong>s</strong>，<strong>[]int</strong> 标识为其元素类型为 int 的切片。</p>

<hr>

<h2>len() 和 cap() 函数</h2>

<p>切片是可索引的，并且可以由 len() 方法获取长度。</p>

<p>切片提供了计算容量的方法 cap() 可以测量切片最长可以达到多少。</p>

<p>以下为具体实例：</p>
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> numbers <span style="color: #339933;">=</span> <span style="color: #000066;">make</span><span style="color: #339933;">([]</span><span style="color: #993333;">int</span><span style="color: #339933;">,</span><span style="color: #cc66cc;">3</span><span style="color: #339933;">,</span><span style="color: #cc66cc;">5</span><span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;printSlice<span style="color: #339933;">(</span>numbers<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
<br>
<span style="color: #993333;">func</span> printSlice<span style="color: #339933;">(</span>x <span style="color: #339933;">[]</span><span style="color: #993333;">int</span><span style="color: #339933;">){</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"len=%d cap=%d slice=%v<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span><span style="color: #000066;">len</span><span style="color: #339933;">(</span>x<span style="color: #339933;">),</span><span style="color: #000066;">cap</span><span style="color: #339933;">(</span>x<span style="color: #339933;">),</span>x<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>


<p>以上实例运行输出结果为:</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">len</span><span class="pun">=</span><span class="lit">3</span><span class="pln"> cap</span><span class="pun">=</span><span class="lit">5</span><span class="pln"> slice</span><span class="pun">=[</span><span class="lit">0</span><span class="pln"> </span><span class="lit">0</span><span class="pln"> </span><span class="lit">0</span><span class="pun">]</span></pre>

<hr>

<h2>空(nil)切片</h2>

<p>一个切片在未初始化之前默认为 nil，长度为 0，实例如下：</p>
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> numbers <span style="color: #339933;">[]</span><span style="color: #993333;">int</span><br>
<br>
&nbsp; &nbsp;printSlice<span style="color: #339933;">(</span>numbers<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">if</span><span style="color: #339933;">(</span>numbers <span style="color: #339933;">==</span> <span style="color: #000000; font-weight: bold;">nil</span><span style="color: #339933;">){</span><br>
&nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"切片是空的"</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp;<span style="color: #339933;">}</span><br>
<span style="color: #339933;">}</span><br>
<br>
<span style="color: #993333;">func</span> printSlice<span style="color: #339933;">(</span>x <span style="color: #339933;">[]</span><span style="color: #993333;">int</span><span style="color: #339933;">){</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"len=%d cap=%d slice=%v<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span><span style="color: #000066;">len</span><span style="color: #339933;">(</span>x<span style="color: #339933;">),</span><span style="color: #000066;">cap</span><span style="color: #339933;">(</span>x<span style="color: #339933;">),</span>x<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>

<p>以上实例运行输出结果为:</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">len</span><span class="pun">=</span><span class="lit">0</span><span class="pln"> cap</span><span class="pun">=</span><span class="lit">0</span><span class="pln"> slice</span><span class="pun">=[]</span><span class="pln">
</span><span class="pun">切片是空的</span></pre>

<hr>

<h2>切片截取</h2>

<p>可以通过设置下限及上限来设置截取切片 <em>[lower-bound:upper-bound]</em>，实例如下：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 创建切片 */</span><br>
&nbsp; &nbsp;numbers <span style="color: #339933;">:=</span> <span style="color: #339933;">[]</span><span style="color: #993333;">int</span><span style="color: #339933;">{</span><span style="color: #cc66cc;">0</span><span style="color: #339933;">,</span><span style="color: #cc66cc;">1</span><span style="color: #339933;">,</span><span style="color: #cc66cc;">2</span><span style="color: #339933;">,</span><span style="color: #cc66cc;">3</span><span style="color: #339933;">,</span><span style="color: #cc66cc;">4</span><span style="color: #339933;">,</span><span style="color: #cc66cc;">5</span><span style="color: #339933;">,</span><span style="color: #cc66cc;">6</span><span style="color: #339933;">,</span><span style="color: #cc66cc;">7</span><span style="color: #339933;">,</span><span style="color: #cc66cc;">8</span><span style="color: #339933;">}</span> &nbsp; <br>
&nbsp; &nbsp;printSlice<span style="color: #339933;">(</span>numbers<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 打印原始切片 */</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"numbers =="</span><span style="color: #339933;">,</span> numbers<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 打印子切片从索引1(包含) 到索引4(不包含)*/</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"numbers[1:4] =="</span><span style="color: #339933;">,</span> numbers<span style="color: #339933;">[</span><span style="color: #cc66cc;">1</span><span style="color: #339933;">:</span><span style="color: #cc66cc;">4</span><span style="color: #339933;">])</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 默认下限为 0*/</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"numbers[:3] =="</span><span style="color: #339933;">,</span> numbers<span style="color: #339933;">[:</span><span style="color: #cc66cc;">3</span><span style="color: #339933;">])</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 默认上限为 len(s)*/</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"numbers[4:] =="</span><span style="color: #339933;">,</span> numbers<span style="color: #339933;">[</span><span style="color: #cc66cc;">4</span><span style="color: #339933;">:])</span><br>
<br>
&nbsp; &nbsp;numbers1 <span style="color: #339933;">:=</span> <span style="color: #000066;">make</span><span style="color: #339933;">([]</span><span style="color: #993333;">int</span><span style="color: #339933;">,</span><span style="color: #cc66cc;">0</span><span style="color: #339933;">,</span><span style="color: #cc66cc;">5</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp;printSlice<span style="color: #339933;">(</span>numbers1<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 打印子切片从索引 &nbsp;0(包含) 到索引 2(不包含) */</span><br>
&nbsp; &nbsp;number2 <span style="color: #339933;">:=</span> numbers<span style="color: #339933;">[:</span><span style="color: #cc66cc;">2</span><span style="color: #339933;">]</span><br>
&nbsp; &nbsp;printSlice<span style="color: #339933;">(</span>number2<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 打印子切片从索引 2(包含) 到索引 5(不包含) */</span><br>
&nbsp; &nbsp;number3 <span style="color: #339933;">:=</span> numbers<span style="color: #339933;">[</span><span style="color: #cc66cc;">2</span><span style="color: #339933;">:</span><span style="color: #cc66cc;">5</span><span style="color: #339933;">]</span><br>
&nbsp; &nbsp;printSlice<span style="color: #339933;">(</span>number3<span style="color: #339933;">)</span><br>
<br>
<span style="color: #339933;">}</span><br>
<br>
<span style="color: #993333;">func</span> printSlice<span style="color: #339933;">(</span>x <span style="color: #339933;">[]</span><span style="color: #993333;">int</span><span style="color: #339933;">){</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"len=%d cap=%d slice=%v<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span><span style="color: #000066;">len</span><span style="color: #339933;">(</span>x<span style="color: #339933;">),</span><span style="color: #000066;">cap</span><span style="color: #339933;">(</span>x<span style="color: #339933;">),</span>x<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>

<p>执行以上代码输出结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">len</span><span class="pun">=</span><span class="lit">9</span><span class="pln"> cap</span><span class="pun">=</span><span class="lit">9</span><span class="pln"> slice</span><span class="pun">=[</span><span class="lit">0</span><span class="pln"> </span><span class="lit">1</span><span class="pln"> </span><span class="lit">2</span><span class="pln"> </span><span class="lit">3</span><span class="pln"> </span><span class="lit">4</span><span class="pln"> </span><span class="lit">5</span><span class="pln"> </span><span class="lit">6</span><span class="pln"> </span><span class="lit">7</span><span class="pln"> </span><span class="lit">8</span><span class="pun">]</span><span class="pln">
numbers </span><span class="pun">==</span><span class="pln"> </span><span class="pun">[</span><span class="lit">0</span><span class="pln"> </span><span class="lit">1</span><span class="pln"> </span><span class="lit">2</span><span class="pln"> </span><span class="lit">3</span><span class="pln"> </span><span class="lit">4</span><span class="pln"> </span><span class="lit">5</span><span class="pln"> </span><span class="lit">6</span><span class="pln"> </span><span class="lit">7</span><span class="pln"> </span><span class="lit">8</span><span class="pun">]</span><span class="pln">
numbers</span><span class="pun">[</span><span class="lit">1</span><span class="pun">:</span><span class="lit">4</span><span class="pun">]</span><span class="pln"> </span><span class="pun">==</span><span class="pln"> </span><span class="pun">[</span><span class="lit">1</span><span class="pln"> </span><span class="lit">2</span><span class="pln"> </span><span class="lit">3</span><span class="pun">]</span><span class="pln">
numbers</span><span class="pun">[:</span><span class="lit">3</span><span class="pun">]</span><span class="pln"> </span><span class="pun">==</span><span class="pln"> </span><span class="pun">[</span><span class="lit">0</span><span class="pln"> </span><span class="lit">1</span><span class="pln"> </span><span class="lit">2</span><span class="pun">]</span><span class="pln">
numbers</span><span class="pun">[</span><span class="lit">4</span><span class="pun">:]</span><span class="pln"> </span><span class="pun">==</span><span class="pln"> </span><span class="pun">[</span><span class="lit">4</span><span class="pln"> </span><span class="lit">5</span><span class="pln"> </span><span class="lit">6</span><span class="pln"> </span><span class="lit">7</span><span class="pln"> </span><span class="lit">8</span><span class="pun">]</span><span class="pln">
len</span><span class="pun">=</span><span class="lit">0</span><span class="pln"> cap</span><span class="pun">=</span><span class="lit">5</span><span class="pln"> slice</span><span class="pun">=[]</span><span class="pln">
len</span><span class="pun">=</span><span class="lit">2</span><span class="pln"> cap</span><span class="pun">=</span><span class="lit">9</span><span class="pln"> slice</span><span class="pun">=[</span><span class="lit">0</span><span class="pln"> </span><span class="lit">1</span><span class="pun">]</span><span class="pln">
len</span><span class="pun">=</span><span class="lit">3</span><span class="pln"> cap</span><span class="pun">=</span><span class="lit">7</span><span class="pln"> slice</span><span class="pun">=[</span><span class="lit">2</span><span class="pln"> </span><span class="lit">3</span><span class="pln"> </span><span class="lit">4</span><span class="pun">]</span></pre>

<hr>

<h2>append() 和 copy() 函数</h2>

<p>如果想增加切片的容量，我们必须创建一个新的更大的切片并把原分片的内容都拷贝过来。</p>

<p>下面的代码描述了从拷贝切片的 copy 方法和向切片追加新元素的 append 方法。</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> numbers <span style="color: #339933;">[]</span><span style="color: #993333;">int</span><br>
&nbsp; &nbsp;printSlice<span style="color: #339933;">(</span>numbers<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 允许追加空切片 */</span><br>
&nbsp; &nbsp;numbers <span style="color: #339933;">=</span> append<span style="color: #339933;">(</span>numbers<span style="color: #339933;">,</span> <span style="color: #cc66cc;">0</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp;printSlice<span style="color: #339933;">(</span>numbers<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 向切片添加一个元素 */</span><br>
&nbsp; &nbsp;numbers <span style="color: #339933;">=</span> append<span style="color: #339933;">(</span>numbers<span style="color: #339933;">,</span> <span style="color: #cc66cc;">1</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp;printSlice<span style="color: #339933;">(</span>numbers<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 同时添加多个元素 */</span><br>
&nbsp; &nbsp;numbers <span style="color: #339933;">=</span> append<span style="color: #339933;">(</span>numbers<span style="color: #339933;">,</span> <span style="color: #cc66cc;">2</span><span style="color: #339933;">,</span><span style="color: #cc66cc;">3</span><span style="color: #339933;">,</span><span style="color: #cc66cc;">4</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp;printSlice<span style="color: #339933;">(</span>numbers<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 创建切片 numbers1 是之前切片的两倍容量*/</span><br>
&nbsp; &nbsp;numbers1 <span style="color: #339933;">:=</span> <span style="color: #000066;">make</span><span style="color: #339933;">([]</span><span style="color: #993333;">int</span><span style="color: #339933;">,</span> <span style="color: #000066;">len</span><span style="color: #339933;">(</span>numbers<span style="color: #339933;">),</span> <span style="color: #339933;">(</span><span style="color: #000066;">cap</span><span style="color: #339933;">(</span>numbers<span style="color: #339933;">))</span><span style="color: #339933;">*</span><span style="color: #cc66cc;">2</span><span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 拷贝 numbers 的内容到 numbers1 */</span><br>
&nbsp; &nbsp;<span style="color: #000066;">copy</span><span style="color: #339933;">(</span>numbers1<span style="color: #339933;">,</span>numbers<span style="color: #339933;">)</span><br>
&nbsp; &nbsp;printSlice<span style="color: #339933;">(</span>numbers1<span style="color: #339933;">)</span> &nbsp; <br>
<span style="color: #339933;">}</span><br>
<br>
<span style="color: #993333;">func</span> printSlice<span style="color: #339933;">(</span>x <span style="color: #339933;">[]</span><span style="color: #993333;">int</span><span style="color: #339933;">){</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"len=%d cap=%d slice=%v<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span><span style="color: #000066;">len</span><span style="color: #339933;">(</span>x<span style="color: #339933;">),</span><span style="color: #000066;">cap</span><span style="color: #339933;">(</span>x<span style="color: #339933;">),</span>x<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>


<p>以上代码执行输出结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">len</span><span class="pun">=</span><span class="lit">0</span><span class="pln"> cap</span><span class="pun">=</span><span class="lit">0</span><span class="pln"> slice</span><span class="pun">=[]</span><span class="pln">
len</span><span class="pun">=</span><span class="lit">1</span><span class="pln"> cap</span><span class="pun">=</span><span class="lit">1</span><span class="pln"> slice</span><span class="pun">=[</span><span class="lit">0</span><span class="pun">]</span><span class="pln">
len</span><span class="pun">=</span><span class="lit">2</span><span class="pln"> cap</span><span class="pun">=</span><span class="lit">2</span><span class="pln"> slice</span><span class="pun">=[</span><span class="lit">0</span><span class="pln"> </span><span class="lit">1</span><span class="pun">]</span><span class="pln">
len</span><span class="pun">=</span><span class="lit">5</span><span class="pln"> cap</span><span class="pun">=</span><span class="lit">6</span><span class="pln"> slice</span><span class="pun">=[</span><span class="lit">0</span><span class="pln"> </span><span class="lit">1</span><span class="pln"> </span><span class="lit">2</span><span class="pln"> </span><span class="lit">3</span><span class="pln"> </span><span class="lit">4</span><span class="pun">]</span><span class="pln">
len</span><span class="pun">=</span><span class="lit">5</span><span class="pln"> cap</span><span class="pun">=</span><span class="lit">12</span><span class="pln"> slice</span><span class="pun">=[</span><span class="lit">0</span><span class="pln"> </span><span class="lit">1</span><span class="pln"> </span><span class="lit">2</span><span class="pln"> </span><span class="lit">3</span><span class="pln"> </span><span class="lit">4</span><span class="pun">]</span></pre>			<!-- 其他扩展 -->


		