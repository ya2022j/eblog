
# Go 语言循环语句

<p>在不少实际问题中有许多具有规律性的重复操作，因此在程序中就需要重复执行某些语句。</p>

<p>以下为大多编程语言循环程序的流程图：</p>


<p>Go 语言提供了以下几种类型循环处理语句：</p>

<table class="reference">
<thead>
<tr>
<th>循环类型 </th>
<th> 描述</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href="go-for-loop.html">for 循环</a> </td>
<td> 重复执行语句块</td>
</tr>
<tr>
<td><a href="/go/go-nested-loops.html">循环嵌套</a>  </td>
<td> 在 for 循环中嵌套一个或多个 for 循环</td>
</tr>
</tbody>
</table>


<hr>

<h2>循环控制语句</h2>

<p>循环控制语句可以控制循环体内语句的执行过程。</p>

<p>GO 语言支持以下几种循环控制语句：</p>

<table class="reference">
<thead>
<tr>
<th>控制语句 </th>
<th> 描述</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href="/go/go-break-statement.html">break 语句</a> </td>
<td> 经常用于中断当前 for 循环或跳出 switch 语句</td>
</tr>
<tr>
<td><a href="/go/go-continue-statement.html">continue 语句</a> </td>
<td> 跳过当前循环的剩余语句，然后继续进行下一轮循环。</td>
</tr>
<tr>
<td><a href="/go/go-goto-statement.html">goto 语句</a> </td>
<td> 将控制转移到被标记的语句。</td>
</tr>
</tbody>
</table>
<hr>

<h2>无限循环</h2>

<p>如果循环中条件语句永远不为 false 则会进行无限循环，我们可以通过 for 循环语句中只设置一个条件表达式来执行无限循环：</p>

<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #b1b100; font-weight: bold;">package</span> main<br>
<br>
<span style="color: #b1b100; font-weight: bold;">import</span> <span style="color: #cc66cc;">"fmt"</span><br>
<br>
<span style="color: #993333;">func</span> main<span style="color: #339933;">()</span> <span style="color: #339933;">{</span><br>
&nbsp; &nbsp; <span style="color: #b1b100; font-weight: bold;">for</span> <span style="color: #000000; font-weight: bold;">true</span> &nbsp;<span style="color: #339933;">{</span><br>
&nbsp; &nbsp; &nbsp; &nbsp; fmt<span style="color: #339933;">.</span>Printf<span style="color: #339933;">(</span><span style="color: #cc66cc;">"这是无限循环。<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">);</span><br>
&nbsp; &nbsp; <span style="color: #339933;">}</span><br>
<span style="color: #339933;">}</span><br>
</div></div>		
