## Advanced Encryption Standard (AES)
* <function><a id="aesgenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AESGenerate</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySizeBits = <span style="color:#5FAFAF; margin-right:1px">256</span>) -> <span style="color:#87AF00">ValueTuple\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a new pair of AES Key and Initial Vector (IV)  
***keySizeBits***: AES key size to be created  
**Returns**: Key and IV pair  

</pre></function>
* <function><a id="aesencrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AESEncrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> plaintext, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64IV) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Encrypts a given plaintext using AES encryption with the provided base64 key and IV.  
***plaintext***: The text to be encrypted.
***base64Key***: The base64\-encoded AES key.
***base64IV***: The base64\-encoded IV.  
**Returns**: The base64\-encoded encrypted ciphertext.  

</pre></function>
* <function><a id="aesdecrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AESDecrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64CipherText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64IV) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Decrypts a base64\-encrypted data using the provided key and initialization vector.  
***base64CipherText***: The encrypted base64 string.
***base64Key***: The base64\-encoded encryption key.
***base64IV***: The base64\-encoded initialization vector.  
**Returns**: The decrypted AES data as a UTF8 string.  

</pre></function>
