## Secure String
* <function><a id="tosecurestring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToSecureString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Encrypts the specified input string using AES encryption and returns a secure string.
The method throws an exception if the input is null. It performs AES encryption with 
a 256\-bit key size, CBC mode, and PKCS7 padding. An HMAC\-SHA256 is computed over the IV 
concatenated with the cipher text to ensure integrity, and the final payload includes the
IV, cipher text, and MAC. Sensitive data buffers are cleared after use.
&lt;/summary&gt;
&lt;remarks&gt;
Set custom secret via ENV &apos;SECURE\_SECRET&apos;
&lt;/remarks&gt;
&lt;param name=&quot;input&quot;&gt;The input string to be encrypted.&lt;/param&gt;
&lt;returns&gt;A Base64 encoded string representing the encrypted data including the IV, 
cipher text, and HMAC\-SHA256 MAC.&lt;/returns&gt;</pre></function>
* <function><a id="fromsecurestring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromSecureString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> encrypted) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a Base64 encoded string that represents an encrypted and HMAC\-protected payload into its plaintext form.
This method performs decryption using AES with CBC mode and verifies the integrity of the data using HMAC\-SHA256.
&lt;/summary&gt;
&lt;param name=&quot;encrypted&quot;&gt;The Base64 encoded string containing the encrypted data, initialization vector (IV), 
and message authentication code (MAC). The input must not be null.&lt;/param&gt;
&lt;returns&gt;A string representing the decrypted plaintext content.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;Thrown when the input parameter &apos;encrypted&apos; is null.&lt;/exception&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown if the payload format is invalid or does not meet expected length requirements.&lt;/exception&gt;
&lt;exception cref=&quot;CryptographicException&quot;&gt;Thrown when the MAC verification fails, indicating potential data tampering.&lt;/exception&gt;</pre></function>
