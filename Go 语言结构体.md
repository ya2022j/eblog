
# Go 语言结构体

<p>Go 语言中数组可以存储同一类型的数据，但在结构体中我们可以为不同项定义不同的数据类型。</p>

<p>结构体是由一系列具有相同类型或不同类型的数据构成的数据集合。</p>

<p>结构体表示一项记录，比如保存图书馆的书籍记录，每本书有以下属性：</p>

<ul>
<li>Title ：标题</li>
<li>Author ： 作者</li>
<li>Subject：学科</li>
<li>ID：书籍ID</li>
</ul>


<hr>

<h2>定义结构体</h2>

<p>结构体定义需要使用 type 和 struct 语句。struct 语句定义一个新的数据类型，结构体中有一个或多个成员。type 语句设定了结构体的名称。结构体的格式如下：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">type struct_variable_type </span><span class="kwd">struct</span><span class="pln"> </span><span class="pun">{</span><span class="pln">
   member definition
   member definition
   </span><span class="pun">...</span><span class="pln">
   member definition
</span><span class="pun">}</span></pre>

<p>一旦定义了结构体类型，它就能用于变量的声明，语法格式如下：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">variable_name </span><span class="pun">:=</span><span class="pln"> structure_variable_type </span><span class="pun">{</span><span class="pln">value1</span><span class="pun">,</span><span class="pln"> value2</span><span class="pun">...</span><span class="pln">valuen</span><span class="pun">}</span><span class="pln">
</span><span class="pun">或</span><span class="pln">
variable_name </span><span class="pun">:=</span><span class="pln"> structure_variable_type </span><span class="pun">{</span><span class="pln"> key1</span><span class="pun">:</span><span class="pln"> value1</span><span class="pun">,</span><span class="pln"> key2</span><span class="pun">:</span><span class="pln"> value2</span><span class="pun">...,</span><span class="pln"> keyn</span><span class="pun">:</span><span class="pln"> valuen</span><span class="pun">}</span></pre>
<p>实例如下：</p>
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #b1b100; font-weight: bold;">type</span> Books <span style="color: #993333;">struct</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;title <span style="color: #993333;">string</span><br>
&nbsp; &nbsp;author <span style="color: #993333;">string</span><br>
&nbsp; &nbsp;subject <span style="color: #993333;">string</span><br>
&nbsp; &nbsp;book_id <span style="color: #993333;">int</span><br>
<span style="color: #339933;">}</span><br>
<br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
<br>
&nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// 创建一个新的结构体</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span>Books<span style="color: #339933;">{</span><span style="color: #cc66cc;">"Go 语言"</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">"www.runoob.com"</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">"Go 语言教程"</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">6495407</span><span style="color: #339933;">})</span><br>
<br>
&nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// 也可以使用 key =&gt; value 格式</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span>Books<span style="color: #339933;">{</span>title<span style="color: #339933;">:</span> <span style="color: #cc66cc;">"Go 语言"</span><span style="color: #339933;">,</span> author<span style="color: #339933;">:</span> <span style="color: #cc66cc;">"www.runoob.com"</span><span style="color: #339933;">,</span> subject<span style="color: #339933;">:</span> <span style="color: #cc66cc;">"Go 语言教程"</span><span style="color: #339933;">,</span> book_id<span style="color: #339933;">:</span> <span style="color: #cc66cc;">6495407</span><span style="color: #339933;">})</span><br>
<br>
&nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// 忽略的字段为 0 或 空</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span>Books<span style="color: #339933;">{</span>title<span style="color: #339933;">:</span> <span style="color: #cc66cc;">"Go 语言"</span><span style="color: #339933;">,</span> author<span style="color: #339933;">:</span> <span style="color: #cc66cc;">"www.runoob.com"</span><span style="color: #339933;">})</span><br>
<span style="color: #339933;">}</span><br>
</div></div>
<p>输出结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pun">{</span><span class="typ">Go</span><span class="pln"> </span><span class="pun">语言</span><span class="pln"> www</span><span class="pun">.</span><span class="pln">runoob</span><span class="pun">.</span><span class="pln">com </span><span class="typ">Go</span><span class="pln"> </span><span class="pun">语言教程</span><span class="pln"> </span><span class="lit">6495407</span><span class="pun">}</span><span class="pln">
</span><span class="pun">{</span><span class="typ">Go</span><span class="pln"> </span><span class="pun">语言</span><span class="pln"> www</span><span class="pun">.</span><span class="pln">runoob</span><span class="pun">.</span><span class="pln">com </span><span class="typ">Go</span><span class="pln"> </span><span class="pun">语言教程</span><span class="pln"> </span><span class="lit">6495407</span><span class="pun">}</span><span class="pln">
</span><span class="pun">{</span><span class="typ">Go</span><span class="pln"> </span><span class="pun">语言</span><span class="pln"> www</span><span class="pun">.</span><span class="pln">runoob</span><span class="pun">.</span><span class="pln">com  </span><span class="lit">0</span><span class="pun">}</span></pre>
<hr>

