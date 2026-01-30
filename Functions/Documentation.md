## Documentation
* <function><a id="documentationtyped"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DocumentationTyped</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> function) -> <span style="color:#87AF00">XmlDocumentation</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the typed XML documentation for a specified function.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The loader context data containing information required to locate the documentation.&lt;/param&gt;
&lt;param name=&quot;function&quot;&gt;The name of the function whose documentation is being retrieved.&lt;/param&gt;
&lt;returns&gt;The parsed XML documentation object corresponding to the given function, or null if not found.&lt;/returns&gt;</pre></function>
* <function><a id="documentation"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Documentation</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> function) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the XML documentation for a specified function within the given loader context data.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The context containing information about the loaded plugin or library.&lt;/param&gt;
&lt;param name=&quot;function&quot;&gt;The name of the function whose documentation is to be retrieved.&lt;/param&gt;
&lt;returns&gt;A string representing the raw XML documentation for the specified function, 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;or null if no documentation is found.&lt;/returns&gt;</pre></function>
