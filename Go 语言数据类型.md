
# Go 语言数据类型
<p>
在 Go 编程语言中，数据类型用于声明函数和变量。</p>
<p>
数据类型的出现是为了把数据分成所需内存大小不同的数据，编程的时候需要用大数据的时候才需要申请大内存，就可以充分利用内存。</p>
<p>Go 语言按类别有以下几种数据类型：</p>
<table class="reference">
<tbody><tr><th>序号</th><th>类型和描述</th></tr>
<tr><td>1</td><td><b>布尔型</b><br>布尔型的值只可以是常量 true 或者 false。一个简单的例子：var b bool = true。</td></tr>
<tr><td>2</td><td><b>数字类型</b><br>整型 int 和浮点型 float32、float64，Go 语言支持整型和浮点型数字，并且支持复数，其中位的运算采用补码。</td></tr>
<tr><td>3</td><td><b>字符串类型:</b><br>字符串就是一串固定长度的字符连接起来的字符序列。Go 的字符串是由单个字节连接起来的。Go 语言的字符串的字节使用 UTF-8 编码标识 Unicode 文本。</td></tr>
<tr><td>4</td><td><b>派生类型:</b><br>包括：<ul><li> (a) 指针类型（Pointer）</li><li>(b) 数组类型</li><li> (c) 结构化类型(struct)</li><li> (d) Channel 类型</li><li> (e) 函数类型 </li><li>(f) 切片类型 </li><li>(g) 接口类型（interface）</li><li> (h) Map 类型 </li></ul></td></tr>
</tbody></table>
<hr><h2>数字类型</h2>
<p>
Go 也有基于架构的类型，例如：int、uint 和 uintptr。</p>

<table class="reference">
<tbody><tr><th>序号</th><th>类型和描述</th></tr>
<tr><td>1</td><td><b>uint8</b><br>无符号 8 位整型 (0 到 255)</td></tr>
<tr><td>2</td><td><b>uint16</b><br>无符号 16 位整型 (0 到 65535)</td></tr>
<tr><td>3</td><td><b>uint32</b><br>无符号 32 位整型 (0 到 4294967295)</td></tr>
<tr><td>4</td><td><b>uint64</b><br>无符号 64 位整型 (0 到 18446744073709551615)</td></tr>
<tr><td>5</td><td><b>int8</b><br>有符号 8 位整型 (-128 到 127)</td></tr>
<tr><td>6</td><td><b>int16</b><br>有符号 16 位整型 (-32768 到 32767)</td></tr>
<tr><td>7</td><td><b>int32</b><br>有符号 32 位整型 (-2147483648 到 2147483647)</td></tr>
<tr><td>8</td><td><b>int64</b><br>有符号 64 位整型 (-9223372036854775808 到 9223372036854775807)</td></tr>
</tbody></table>
<h3>浮点型</h3>

<table class="reference">
<tbody><tr><th>序号</th><th>类型和描述</th></tr>
<tr><td>1</td><td><b>float32</b><br>IEEE-754 32位浮点型数</td></tr>
<tr><td>2</td><td><b>float64</b><br>IEEE-754 64位浮点型数</td></tr>
<tr><td>3</td><td><b>complex64</b><br>32 位实数和虚数</td></tr>
<tr><td>4</td><td><b>complex128</b><br>64 位实数和虚数</td></tr>
</tbody></table>
<hr>
<h2>其他数字类型</h2>
<p>以下列出了其他更多的数字类型：</p>
<table class="reference">
<tbody><tr><th>序号</th><th>类型和描述</th></tr>
<tr><td>1</td><td><b>byte</b><br>类似 uint8</td></tr>
<tr><td>2</td><td><b>rune</b><br>类似 int32</td></tr>
<tr><td>3</td><td><b>uint</b><br>32 或 64 位</td></tr>
<tr><td>4</td><td><b>int</b><br>与 uint 一样大小</td></tr>
<tr><td>5</td><td><b>uintptr</b><br>无符号整型，用于存放一个指针</td></tr>
</tbody></table>







