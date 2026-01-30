## JSON Web Token (JWT)
* <function><a id="encodejwt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EncodeJwt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> claims, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> secret) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Encodes a JSON Web Token (JWT) using the specified claims and secret key.
The token is composed of three parts: header, payload, and signature. 
The header specifies the algorithm (&quot;HS256&quot;) used for signing the JWT, 
while the payload contains the claims to be encoded in the JWT. 
Finally, the signature is generated using HMAC SHA\-256 with the secret key.
&lt;/summary&gt;
&lt;param name=&quot;claims&quot;&gt;A dictionary of claims to include in the JWT.&lt;/param&gt;
&lt;param name=&quot;secret&quot;&gt;The secret key used for signing the JWT.&lt;/param&gt;
&lt;returns&gt;A string representing the encoded JWT.&lt;/returns&gt;</pre></function>
* <function><a id="decodejwt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DecodeJwt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> token, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> secret = <span style="color:#D70000; margin-right:1px">null</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> includeMetadata = <span style="color:#5FAFAF; margin-right:1px">false</span>) -> <span style="color:#87AF00">IDictionary\<string, object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Decodes a JWT (JSON Web Token) and validates its HMAC\-SHA256 signature using an optional secret.
Throws exceptions for invalid tokens or signatures. Optionally includes token metadata in the output.
&lt;/summary&gt;
&lt;param name=&quot;token&quot;&gt;The JWT to decode.&lt;/param&gt;
&lt;param name=&quot;secret&quot;&gt;Optional secret key used to validate the signature (for HMAC\-SHA256).&lt;/param&gt;
&lt;param name=&quot;includeMetadata&quot;&gt;
Whether to include the JWT header and signature as metadata in the returned dictionary.
&lt;/param&gt;
&lt;returns&gt;A dictionary containing the decoded JWT payload, optionally including header and signature metadata.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when the token is empty or null.&lt;/exception&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown when the token does not have exactly three parts separated by dots.&lt;/exception&gt;
&lt;exception cref=&quot;NotSupportedException&quot;&gt;
Thrown when the algorithm specified in the JWT header is not HS256.
&lt;/exception&gt;
&lt;exception cref=&quot;CryptographicException&quot;&gt;Thrown when the signature of the token cannot be validated with the given secret.&lt;/exception&gt;</pre></function>
* <function><a id="isjwt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsJwt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> token) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines if the provided string is a valid JWT (JSON Web Token).
&lt;/summary&gt;
&lt;param name=&quot;token&quot;&gt;The token to be validated as a JWT.&lt;/param&gt;
&lt;returns&gt;True if the token is a valid JWT; otherwise, false.&lt;/returns&gt;</pre></function>
