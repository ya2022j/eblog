
# Go 语言变量
<p>
变量来源于数学，是计算机语言中能储存计算结果或能表示值抽象概念。</p><p>变量可以通过变量名访问。</p>
<p>Go 语言变量名由字母、数字、下划线组成，其中首个字符不能为数字。</p>
<p>声明变量的一般形式是使用 var 关键字：</p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> identifier type</span></pre>
<p>可以一次声明多个变量：</p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> identifier1</span><span class="pun">,</span><span class="pln"> identifier2 type</span></pre>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">var</span> a <span style="color: #993333;">string</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"Runoob"</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Println<span style="color: #339933;">(</span>a<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">var</span> b<span style="color: #339933;">,</span> c <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">1</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">2</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Println<span style="color: #339933;">(</span>b<span style="color: #339933;">,</span> c<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>
<p>以上实例输出结果为：</p>
<pre class="prettyprint prettyprinted" style=""><span class="typ">Runoob</span><span class="pln">
</span><span class="lit">1</span><span class="pln"> </span><span class="lit">2</span></pre>

<h3>变量声明</h3>
<p><strong>第一种，指定变量类型，如果没有初始化，则变量默认为零值</strong>。</p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> v_name v_type
v_name </span><span class="pun">=</span><span class="pln"> value</span></pre>
<p>零值就是变量没有做初始化时系统默认设置的值。</p>
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
<br>
&nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// 声明一个变量并初始化</span><br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">var</span> a <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"RUNOOB"</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span>a<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// 没有初始化就为零值</span><br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">var</span> b <span style="color: #993333;">int</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Println<span style="color: #339933;">(</span>b<span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// bool 零值为 false</span><br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">var</span> c <span style="color: #993333;">bool</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Println<span style="color: #339933;">(</span>c<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>

<p>以上实例执行结果为：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">RUNOOB
</span><span class="lit">0</span><span class="pln">
</span><span class="kwd">false</span></pre>
<ul><li><p>数值类型（包括complex64/128）为 <strong>0</strong></p></li><li>
<p>布尔类型为 <strong>false</strong></p></li><li>
<p>字符串为 <strong>""</strong>（空字符串）</p></li>
<li><p>以下几种类型为 <strong>nil</strong>：</p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> a </span><span class="pun">*</span><span class="kwd">int</span><span class="pln">
</span><span class="kwd">var</span><span class="pln"> a </span><span class="pun">[]</span><span class="kwd">int</span><span class="pln">
</span><span class="kwd">var</span><span class="pln"> a map</span><span class="pun">[</span><span class="kwd">string</span><span class="pun">]</span><span class="pln"> </span><span class="kwd">int</span><span class="pln">
</span><span class="kwd">var</span><span class="pln"> a chan </span><span class="kwd">int</span><span class="pln">
</span><span class="kwd">var</span><span class="pln"> a func</span><span class="pun">(</span><span class="kwd">string</span><span class="pun">)</span><span class="pln"> </span><span class="kwd">int</span><span class="pln">
</span><span class="kwd">var</span><span class="pln"> a error </span><span class="com">// error 是接口</span></pre>
</li>
</ul>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">var</span> <span style="">i</span> <span style="color: #993333;">int</span><br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">var</span> f <span style="color: #993333;">float64</span><br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">var</span> b <span style="color: #993333;">bool</span><br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">var</span> s <span style="color: #993333;">string</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"%v %v %v %q<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> i<span style="color: #339933;">,</span> f<span style="color: #339933;">,</span> b<span style="color: #339933;">,</span> s<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>
<p>输出结果是：</p>
<pre class="prettyprint prettyprinted" style=""><span class="lit">0</span><span class="pln"> </span><span class="lit">0</span><span class="pln"> </span><span class="kwd">false</span><span class="pln"> </span><span class="str">""</span></pre>


