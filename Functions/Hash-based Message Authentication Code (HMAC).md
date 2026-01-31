## Hash-based Message Authentication Code (HMAC)
* <function><a id="hmacgenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMACGenerate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> algorithm = <span style="color:#D70000; margin-right:1px">"SHA256"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a Base64 encoded HMAC key for the specified algorithm.  
***algorithm***: The hashing algorithm to use for HMAC (e.g., &quot;SHA256&quot;).  
**Returns**: A string representing the Base64 encoded HMAC key.  

</pre></function>
* <function><a id="hmacsign"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMACSign</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> algorithm = <span style="color:#D70000; margin-right:1px">"SHA256"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Creates an HMAC (Hash\-based Message Authentication Code) signature for a given message using the specified key and algorithm.  
***message***: The input string message to be signed.
***base64Key***: The base64\-encoded secret key used for creating the HMAC signature.
***algorithm***: The hashing algorithm to use, with a default of &quot;SHA256&quot;.  
**Returns**: A base64\-encoded string representing the HMAC signature of the message.  
**Remarks**:
This function uses UTF\-8 encoding for converting the input message into bytes. 
It creates an HMAC using the specified or default algorithm and computes the hash of the input message bytes.
The computed hash is then converted to a base64 string and returned as the signature.
Ensure that the key provided in base64 format is correctly decoded to prevent errors during HMAC generation.  

</pre></function>
* <function><a id="hmacverify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMACVerify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Signature, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> algorithm = <span style="color:#D70000; margin-right:1px">"SHA256"</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Verifies if the provided Base64\-encoded HMAC signature matches the expected HMAC 
signature generated from the given message and key using the specified hash algorithm.  
***message***: The original message for which the HMAC signature is to be verified.
***base64Signature***: The Base64\-encoded HMAC signature to verify against the expected signature.
***base64Key***: The Base64\-encoded key used to generate the HMAC signature.
***algorithm***: The hash algorithm to use for generating the HMAC signature (default is &quot;SHA256&quot;).  
**Returns**: True if the provided signature matches the generated signature; otherwise, false.  

</pre></function>
