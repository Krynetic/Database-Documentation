## Multipurpose Internet Mail Extensions (MIME)
* <function><a id="getmimefromextension"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetMimeFromExtension</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> ext) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the MIME type associated with a given file extension.
&lt;/summary&gt;
&lt;param name=&quot;ext&quot;&gt;The file extension for which to retrieve the MIME type. Must not be null or whitespace.&lt;/param&gt;
&lt;returns&gt;A string representing the MIME type, or an empty string if the extension is null, whitespace, or has no associated MIME type.&lt;/returns&gt;</pre></function>
* <function><a id="getextensionfrommime"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetExtensionFromMime</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> mime) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the file extension associated with a given MIME type. If the MIME type is null, empty, or whitespace,
an empty string is returned. Otherwise, the method trims any leading or trailing whitespace from the input and 
attempts to find the first corresponding extension using the MimeTypes.GetMimeTypeExtensions method.
If no suitable extension is found, it defaults to &quot;.bin&quot;.
&lt;/summary&gt;
&lt;param name=&quot;mime&quot;&gt;The MIME type for which to retrieve the file extension.&lt;/param&gt;
&lt;returns&gt;A string representing the associated file extension or &quot;.bin&quot; if none are found; an empty string
if the input MIME type is null, empty, or only whitespace.&lt;/returns&gt;</pre></function>