<p><strong>第二种，根据值自行判定变量类型。</strong></p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> v_name </span><span class="pun">=</span><span class="pln"> value</span></pre>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">var</span> d <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">true</span><br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Println<span style="color: #339933;">(</span>d<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>
<p>输出结果是：</p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">true</span></pre>
<p><strong>第三种，如果变量已经使用 var 声明过了，再使用 <span class="marked">:=</span> 声明变量，就产生编译错误，格式：</strong></p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">v_name </span><span class="pun">:=</span><span class="pln"> value</span></pre>
<p>例如：</p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> intVal </span><span class="kwd">int</span><span class="pln"> 
intVal </span><span class="pun">:=</span><span class="lit">1</span><span class="pln"> </span><span class="com">// 这时候会产生编译错误，因为 intVal 已经声明，不需要重新声明</span></pre>
<p>直接使用下面的语句即可：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">intVal </span><span class="pun">:=</span><span class="pln"> </span><span class="lit">1</span><span class="pln"> </span><span class="com">// 此时不会产生编译错误，因为有声明新的变量，因为 := 是一个声明语句</span></pre>
<p><span class="marked">intVal := 1</span> 相等于：</p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> intVal </span><span class="kwd">int</span><span class="pln"> 
intVal </span><span class="pun">=</span><span class="lit">1</span><span class="pln"> </span></pre>
<p>可以将 var f string = "Runoob" 简写为 f := "Runoob"：</p>
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; f <span style="color: #339933;">:=</span> <span style="color: #cc66cc;">"Runoob"</span> <span style="color: #666666; font-style: italic;">// var f string = "Runoob"</span><br>
<br>
&nbsp; &nbsp; fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span>f<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>
<p>输出结果是：</p>
<pre class="prettyprint prettyprinted" style=""><span class="typ">Runoob</span></pre>

<h3>多变量声明</h3>
<pre class="prettyprint prettyprinted" style=""><span class="com">//类型相同多个变量, 非全局变量</span><span class="pln">
</span><span class="kwd">var</span><span class="pln"> vname1</span><span class="pun">,</span><span class="pln"> vname2</span><span class="pun">,</span><span class="pln"> vname3 type
vname1</span><span class="pun">,</span><span class="pln"> vname2</span><span class="pun">,</span><span class="pln"> vname3 </span><span class="pun">=</span><span class="pln"> v1</span><span class="pun">,</span><span class="pln"> v2</span><span class="pun">,</span><span class="pln"> v3

</span><span class="kwd">var</span><span class="pln"> vname1</span><span class="pun">,</span><span class="pln"> vname2</span><span class="pun">,</span><span class="pln"> vname3 </span><span class="pun">=</span><span class="pln"> v1</span><span class="pun">,</span><span class="pln"> v2</span><span class="pun">,</span><span class="pln"> v3 </span><span class="com">// 和 python 很像,不需要显示声明类型，自动推断</span><span class="pln">

vname1</span><span class="pun">,</span><span class="pln"> vname2</span><span class="pun">,</span><span class="pln"> vname3 </span><span class="pun">:=</span><span class="pln"> v1</span><span class="pun">,</span><span class="pln"> v2</span><span class="pun">,</span><span class="pln"> v3 </span><span class="com">// 出现在 := 左侧的变量不应该是已经被声明过的，否则会导致编译错误</span><span class="pln">


</span><span class="com">// 这种因式分解关键字的写法一般用于声明全局变量</span><span class="pln">
</span><span class="kwd">var</span><span class="pln"> </span><span class="pun">(</span><span class="pln">
    vname1 v_type1
    vname2 v_type2
</span><span class="pun">)</span></pre>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">var</span> x<span style="color: #339933;">,</span> y <span style="color: #993333;">int</span><br>
<span style="color: #b1b100; font-weight: bold;">var</span> <span style="color: #339933;">(</span> &nbsp;<span style="color: #666666; font-style: italic;">// 这种因式分解关键字的写法一般用于声明全局变量</span><br>
&nbsp; &nbsp; a <span style="color: #993333;">int</span><br>
&nbsp; &nbsp; b <span style="color: #993333;">bool</span><br>
<span style="color: #339933;">)</span><br>
<br>
<span style="color: #b1b100; font-weight: bold;">var</span> c<span style="color: #339933;">,</span> d <span style="color: #993333;">int</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">1</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">2</span><br>
<span style="color: #b1b100; font-weight: bold;">var</span> e<span style="color: #339933;">,</span> f <span style="color: #339933;">=</span> <span style="color: #cc66cc;">123</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">"hello"</span><br>
<br>
<span style="color: #666666; font-style: italic;">//这种不带声明格式的只能在函数体中出现</span><br>
<span style="color: #666666; font-style: italic;">//g, h := 123, "hello"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">(){</span><br>
&nbsp; &nbsp; g<span style="color: #339933;">,</span> h <span style="color: #339933;">:=</span> <span style="color: #cc66cc;">123</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">"hello"</span><br>
&nbsp; &nbsp; <span style="color: #000066;">println</span><span style="color: #339933;">(</span>x<span style="color: #339933;">,</span> y<span style="color: #339933;">,</span> a<span style="color: #339933;">,</span> b<span style="color: #339933;">,</span> c<span style="color: #339933;">,</span> d<span style="color: #339933;">,</span> e<span style="color: #339933;">,</span> f<span style="color: #339933;">,</span> g<span style="color: #339933;">,</span> h<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>

<p>以上实例执行结果为：</p>
<pre class="prettyprint prettyprinted" style=""><span class="lit">0</span><span class="pln"> </span><span class="lit">0</span><span class="pln"> </span><span class="lit">0</span><span class="pln"> </span><span class="kwd">false</span><span class="pln"> </span><span class="lit">1</span><span class="pln"> </span><span class="lit">2</span><span class="pln"> </span><span class="lit">123</span><span class="pln"> hello </span><span class="lit">123</span><span class="pln"> hello</span></pre>
<hr>
<h2>值类型和引用类型</h2>
<p>所有像 int、float、bool 和 string 这些基本类型都属于值类型，使用这些类型的变量直接指向存在内存中的值：</p>

<p>
当使用等号 <code>=</code> 将一个变量的值赋值给另一个变量时，如：<code>j = i</code>，实际上是在内存中将 i 的值进行了拷贝：
</p>
<p>
你可以通过 &amp;i 来获取变量 i 的内存地址，例如：0xf840000040（每次的地址都可能不一样）。
</p><p>值类型变量的值存储在堆中。</p><p>
内存地址会根据机器的不同而有所不同，甚至相同的程序在不同的机器上执行后也会有不同的内存地址。因为每台机器可能有不同的存储器布局，并且位置分配也可能不同。
</p><p>
更复杂的数据通常会需要使用多个字，这些数据一般使用引用类型保存。
</p><p>
一个引用类型的变量 r1 存储的是 r1 的值所在的内存地址（数字），或内存地址中第一个字所在的位置。
</p><p>
</p><p>
这个内存地址称之为指针，这个指针实际上也被存在另外的某一个值中。
</p><p>同一个引用类型的指针指向的多个字可以是在连续的内存地址中（内存布局是连续的），这也是计算效率最高的一种存储形式；也可以将这些字分散存放在内存中，每个字都指示了下一个字所在的内存地址。
</p><p>
当使用赋值语句 r2 = r1 时，只有引用（地址）被复制。
</p><p>
如果 r1 的值被改变了，那么这个值的所有引用都会指向被修改后的内容，在这个例子中，r2 也会受到影响。
</p>

<hr><h2>简短形式，使用 := 赋值操作符</h2><p>
我们知道可以在变量的初始化时省略变量的类型而由系统自动推断，声明语句写上 var 关键字其实是显得有些多余了，因此我们可以将它们简写为 a := 50 或 b := false。
</p><p>
a 和 b 的类型（int 和 bool）将由编译器自动推断。
</p><p>
这是使用变量的首选形式，但是它只能被用在函数体内，而不可以用于全局变量的声明与赋值。使用操作符 := 可以高效地创建一个新的变量，称之为初始化声明。</p>
<h3>注意事项</h3>
<p>
如果在相同的代码块中，我们不可以再次对于相同名称的变量使用初始化声明，例如：a := 20 就是不被允许的，编译器会提示错误 no new variables on left side of :=，但是 a = 20 是可以的，因为这是给相同的变量赋予一个新的值。
</p><p>
如果你在定义变量 a 之前使用它，则会得到编译错误 undefined: a。
</p><p>
如果你声明了一个局部变量却没有在相同的代码块中使用它，同样会得到编译错误，例如下面这个例子当中的变量 a：
</p>
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp;<span style="color: #b1b100; font-weight: bold;">var</span> a <span style="color: #993333;">string</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">"abc"</span><br>
&nbsp; &nbsp;fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span><span style="color: #cc66cc;">"hello, world"</span><span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div><p>
尝试编译这段代码将得到错误 <b>a declared but not used</b>。
</p><p>
此外，单纯地给 a 赋值也是不够的，这个值必须被使用，所以使用</p> <pre class="prettyprint prettyprinted" style=""><span class="pln">fmt</span><span class="pun">.</span><span class="typ">Println</span><span class="pun">(</span><span class="str">"hello, world"</span><span class="pun">,</span><span class="pln"> a</span><span class="pun">)</span></pre><p> 会移除错误。
</p><p>
但是全局变量是允许声明但不使用的。

同一类型的多个变量可以声明在同一行，如：
</p><pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> a</span><span class="pun">,</span><span class="pln"> b</span><span class="pun">,</span><span class="pln"> c </span><span class="kwd">int</span></pre><p>
多变量可以在同一行进行赋值，如：</p>
<pre class="prettyprint prettyprinted" style=""><span class="kwd">var</span><span class="pln"> a</span><span class="pun">,</span><span class="pln"> b </span><span class="kwd">int</span><span class="pln">
</span><span class="kwd">var</span><span class="pln"> c </span><span class="kwd">string</span><span class="pln">
a</span><span class="pun">,</span><span class="pln"> b</span><span class="pun">,</span><span class="pln"> c </span><span class="pun">=</span><span class="pln"> </span><span class="lit">5</span><span class="pun">,</span><span class="pln"> </span><span class="lit">7</span><span class="pun">,</span><span class="pln"> </span><span class="str">"abc"</span></pre>
<p>
上面这行假设了变量 a，b 和 c 都已经被声明，否则的话应该这样使用：
</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">a</span><span class="pun">,</span><span class="pln"> b</span><span class="pun">,</span><span class="pln"> c </span><span class="pun">:=</span><span class="pln"> </span><span class="lit">5</span><span class="pun">,</span><span class="pln"> </span><span class="lit">7</span><span class="pun">,</span><span class="pln"> </span><span class="str">"abc"</span></pre>
<p>
右边的这些值以相同的顺序赋值给左边的变量，所以 a 的值是 5， b 的值是 7，c 的值是 "abc"。
</p><p>
这被称为 并行 或 同时 赋值。
</p><p>
如果你想要交换两个变量的值，则可以简单地使用 <span class="marked">a, b = b, a</span>，两个变量的类型必须是相同。
</p><p>


空白标识符 _ 也被用于抛弃值，如值 5 在：_, b = 5, 7 中被抛弃。
</p><p>
_ 实际上是一个只写变量，你不能得到它的值。这样做是因为 Go 语言中你必须使用所有被声明的变量，但有时你并不需要使用从一个函数得到的所有返回值。
</p><p>
并行赋值也被用于当一个函数返回多个返回值时，比如这里的 val 和错误 err 是通过调用 Func1 函数同时得到：val, err = Func1(var1)。
</p>	
