## Validation
* <function><a id="isvalidemail"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsValidEmail</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> address) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Validates whether a given email address string is valid.  
***address***: The email address to validate.  
**Returns**: True if the email address is valid and not null; otherwise, false.  

</pre></function>
* <function><a id="isvalidphonenumber"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsValidPhoneNumber</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> number, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> defaultRegion = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines if the provided phone number is valid based on regional formatting rules.  
***number***: The phone number to be validated. If null, returns false.
***defaultRegion***: Optional region code used when no region is specified in the phone number; can also be null.  
**Returns**: True if the phone number is valid according to regional rules, otherwise false.  

</pre></function>
* <function><a id="iscreditcardinfovalid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsCreditCardInfoValid</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cardNo, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> expiryDate = <span style="color:#D70000; margin-right:1px">null</span>, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cvv = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines if the credit card information provided is valid.
Validates the credit card number, CVV, and expiry date according to specified patterns and conditions.  
***cardNo***: The credit card number as a string.
***expiryDate***: Optional. The expiry date of the credit card in &quot;MM/yyyy&quot; format.
***cvv***: Optional. The CVV code of the credit card.  
**Returns**: True if all provided credit card information is valid; otherwise, false.  

</pre></function>
* <function><a id="validatejson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ValidateJson</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> json, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> schema) -> <span style="color:#87AF00">Task\<bool\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Validates a JSON string against the provided JSON Schema.  
***json***: The JSON string to validate.
***schema***: The JSON schema in string format used for validation.  
**Returns**: A task that represents the asynchronous operation. The task result contains a boolean indicating whether the JSON is valid against the schema (true if valid, false otherwise).  

</pre></function>
* <function><a id="isurl"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsUrl</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Checks if the provided string is a valid absolute URL.  
***input***: The string to be checked as a potential URL.  
**Returns**: True if the input is a valid absolute URL, otherwise false.  

</pre></function>
* <function><a id="isnumeric"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsNumeric</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified string can be parsed as a numeric value.
Utilizes the double.TryParse method to check if the conversion is successful.  
***input***: The input string to evaluate for its numeric nature.  
**Returns**: true if the string represents a valid double; otherwise, false.  

</pre></function>
* <function><a id="isguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsGuid</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified string is a valid GUID.  
***input***: The string to check for being a valid GUID.  
**Returns**: True if the input string represents a valid GUID; otherwise, false.  

</pre></function>
