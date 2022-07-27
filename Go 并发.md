# Go 并发
<p>Go 语言支持并发，我们只需要通过 go 关键字来开启 goroutine 即可。</p>
<p>goroutine 是轻量级线程，goroutine 的调度是由 Golang 运行时进行管理的。</p>


<p>goroutine 语法格式：</p>

<pre class="prettyprint prettyprinted" style=""><span class="pln">go </span><span class="pun">函数名(</span><span class="pln"> </span><span class="pun">参数列表</span><span class="pln"> </span><span class="pun">)</span></pre>

<p>例如：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">go f</span><span class="pun">(</span><span class="pln">x</span><span class="pun">,</span><span class="pln"> y</span><span class="pun">,</span><span class="pln"> z</span><span class="pun">)</span></pre>

<p>开启一个新的 goroutine:</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">f</span><span class="pun">(</span><span class="pln">x</span><span class="pun">,</span><span class="pln"> y</span><span class="pun">,</span><span class="pln"> z</span><span class="pun">)</span></pre>


<p>Go 允许使用 go 语句开启一个新的运行期线程， 即 goroutine，以一个不同的、新创建的 goroutine 来执行一个函数。 同一个程序中的所有 goroutine 共享同一个地址空间。</p>


<div class="example"><h2 class="example">实例</h2><div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #339933;">(</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #cc66cc;">"fmt"</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #cc66cc;">"time"</span><br>
<span style="color: #339933;">)</span><br>
<br>
<span style="color: #993333;">func</span> say<span style="color: #339933;">(</span>s <span style="color: #993333;">string</span><span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">for</span> <span style="">i</span> <span style="color: #339933;">:=</span> <span style="color: #cc66cc;">0</span><span style="color: #339933;">;</span> <span style="">i</span> &lt; <span style="color: #cc66cc;">5</span><span style="color: #339933;">;</span> <span style="">i</span><span style="color: #339933;">++</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; time<span style="color: #339933;">.</span>Sleep<span style="color: #339933;">(</span><span style="color: #cc66cc;">100</span> <span style="color: #339933;">*</span> time<span style="color: #339933;">.</span>Millisecond<span style="color: #339933;">)</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Println<span style="color: #339933;">(</span>s<span style="color: #339933;">)</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #339933;">}</span><br>
<span style="color: #339933;">}</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">go</span> say<span style="color: #339933;">(</span><span style="color: #cc66cc;">"world"</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; say<span style="color: #339933;">(</span><span style="color: #cc66cc;">"hello"</span><span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>


<p>执行以上代码，你会看到输出的 hello 和 world 是没有固定先后顺序。因为它们是两个 goroutine 在执行：</p>


<pre class="prettyprint prettyprinted" style=""><span class="pln">world
hello
hello
world
world
hello
hello
world
world
hello</span></pre>

<hr>
<h2>通道（channel）</h2>

<p>通道（channel）是用来传递数据的一个数据结构。</p>
<p>通道可用于两个 goroutine 之间通过传递一个指定类型的值来同步运行和通讯。操作符 <code>&lt;-</code> 用于指定通道的方向，发送或接收。如果未指定方向，则为双向通道。</p>


<pre class="prettyprint prettyprinted" style=""><span class="pln">ch </span><span class="pun">&lt;-</span><span class="pln"> v    </span><span class="com">// 把 v 发送到通道 ch</span><span class="pln">
v </span><span class="pun">:=</span><span class="pln"> </span><span class="pun">&lt;-</span><span class="pln">ch  </span><span class="com">// 从 ch 接收数据</span><span class="pln">
           </span><span class="com">// 并把值赋给 v</span></pre>

<p>声明一个通道很简单，我们使用chan关键字即可，通道在使用前必须先创建：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">ch </span><span class="pun">:=</span><span class="pln"> make</span><span class="pun">(</span><span class="pln">chan </span><span class="kwd">int</span><span class="pun">)</span></pre>
<p>
<strong>注意</strong>：默认情况下，通道是不带缓冲区的。发送端发送数据，同时必须有接收端相应的接收数据。</p>


