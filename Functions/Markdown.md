## Markdown
* <function><a id="markdown"></a><b>fn</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Markdown</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> markdown) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts Markdown text to HTML using Markdig.  
***markdown***: The Markdown source text to convert. Cannot be null, empty, or whitespace.  
**Returns**: The Markdown input rendered as an HTML string.  
**Remarks**:
Uses a shared Markdig pipeline with advanced extensions enabled, including support for
tables, task lists, autolinks, footnotes, and definition lists.  
**Examples**:
string html = MarkdownPlugin.Markdown(&quot;\# Hello\\n\\nThis is **Markdown**.&quot;);
// html contains: Hello\\nThis is Markdown.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when markdown is null, empty, or consists only of whitespace.  

</pre></function>
