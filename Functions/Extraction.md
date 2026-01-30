## Extraction
* <function><a id="extractemails"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExtractEmails</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">List\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Extracts and returns a list of email addresses found within the specified input string using regular expressions.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The text from which to extract emails.&lt;/param&gt;
&lt;returns&gt;A list containing all email addresses identified in the input string.&lt;/returns&gt;</pre></function>
* <function><a id="extracturls"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExtractUrls</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">List\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Represents a plugin function that extracts URLs from the given input string.
This method uses regular expressions to identify and return a list of URL strings found in the input.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string from which URLs are extracted.&lt;/param&gt;
&lt;returns&gt;A list containing all URLs found within the input string. Returns an empty list if no URLs are found.&lt;/returns&gt;</pre></function>
* <function><a id="extractemailuser"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExtractEmailUser</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> email) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Extracts and returns the user portion of an email address.
&lt;/summary&gt;
&lt;param name=&quot;email&quot;&gt;The full email address from which to extract the user.&lt;/param&gt;
&lt;returns&gt;A string representing the user part before the &apos;@&apos; symbol, or an empty string if invalid or null.&lt;/returns&gt;</pre></function>
