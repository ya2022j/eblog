
		
# Go 语言条件语句
<p>
条件语句需要开发者通过指定一个或多个条件，并通过测试条件是否为 true 来决定是否执行指定语句，并在条件为 false 的情况在执行另外的语句。</p>


<p>Go 语言提供了以下几种条件判断语句：</p>
<table class="reference">
<tbody><tr><th style="width:35%">语句</th><th>描述</th></tr>
<tr><td><a href="/go/go-if-statement.html" title="Go if 语句">if 语句</a></td><td><b>if 语句</b> 由一个布尔表达式后紧跟一个或多个语句组成。</td></tr>
<tr><td><a href="/go/go-if-else-statement.html" title="Go if...else 语句">if...else 语句</a></td><td><b>if 语句</b> 后可以使用可选的 <b>else 语句</b>, else 语句中的表达式在布尔表达式为 false 时执行。</td></tr>
<tr><td><a href="/go/go-nested-if-statements.html" title="Go if 嵌套语句"> if 嵌套语句</a></td><td>你可以在 <b>if</b> 或 <b>else if</b> 语句中嵌入一个或多个 <b>if</b> 或 <b>else if</b> 语句。</td></tr>
<tr><td><a href="/go/go-switch-statement.html" title="Go switch 语句">switch 语句</a></td><td><b>switch</b> 语句用于基于不同条件执行不同动作。</td></tr>
<tr><td><a href="/go/go-select-statement.html" title="Go select 语句">select 语句</a></td><td><b>select</b> 语句类似于 <b>switch</b> 语句，但是select会随机执行一个可运行的case。如果没有case可运行，它将阻塞，直到有case可运行。</td></tr>
</tbody></table>



<blockquote><p>注意：Go 没有三目运算符，所以不支持 <strong>?:</strong> 形式的条件判断。</p></blockquote>

	