<h2>访问结构体成员</h2>

<p>如果要访问结构体成员，需要使用点号 <span class="marked">.</span>  操作符，格式为： </p><pre class="prettyprint prettyprinted" style=""><span class="pun">结构体.成员名</span><span class="str">"</span></pre>

<p>结构体类型变量使用 struct 关键字定义，实例如下：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #b1b100; font-weight: bold;">type</span> Books <span style="color: #993333;">struct</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;title <span style="color: #993333;">string</span><br>
&nbsp; &nbsp;author <span style="color: #993333;">string</span><br>
&nbsp; &nbsp;subject <span style="color: #993333;">string</span><br>
&nbsp; &nbsp;book_id <span style="color: #993333;">int</span><br>
<span style="color: #339933;">}</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> Book1 Books &nbsp; &nbsp; &nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 声明 Book1 为 Books 类型 */</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> Book2 Books &nbsp; &nbsp; &nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 声明 Book2 为 Books 类型 */</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* book 1 描述 */</span><br>
&nbsp; &nbsp;Book1<span style="color: #339933;">.</span>title <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"Go 语言"</span><br>
&nbsp; &nbsp;Book1<span style="color: #339933;">.</span>author <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"www.runoob.com"</span><br>
&nbsp; &nbsp;Book1<span style="color: #339933;">.</span>subject <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"Go 语言教程"</span><br>
&nbsp; &nbsp;Book1<span style="color: #339933;">.</span>book_id <span style="color: #339933;">=</span> <span style="color: #cc66cc;">6495407</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* book 2 描述 */</span><br>
&nbsp; &nbsp;Book2<span style="color: #339933;">.</span>title <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"Python 教程"</span><br>
&nbsp; &nbsp;Book2<span style="color: #339933;">.</span>author <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"www.runoob.com"</span><br>
&nbsp; &nbsp;Book2<span style="color: #339933;">.</span>subject <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"Python 语言教程"</span><br>
&nbsp; &nbsp;Book2<span style="color: #339933;">.</span>book_id <span style="color: #339933;">=</span> <span style="color: #cc66cc;">6495700</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 打印 Book1 信息 */</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book 1 title : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> Book1<span style="color: #339933;">.</span>title<span style="color: #339933;">)</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book 1 author : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> Book1<span style="color: #339933;">.</span>author<span style="color: #339933;">)</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book 1 subject : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> Book1<span style="color: #339933;">.</span>subject<span style="color: #339933;">)</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book 1 book_id : %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> Book1<span style="color: #339933;">.</span>book_id<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 打印 Book2 信息 */</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book 2 title : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> Book2<span style="color: #339933;">.</span>title<span style="color: #339933;">)</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book 2 author : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> Book2<span style="color: #339933;">.</span>author<span style="color: #339933;">)</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book 2 subject : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> Book2<span style="color: #339933;">.</span>subject<span style="color: #339933;">)</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book 2 book_id : %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> Book2<span style="color: #339933;">.</span>book_id<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>


