## Uniform Resource Locator (URL)
* <function><a id="parseuriquery"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUriQuery</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> uri) -> <span style="color:#87AF00">Dictionary\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the query parameters from a given URI and returns them as a dictionary.  
***uri***: The absolute URI containing query parameters to parse.  
**Returns**: A dictionary where each key is a parameter name and each value is the corresponding parameter value. 
If a parameter has no value, its entry in the dictionary will have an empty string as the value.  

</pre></function>
* <function><a id="parseuriparts"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUriParts</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> uriString) -> <span style="color:#87AF00">Dictionary\<string, object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the given URI string into its components and returns them as a dictionary.  
***uriString***: The URI string to be parsed.  
**Returns**: A dictionary containing the components of the URI such as scheme, host, port, path,
query, fragment, user info, absolute URI, segments, and whether it is an absolute URI. 
If the input is a relative URI, only the original string is treated as the path.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown if the provided URI string format is invalid or
if an unexpected error occurs during parsing.  

</pre></function>
