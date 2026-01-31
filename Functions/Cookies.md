## Cookies
* <function><a id="parsecookie"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseCookie</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cookie) -> <span style="color:#87AF00">Dictionary\<string, object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a cookie string into a dictionary of key\-value pairs, where values are dynamically typed objects.  
***cookie***: The cookie string to parse.  
**Returns**: A dictionary containing the parsed key\-value pairs from the cookie string. The keys are strings and
        the values can be of type null, bool, int, long, double, DateTime, Guid, or string, depending on their format in the input.
        If the input is empty or null, an empty dictionary with case\-insensitive string comparison for keys is returned.  

</pre></function>
* <function><a id="createcookie"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CreateCookie</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> data) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Creates a cookie string from the provided key\-value pairs in the data dictionary.
Each key and value pair is concatenated with an &apos;=&apos; character, and multiple
pairs are separated by &apos;; &apos;. If the input dictionary contains no elements, an empty string is returned.  
***data***: A dictionary containing cookie name and values as key\-value pairs.  
**Returns**: A string representing a formatted cookie with all provided data.  

</pre></function>