<p>以下实例通过两个 goroutine 来计算数字之和，在 goroutine 完成计算后，它会计算两个结果的和：</p>
<div class="example"><h2 class="example">实例</h2><div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> sum<span style="color: #339933;">(</span>s <span style="color: #339933;">[]</span><span style="color: #993333;">int</span><span style="color: #339933;">,</span> c <span style="color: #993333;">chan</span> <span style="color: #993333;">int</span><span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; sum <span style="color: #339933;">:=</span> <span style="color: #cc66cc;">0</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">for</span> _<span style="color: #339933;">,</span> v <span style="color: #339933;">:=</span> <span style="color: #b1b100; font-weight: bold;">range</span> s <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; sum <span style="color: #339933;">+=</span> v<br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #339933;">}</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; c &lt;<span style="color: #339933;">-</span> sum <span style="color: #666666; font-style: italic;">// 把 sum 发送到通道 c</span><br>
<span style="color: #339933;">}</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; s <span style="color: #339933;">:=</span> <span style="color: #339933;">[]</span><span style="color: #993333;">int</span><span style="color: #339933;">{</span><span style="color: #cc66cc;">7</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">2</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">8</span><span style="color: #339933;">,</span> <span style="color: #339933;">-</span><span style="color: #cc66cc;">9</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">4</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">0</span><span style="color: #339933;">}</span><br>
<br>
&nbsp; &nbsp; &nbsp; &nbsp; c <span style="color: #339933;">:=</span> <span style="color: #000066;">make</span><span style="color: #339933;">(</span><span style="color: #993333;">chan</span> <span style="color: #993333;">int</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">go</span> sum<span style="color: #339933;">(</span>s<span style="color: #339933;">[:</span><span style="color: #000066;">len</span><span style="color: #339933;">(</span>s<span style="color: #339933;">)</span><span style="color: #339933;">/</span><span style="color: #cc66cc;">2</span><span style="color: #339933;">],</span> c<span style="color: #339933;">)</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">go</span> sum<span style="color: #339933;">(</span>s<span style="color: #339933;">[</span><span style="color: #000066;">len</span><span style="color: #339933;">(</span>s<span style="color: #339933;">)</span><span style="color: #339933;">/</span><span style="color: #cc66cc;">2</span><span style="color: #339933;">:],</span> c<span style="color: #339933;">)</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; x<span style="color: #339933;">,</span> y <span style="color: #339933;">:=</span> &lt;<span style="color: #339933;">-</span>c<span style="color: #339933;">,</span> &lt;<span style="color: #339933;">-</span>c <span style="color: #666666; font-style: italic;">// 从通道 c 中接收</span><br>
<br>
&nbsp; &nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span>x<span style="color: #339933;">,</span> y<span style="color: #339933;">,</span> x<span style="color: #339933;">+</span>y<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>

<p>输出结果为：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pun">-</span><span class="lit">5</span><span class="pln"> </span><span class="lit">17</span><span class="pln"> </span><span class="lit">12</span></pre>


<h3>通道缓冲区</h3>

<p>通道可以设置缓冲区，通过 make 的第二个参数指定缓冲区大小：</p>
<pre class="prettyprint prettyprinted" style=""><span class="pln">ch </span><span class="pun">:=</span><span class="pln"> make</span><span class="pun">(</span><span class="pln">chan </span><span class="kwd">int</span><span class="pun">,</span><span class="pln"> </span><span class="lit">100</span><span class="pun">)</span></pre>



<p>带缓冲区的通道允许发送端的数据发送和接收端的数据获取处于异步状态，就是说发送端发送的数据可以放在缓冲区里面，可以等待接收端去获取数据，而不是立刻需要接收端去获取数据。</p>
<p>不过由于缓冲区的大小是有限的，所以还是必须有接收端来接收数据的，否则缓冲区一满，数据发送端就无法再发送数据了。</p>

<p><strong>注意</strong>：如果通道不带缓冲，发送方会阻塞直到接收方从通道中接收了值。如果通道带缓冲，发送方则会阻塞直到发送的值被拷贝到缓冲区内；如果缓冲区已满，则意味着需要等待直到某个接收方获取到一个值。接收方在有值可以接收之前会一直阻塞。</p>


<div class="example"><h2 class="example">实例</h2><div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// 这里我们定义了一个可以存储整数类型的带缓冲通道</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// 缓冲区大小为2</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; ch <span style="color: #339933;">:=</span> <span style="color: #000066;">make</span><span style="color: #339933;">(</span><span style="color: #993333;">chan</span> <span style="color: #993333;">int</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">2</span><span style="color: #339933;">)</span><br>
<br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// 因为 ch 是带缓冲的通道，我们可以同时发送两个数据</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// 而不用立刻需要去同步读取数据</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; ch &lt;<span style="color: #339933;">-</span> <span style="color: #cc66cc;">1</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; ch &lt;<span style="color: #339933;">-</span> <span style="color: #cc66cc;">2</span><br>
<br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// 获取这两个数据</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span><span style="color: #339933;">&lt;-</span>ch<span style="color: #339933;">)</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span><span style="">Println</span><span style="color: #339933;">(</span><span style="color: #339933;">&lt;-</span>ch<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
</div></div>
<p>执行输出结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="lit">1</span><span class="pln">
</span><span class="lit">2</span></pre>
<h3>Go 遍历通道与关闭通道</h3>

<p>Go 通过 range 关键字来实现遍历读取到的数据，类似于与数组或切片。格式如下：
</p>


<pre class="prettyprint prettyprinted" style=""><span class="pln">v</span><span class="pun">,</span><span class="pln"> ok </span><span class="pun">:=</span><span class="pln"> </span><span class="pun">&lt;-</span><span class="pln">ch</span></pre>


<p>如果通道接收不到数据后 ok 就为 false，这时通道就可以使用 <span class="marked">close()</span> 函数来关闭。</p>



<div class="example"><h2 class="example">实例</h2><div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #339933;">(</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #cc66cc;">"fmt"</span><br>
<span style="color: #339933;">)</span><br>
<br>
<span style="color: #993333;">func</span> fibonacci<span style="color: #339933;">(</span>n <span style="color: #993333;">int</span><span style="color: #339933;">,</span> c <span style="color: #993333;">chan</span> <span style="color: #993333;">int</span><span style="color: #339933;">)</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; x<span style="color: #339933;">,</span> y <span style="color: #339933;">:=</span> <span style="color: #cc66cc;">0</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">1</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">for</span> <span style="">i</span> <span style="color: #339933;">:=</span> <span style="color: #cc66cc;">0</span><span style="color: #339933;">;</span> <span style="">i</span> &lt; n<span style="color: #339933;">;</span> <span style="">i</span><span style="color: #339933;">++</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; c &lt;<span style="color: #339933;">-</span> x<br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; x<span style="color: #339933;">,</span> y <span style="color: #339933;">=</span> y<span style="color: #339933;">,</span> x<span style="color: #339933;">+</span>y<br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #339933;">}</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #000066;">close</span><span style="color: #339933;">(</span>c<span style="color: #339933;">)</span><br>
<span style="color: #339933;">}</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; c <span style="color: #339933;">:=</span> <span style="color: #000066;">make</span><span style="color: #339933;">(</span><span style="color: #993333;">chan</span> <span style="color: #993333;">int</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">10</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">go</span> fibonacci<span style="color: #339933;">(</span><span style="color: #000066;">cap</span><span style="color: #339933;">(</span>c<span style="color: #339933;">),</span> c<span style="color: #339933;">)</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// range 函数遍历每个从通道接收到的数据，因为 c 在发送完 10 个</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// 数据之后就关闭了通道，所以这里我们 range 函数在接收到 10 个数据</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// 之后就结束了。如果上面的 c 通道不关闭，那么 range 函数就不</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #666666; font-style: italic;">// 会结束，从而在接收第 11 个数据的时候就阻塞了。</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">for</span> <span style="">i</span> <span style="color: #339933;">:=</span> <span style="color: #b1b100; font-weight: bold;">range</span> c <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Println<span style="color: #339933;">(</span><span style="">i</span><span style="color: #339933;">)</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #339933;">}</span><br>
<span style="color: #339933;">}</span><br>
</div></div>

<p>执行输出结果为：</p>

<pre class="prettyprint prettyprinted" style=""><span class="lit">0</span><span class="pln">
</span><span class="lit">1</span><span class="pln">
</span><span class="lit">1</span><span class="pln">
</span><span class="lit">2</span><span class="pln">
</span><span class="lit">3</span><span class="pln">
</span><span class="lit">5</span><span class="pln">
</span><span class="lit">8</span><span class="pln">
</span><span class="lit">13</span><span class="pln">
</span><span class="lit">21</span><span class="pln">
</span><span class="lit">34</span></pre>


		