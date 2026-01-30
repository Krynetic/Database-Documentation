## Advanced Encryption Standard (AES)
* <function><a id="aesgenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AESGenerate</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySizeBits = <span style="color:#5FAFAF; margin-right:1px">256</span>) -> <span style="color:#87AF00">ValueTuple\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a new pair of AES Key and Initial Vector (IV)
&lt;/summary&gt;
&lt;param name=&quot;keySizeBits&quot;&gt;AES key size to be created&lt;/param&gt;
&lt;returns&gt;Key and IV pair&lt;/returns&gt;</pre></function>
* <function><a id="aesencrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AESEncrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> plaintext, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64IV) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Encrypts a given plaintext using AES encryption with the provided base64 key and IV.
&lt;/summary&gt;
&lt;param name=&quot;plaintext&quot;&gt;The text to be encrypted.&lt;/param&gt;
&lt;param name=&quot;base64Key&quot;&gt;The base64\-encoded AES key.&lt;/param&gt;
&lt;param name=&quot;base64IV&quot;&gt;The base64\-encoded IV.&lt;/param&gt;
&lt;returns&gt;The base64\-encoded encrypted ciphertext.&lt;/returns&gt;</pre></function>
* <function><a id="aesdecrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AESDecrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64CipherText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64IV) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Decrypts a base64\-encrypted data using the provided key and initialization vector.
&lt;/summary&gt;
&lt;param name=&quot;base64CipherText&quot;&gt;The encrypted base64 string.&lt;/param&gt;
&lt;param name=&quot;base64Key&quot;&gt;The base64\-encoded encryption key.&lt;/param&gt;
&lt;param name=&quot;base64IV&quot;&gt;The base64\-encoded initialization vector.&lt;/param&gt;
&lt;returns&gt;The decrypted AES data as a UTF8 string.&lt;/returns&gt;</pre></function>
