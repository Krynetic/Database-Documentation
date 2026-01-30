## Roman Numerals
* <function><a id="toromannumeral"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToRomanNumeral</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> number) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts an integer to its corresponding Roman numeral representation.
This function does not support negative numbers and returns &quot;N&quot; for zero.
&lt;/summary&gt;
&lt;param name=&quot;number&quot;&gt;The integer value to convert.&lt;/param&gt;
&lt;returns&gt;A string representing the Roman numeral equivalent of the input number.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentOutOfRangeException&quot;&gt;
Thrown when a negative number is provided, as Roman numerals do not support negatives.
&lt;/exception&gt;</pre></function>
* <function><a id="fromromannumeral"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromRomanNumeral</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> roman) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a Roman numeral string to its corresponding integer value.
&lt;/summary&gt;
&lt;param name=&quot;roman&quot;&gt;The Roman numeral string to convert. The input should be in uppercase and 
can optionally contain whitespace which will be ignored.&lt;/param&gt;
&lt;returns&gt;The integer representation of the given Roman numeral.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when the input Roman numeral string is empty or contains only whitespace.&lt;/exception&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown when the input contains invalid characters that do not 
correspond to any Roman numeral symbols in SymbolMap.&lt;/exception&gt;</pre></function>
