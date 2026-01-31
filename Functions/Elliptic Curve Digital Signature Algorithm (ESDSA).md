## Elliptic Curve Digital Signature Algorithm (ESDSA)
* <function><a id="ecdsagenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ECDSAGenerate</span>() -> <span style="color:#87AF00">ValueTuple\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates an ECDSA key pair using the NIST P\-256 curve.  
**Returns**: A tuple containing the Base64\-encoded  

</pre></function>
* <function><a id="ecdsasign"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ECDSASign</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64PrivateKey) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Signs a message using the ECDSA algorithm with a provided  
***message***: The original message to be signed.
***base64PrivateKey***: The base64 encoded private key  

</pre></function>
* <function><a id="ecdsaverify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ECDSAVerify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Signature, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64PublicKey) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Verifies an ECDSA (Elliptic Curve Digital Signature Algorithm) signature for a given message.  
***message***: The original message that was signed.
***base64Signature***: The base64 encoded string representing the signature to be verified.
***base64PublicKey***: The base64 encoded public key  

</pre></function>
