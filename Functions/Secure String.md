## Secure String
* <function><a id="tosecurestring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToSecureString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Encrypts the specified input string using AES encryption and returns a secure string.
The method throws an exception if the input is null. It performs AES encryption with 
a 256\-bit key size, CBC mode, and PKCS7 padding. An HMAC\-SHA256 is computed over the IV 
concatenated with the cipher text to ensure integrity, and the final payload includes the
IV, cipher text, and MAC. Sensitive data buffers are cleared after use.  
***input***: The input string to be encrypted.  
**Returns**: A Base64 encoded string representing the encrypted data including the IV, 
cipher text, and HMAC\-SHA256 MAC.  
**Remarks**:
Set custom secret via ENV &apos;SECURE\_SECRET&apos;  

</pre></function>
* <function><a id="fromsecurestring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromSecureString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> encrypted) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a Base64 encoded string that represents an encrypted and HMAC\-protected payload into its plaintext form.
This method performs decryption using AES with CBC mode and verifies the integrity of the data using HMAC\-SHA256.  
***encrypted***: The Base64 encoded string containing the encrypted data, initialization vector (IV), 
and message authentication code (MAC). The input must not be null.  
**Returns**: A string representing the decrypted plaintext content.  
**Exceptions**:
**Type**: ArgumentNullException
**Description**: Thrown when the input parameter &apos;encrypted&apos; is null.  
**Type**: FormatException
**Description**: Thrown if the payload format is invalid or does not meet expected length requirements.  
**Type**: CryptographicException
**Description**: Thrown when the MAC verification fails, indicating potential data tampering.  

</pre></function>
