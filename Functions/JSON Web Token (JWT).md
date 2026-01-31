## JSON Web Token (JWT)
* <function><a id="encodejwt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EncodeJwt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> claims, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> secret) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Encodes a JSON Web Token (JWT) using the specified claims and secret key.
The token is composed of three parts: header, payload, and signature. 
The header specifies the algorithm (&quot;HS256&quot;) used for signing the JWT, 
while the payload contains the claims to be encoded in the JWT. 
Finally, the signature is generated using HMAC SHA\-256 with the secret key.  
***claims***: A dictionary of claims to include in the JWT.
***secret***: The secret key used for signing the JWT.  
**Returns**: A string representing the encoded JWT.  

</pre></function>
* <function><a id="decodejwt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DecodeJwt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> token, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> secret = <span style="color:#D70000; margin-right:1px">null</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> includeMetadata = <span style="color:#5FAFAF; margin-right:1px">false</span>) -> <span style="color:#87AF00">IDictionary\<string, object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Decodes a JWT (JSON Web Token) and validates its HMAC\-SHA256 signature using an optional secret.
Throws exceptions for invalid tokens or signatures. Optionally includes token metadata in the output.  
***token***: The JWT to decode.
***secret***: Optional secret key used to validate the signature (for HMAC\-SHA256).
***includeMetadata***: Whether to include the JWT header and signature as metadata in the returned dictionary.  
**Returns**: A dictionary containing the decoded JWT payload, optionally including header and signature metadata.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when the token is empty or null.  
**Type**: FormatException
**Description**: Thrown when the token does not have exactly three parts separated by dots.  
**Type**: NotSupportedException
**Description**: Thrown when the algorithm specified in the JWT header is not HS256.  
**Type**: CryptographicException
**Description**: Thrown when the signature of the token cannot be validated with the given secret.  

</pre></function>
* <function><a id="isjwt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsJwt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> token) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines if the provided string is a valid JWT (JSON Web Token).  
***token***: The token to be validated as a JWT.  
**Returns**: True if the token is a valid JWT; otherwise, false.  

</pre></function>
