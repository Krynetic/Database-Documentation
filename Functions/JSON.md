## JSON
* <function><a id="tojson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToJSON</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> obj, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> indented) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Serializes an object to a JSON string with optional indentation.
&lt;/summary&gt;
&lt;param name=&quot;obj&quot;&gt;The object to serialize. Can be null.&lt;/param&gt;
&lt;param name=&quot;indented&quot;&gt;
A boolean indicating whether the output JSON should be indented for readability.
If true, the resulting JSON will include whitespace and line breaks.
If false, the resulting JSON will be compact without unnecessary spaces or newlines.
&lt;/param&gt;
&lt;returns&gt;A string representation of the serialized object in JSON format. Returns null if the input object is null.&lt;/returns&gt;</pre></function>
* <function><a id="formatjson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FormatJSON</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> json, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> indented = <span style="color:#5FAFAF; margin-right:1px">true</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Formats a JSON string with optional indentation.
&lt;/summary&gt;
&lt;param name=&quot;json&quot;&gt;The JSON string to format. Can be null.&lt;/param&gt;
&lt;param name=&quot;indented&quot;&gt;A boolean indicating whether the output should be indented for readability. Default is true.&lt;/param&gt;
&lt;returns&gt;A formatted JSON string if input is valid; otherwise, null.&lt;/returns&gt;</pre></function>
* <function><a id="parsejson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseJSON</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> json) -> <span style="color:#87AF00">object</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a JSON string and deserializes it into an object.
&lt;/summary&gt;
&lt;param name=&quot;json&quot;&gt;The JSON string to parse.&lt;/param&gt;
&lt;returns&gt;An object representing the deserialized data from the input JSON, or null if the input is null.&lt;/returns&gt;</pre></function>
