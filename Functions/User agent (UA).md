## User agent (UA)
* <function><a id="parseuseragent"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUserAgent</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> userAgent) -> <span style="color:#87AF00">UserAgent</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a user agent string to extract information about the browser or device.
&lt;/summary&gt;
&lt;param name=&quot;userAgent&quot;&gt;The user agent string to be parsed.&lt;/param&gt;
&lt;returns&gt;A UserAgent object containing the name, version, and optionally platform type and name.&lt;/returns&gt;
&lt;exception cref=&quot;InvalidDataException&quot;&gt;
Thrown when the provided user agent string cannot be parsed and results in an unknown type with no identifiable information.
&lt;/exception&gt;</pre></function>
