## CSharp
* <function><a id="csharp"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">CSharp</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">CSharpScript</span>, <span style="color:#D75F00">Cs</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Evaluates C\# code using the CSharpScript runtime
&lt;/summary&gt;
&lt;example&gt;
&lt;code&gt;
{
&nbsp;&nbsp;&nbsp;&nbsp;&quot;input&quot;: {
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&quot;Globals.expression&quot;: &quot;$()&quot;,
&nbsp;&nbsp;&nbsp;&nbsp;},
&nbsp;&nbsp;&nbsp;&nbsp;&quot;code&quot;: &quot;&quot;&quot;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;using System; 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return 1234 \+ 5678;
&nbsp;&nbsp;&nbsp;&nbsp;&quot;&quot;&quot;,
&nbsp;&nbsp;&nbsp;&nbsp;&quot;result.expression&quot;: &quot;CSharp(code, input)&quot;
}
CSharp(
&lt;/code&gt;
&lt;/example&gt;
&lt;param name=&quot;code&quot;&gt;C\# code that should be executed&lt;/param&gt;
&lt;param name=&quot;input&quot;&gt;Configuration parameters when executing&lt;/param&gt;
&lt;returns&gt;Output from execution&lt;/returns&gt;</pre></function>
