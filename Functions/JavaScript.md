## JavaScript
* <function><a id="javascript"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">JavaScript</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">Js</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Evaluates Javascript code using the YantraJS runtime
&lt;/summary&gt;
&lt;example&gt;
&lt;code&gt;
{
&nbsp;&nbsp;&nbsp;&nbsp;&quot;code&quot;: &quot;&quot;&quot;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;function fib(n) {
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return n &lt;= 1 ? n : fib(n \- 1) \+ fib(n \- 2);
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return fib(7);
&nbsp;&nbsp;&nbsp;&nbsp;&quot;&quot;&quot;,
&nbsp;&nbsp;&nbsp;&nbsp;&quot;result.expression&quot;: &quot;JavaScript(code)&quot;
}
&lt;/code&gt;
&lt;/example&gt;
&lt;param name=&quot;code&quot;&gt;Javascript code that should be executed&lt;/param&gt;
&lt;param name=&quot;input&quot;&gt;Configuration parameters when executing&lt;/param&gt;
&lt;returns&gt;Output from execution&lt;/returns&gt;</pre></function>
