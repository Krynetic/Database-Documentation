## JavaScript
* <function><a id="javascript"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">JavaScript</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">Js</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Evaluates Javascript code using the YantraJS runtime  
***code***: Javascript code that should be executed
***input***: Configuration parameters when executing  
**Returns**: Output from execution  
**Examples**:
{
&nbsp;&nbsp;&nbsp;&nbsp;&quot;code&quot;: &quot;&quot;&quot;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;function fib(n) {
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return n &lt;= 1 ? n : fib(n \- 1) \+ fib(n \- 2);
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return fib(7);
&nbsp;&nbsp;&nbsp;&nbsp;&quot;&quot;&quot;,
&nbsp;&nbsp;&nbsp;&nbsp;&quot;result.expression&quot;: &quot;JavaScript(code)&quot;
}  

</pre></function>