<p>以上实例执行运行结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="typ">Book</span><span class="pln"> </span><span class="lit">1</span><span class="pln"> title </span><span class="pun">:</span><span class="pln"> </span><span class="typ">Go</span><span class="pln"> </span><span class="pun">语言</span><span class="pln">
</span><span class="typ">Book</span><span class="pln"> </span><span class="lit">1</span><span class="pln"> author </span><span class="pun">:</span><span class="pln"> www</span><span class="pun">.</span><span class="pln">runoob</span><span class="pun">.</span><span class="pln">com
</span><span class="typ">Book</span><span class="pln"> </span><span class="lit">1</span><span class="pln"> subject </span><span class="pun">:</span><span class="pln"> </span><span class="typ">Go</span><span class="pln"> </span><span class="pun">语言教程</span><span class="pln">
</span><span class="typ">Book</span><span class="pln"> </span><span class="lit">1</span><span class="pln"> book_id </span><span class="pun">:</span><span class="pln"> </span><span class="lit">6495407</span><span class="pln">
</span><span class="typ">Book</span><span class="pln"> </span><span class="lit">2</span><span class="pln"> title </span><span class="pun">:</span><span class="pln"> </span><span class="typ">Python</span><span class="pln"> </span><span class="pun">教程</span><span class="pln">
</span><span class="typ">Book</span><span class="pln"> </span><span class="lit">2</span><span class="pln"> author </span><span class="pun">:</span><span class="pln"> www</span><span class="pun">.</span><span class="pln">runoob</span><span class="pun">.</span><span class="pln">com
</span><span class="typ">Book</span><span class="pln"> </span><span class="lit">2</span><span class="pln"> subject </span><span class="pun">:</span><span class="pln"> </span><span class="typ">Python</span><span class="pln"> </span><span class="pun">语言教程</span><span class="pln">
</span><span class="typ">Book</span><span class="pln"> </span><span class="lit">2</span><span class="pln"> book_id </span><span class="pun">:</span><span class="pln"> </span><span class="lit">6495700</span></pre>

<hr>

<h2>结构体作为函数参数</h2>

