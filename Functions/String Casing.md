## String Casing
* <function><a id="tolowercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToLowerCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">LowerCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the specified string to lowercase using culture\-invariant settings.  
***input***: The string to be converted to lowercase. Can be null or empty.  
**Returns**: A new string with all characters converted to lowercase, or the original input if it is null or empty.  

</pre></function>
* <function><a id="touppercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToUpperCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">UpperCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the specified string to uppercase using the current culture&apos;s TextInfo.  
***input***: The string to be converted to uppercase. If null or empty, returns as is.  
**Returns**: The uppercase representation of the input string, or the original input if it is null or empty.  

</pre></function>
* <function><a id="totitlecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToTitleCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">TitleCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the specified string to title case using invariant culture.
This method ensures that each word in the input string is capitalized,
while maintaining any existing casing for words that should remain unchanged.  
***input***: The string to convert to title case.  
**Returns**: A string with each word converted to title case. If the input is null or empty, returns the original input.  

</pre></function>
* <function><a id="tokebabcase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToKebabCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">KebabCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a given string to Kebab Case format. This involves replacing spaces and underscores with hyphens, converting uppercase letters to lowercase, and ensuring no consecutive hyphens are present. It handles null or empty input gracefully by returning the input as is  
***input***: The string to be converted to Kebab Case.  
**Returns**: A new string formatted in Kebab Case or the original input if it was null or empty.  

</pre></function>
* <function><a id="tocamelcase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToCamelCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">CamelCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a given string to CamelCase format. It transforms the input by 
capitalizing the first letter of each word while removing spaces and other 
whitespace characters, ensuring that only the initial character of the entire 
string is in lowercase unless it was originally uppercase.  
***input***: The string to convert to CamelCase.  
**Returns**: A new string in CamelCase format derived from the input. Returns 
the original string if it is null or empty.  

</pre></function>
* <function><a id="tosnakecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToSnakeCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">SnakeCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the provided input string from PascalCase or CamelCase to snake\_case.
The conversion involves replacing uppercase letters with underscores followed by their lowercase equivalents. 
Consecutive underscores are reduced to a single underscore, and any leading/trailing underscores are removed.  
***input***: The input string to convert.  
**Returns**: A new string in snake\_case format or the original input if it is null or empty.  

</pre></function>
* <function><a id="tosentencecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToSentenceCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">SentenceCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the first character of a given string to uppercase while converting all other characters in the string to lowercase.
If the input is null or empty, it returns the input unchanged.  
***input***: The string to be converted to sentence case.  
**Returns**: A new string with the first character capitalized and remaining characters in lowercase, or the original input if it&apos;s null or empty.  

</pre></function>
