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
* <function><a id="getcookievalue"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetCookieValue</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cookie, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">object</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the value of a specific cookie key from a cookie string.  
***cookie***: The full cookie string to search.
***key***: The cookie key whose value should be retrieved.  
**Returns**: The value associated with the specified cookie key if found; otherwise, null.
The returned value may be of type bool, int, long, double, DateTime, Guid, or string.  

</pre></function>
* <function><a id="setcookievalue"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SetCookieValue</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cookie, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Sets or updates a cookie key with the specified value and returns the updated cookie string.  
***cookie***: The original cookie string.
***key***: The cookie key to set or update.
***value***: The value to assign to the cookie key.  
**Returns**: A new cookie string containing the updated key\-value pair.  

</pre></function>
* <function><a id="removecookiekey"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RemoveCookieKey</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cookie, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Removes a specific cookie key from a cookie string.  
***cookie***: The original cookie string.
***key***: The cookie key to remove.  
**Returns**: A new cookie string with the specified key removed.  

</pre></function>
* <function><a id="hascookiekey"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HasCookieKey</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cookie, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether a specific cookie key exists within a cookie string.  
***cookie***: The cookie string to inspect.
***key***: The cookie key to check for existence.  
**Returns**: true if the specified key exists; otherwise, false.  

</pre></function>
* <function><a id="mergecookies"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">MergeCookies</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> baseCookie, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> overrideCookie) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Merges two cookie strings, where values from the override cookie replace values
from the base cookie when keys collide.  
***baseCookie***: The base cookie string.
***overrideCookie***: The cookie string whose values take precedence.  
**Returns**: A merged cookie string containing keys from both inputs.  

</pre></function>
* <function><a id="cookiecount"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CookieCount</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cookie) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Counts the number of distinct cookie key\-value pairs in a cookie string.  
***cookie***: The cookie string to analyze.  
**Returns**: The total number of parsed cookie entries.  

</pre></function>