<p>你可以像其他数据类型一样将结构体类型作为参数传递给函数。并以以上实例的方式访问结构体变量：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #b1b100; font-weight: bold;">type</span> Books <span style="color: #993333;">struct</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;title <span style="color: #993333;">string</span><br>
&nbsp; &nbsp;author <span style="color: #993333;">string</span><br>
&nbsp; &nbsp;subject <span style="color: #993333;">string</span><br>
&nbsp; &nbsp;book_id <span style="color: #993333;">int</span><br>
<span style="color: #339933;">}</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> Book1 Books &nbsp; &nbsp; &nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 声明 Book1 为 Books 类型 */</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> Book2 Books &nbsp; &nbsp; &nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 声明 Book2 为 Books 类型 */</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* book 1 描述 */</span><br>
&nbsp; &nbsp;Book1<span style="color: #339933;">.</span>title <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"Go 语言"</span><br>
&nbsp; &nbsp;Book1<span style="color: #339933;">.</span>author <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"www.runoob.com"</span><br>
&nbsp; &nbsp;Book1<span style="color: #339933;">.</span>subject <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"Go 语言教程"</span><br>
&nbsp; &nbsp;Book1<span style="color: #339933;">.</span>book_id <span style="color: #339933;">=</span> <span style="color: #cc66cc;">6495407</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* book 2 描述 */</span><br>
&nbsp; &nbsp;Book2<span style="color: #339933;">.</span>title <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"Python 教程"</span><br>
&nbsp; &nbsp;Book2<span style="color: #339933;">.</span>author <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"www.runoob.com"</span><br>
&nbsp; &nbsp;Book2<span style="color: #339933;">.</span>subject <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"Python 语言教程"</span><br>
&nbsp; &nbsp;Book2<span style="color: #339933;">.</span>book_id <span style="color: #339933;">=</span> <span style="color: #cc66cc;">6495700</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 打印 Book1 信息 */</span><br>
&nbsp; &nbsp;printBook<span style="color: #339933;">(</span>Book1<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 打印 Book2 信息 */</span><br>
&nbsp; &nbsp;printBook<span style="color: #339933;">(</span>Book2<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
<br>
<span style="color: #993333;">func</span> printBook<span style="color: #339933;">(</span> book Books <span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book title : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> book<span style="color: #339933;">.</span><span style="">title</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book author : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> book<span style="color: #339933;">.</span><span style="">author</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book subject : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> book<span style="color: #339933;">.</span><span style="">subject</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book book_id : %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> book<span style="color: #339933;">.</span><span style="">book_id</span><span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>


<p>以上实例执行运行结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="typ">Book</span><span class="pln"> title </span><span class="pun">:</span><span class="pln"> </span><span class="typ">Go</span><span class="pln"> </span><span class="pun">语言</span><span class="pln">
</span><span class="typ">Book</span><span class="pln"> author </span><span class="pun">:</span><span class="pln"> www</span><span class="pun">.</span><span class="pln">runoob</span><span class="pun">.</span><span class="pln">com
</span><span class="typ">Book</span><span class="pln"> subject </span><span class="pun">:</span><span class="pln"> </span><span class="typ">Go</span><span class="pln"> </span><span class="pun">语言教程</span><span class="pln">
</span><span class="typ">Book</span><span class="pln"> book_id </span><span class="pun">:</span><span class="pln"> </span><span class="lit">6495407</span><span class="pln">
</span><span class="typ">Book</span><span class="pln"> title </span><span class="pun">:</span><span class="pln"> </span><span class="typ">Python</span><span class="pln"> </span><span class="pun">教程</span><span class="pln">
</span><span class="typ">Book</span><span class="pln"> author </span><span class="pun">:</span><span class="pln"> www</span><span class="pun">.</span><span class="pln">runoob</span><span class="pun">.</span><span class="pln">com
</span><span class="typ">Book</span><span class="pln"> subject </span><span class="pun">:</span><span class="pln"> </span><span class="typ">Python</span><span class="pln"> </span><span class="pun">语言教程</span><span class="pln">
</span><span class="typ">Book</span><span class="pln"> book_id </span><span class="pun">:</span><span class="pln"> </span><span class="lit">6495700</span></pre>

<hr>

<h2>结构体指针</h2>

<p>你可以定义指向结构体的指针类似于其他指针变量，格式如下：</p>

<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> struct_pointer </span><span class="pun">*</span><span class="typ">Books</span></pre>

<p>以上定义的指针变量可以存储结构体变量的地址。查看结构体变量地址，可以将 &amp; 符号放置于结构体变量前：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">struct_pointer </span><span class="pun">=</span><span class="pln"> </span><span class="pun">&amp;</span><span class="typ">Book1</span></pre>

<p>使用结构体指针访问结构体成员，使用 "." 操作符：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">struct_pointer</span><span class="pun">.</span><span class="pln">title</span></pre>

<p>接下来让我们使用结构体指针重写以上实例，代码如下：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #b1b100; font-weight: bold;">type</span> Books <span style="color: #993333;">struct</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;title <span style="color: #993333;">string</span><br>
&nbsp; &nbsp;author <span style="color: #993333;">string</span><br>
&nbsp; &nbsp;subject <span style="color: #993333;">string</span><br>
&nbsp; &nbsp;book_id <span style="color: #993333;">int</span><br>
<span style="color: #339933;">}</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> Book1 Books &nbsp; &nbsp; &nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 声明 Book1 为 Books 类型 */</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> Book2 Books &nbsp; &nbsp; &nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 声明 Book2 为 Books 类型 */</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* book 1 描述 */</span><br>
&nbsp; &nbsp;Book1<span style="color: #339933;">.</span>title <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"Go 语言"</span><br>
&nbsp; &nbsp;Book1<span style="color: #339933;">.</span>author <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"www.runoob.com"</span><br>
&nbsp; &nbsp;Book1<span style="color: #339933;">.</span>subject <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"Go 语言教程"</span><br>
&nbsp; &nbsp;Book1<span style="color: #339933;">.</span>book_id <span style="color: #339933;">=</span> <span style="color: #cc66cc;">6495407</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* book 2 描述 */</span><br>
&nbsp; &nbsp;Book2<span style="color: #339933;">.</span>title <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"Python 教程"</span><br>
&nbsp; &nbsp;Book2<span style="color: #339933;">.</span>author <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"www.runoob.com"</span><br>
&nbsp; &nbsp;Book2<span style="color: #339933;">.</span>subject <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"Python 语言教程"</span><br>
&nbsp; &nbsp;Book2<span style="color: #339933;">.</span>book_id <span style="color: #339933;">=</span> <span style="color: #cc66cc;">6495700</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 打印 Book1 信息 */</span><br>
&nbsp; &nbsp;printBook<span style="color: #339933;">(</span>&amp;Book1<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp;<span style="color: #666666; font-style: italic;">/* 打印 Book2 信息 */</span><br>
&nbsp; &nbsp;printBook<span style="color: #339933;">(</span>&amp;Book2<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
<span style="color: #993333;">func</span> printBook<span style="color: #339933;">(</span> book <span style="color: #339933;">*</span>Books <span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book title : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> book<span style="color: #339933;">.</span><span style="">title</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book author : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> book<span style="color: #339933;">.</span><span style="">author</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book subject : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> book<span style="color: #339933;">.</span><span style="">subject</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Printf</span><span style="color: #339933;">(</span> <span style="color: #cc66cc;">"Book book_id : %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> book<span style="color: #339933;">.</span><span style="">book_id</span><span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>


<p>以上实例执行运行结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="typ">Book</span><span class="pln"> title </span><span class="pun">:</span><span class="pln"> </span><span class="typ">Go</span><span class="pln"> </span><span class="pun">语言</span><span class="pln">
</span><span class="typ">Book</span><span class="pln"> author </span><span class="pun">:</span><span class="pln"> www</span><span class="pun">.</span><span class="pln">runoob</span><span class="pun">.</span><span class="pln">com
</span><span class="typ">Book</span><span class="pln"> subject </span><span class="pun">:</span><span class="pln"> </span><span class="typ">Go</span><span class="pln"> </span><span class="pun">语言教程</span><span class="pln">
</span><span class="typ">Book</span><span class="pln"> book_id </span><span class="pun">:</span><span class="pln"> </span><span class="lit">6495407</span><span class="pln">
</span><span class="typ">Book</span><span class="pln"> title </span><span class="pun">:</span><span class="pln"> </span><span class="typ">Python</span><span class="pln"> </span><span class="pun">教程</span><span class="pln">
</span><span class="typ">Book</span><span class="pln"> author </span><span class="pun">:</span><span class="pln"> www</span><span class="pun">.</span><span class="pln">runoob</span><span class="pun">.</span><span class="pln">com
</span><span class="typ">Book</span><span class="pln"> subject </span><span class="pun">:</span><span class="pln"> </span><span class="typ">Python</span><span class="pln"> </span><span class="pun">语言教程</span><span class="pln">
</span><span class="typ">Book</span><span class="pln"> book_id </span><span class="pun">:</span><span class="pln"> </span><span class="lit">6495700</span></pre>			<!-- 其他扩展 -->
						
		