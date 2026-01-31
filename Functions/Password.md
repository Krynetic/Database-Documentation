## Password
* <function><a id="hashpassword"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HashPassword</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> iterations = <span style="color:#5FAFAF; margin-right:1px">150000</span>, <span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset?</span> expiresAt = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Hashes the provided password using PBKDF2 with a random salt and specified number of iterations.
Optionally sets an expiration time for the hash.  
***password***: The password to be hashed.
***iterations***: The number of iterations for the key derivation function. Defaults to Iterations constant if not provided.
***expiresAt***: An optional DateTimeOffset representing when the hash expires. If null, sets it to NoExpiration.  
**Returns**: A formatted string containing the iteration count, expiration time (or default), salt, and hashed key.  

</pre></function>
* <function><a id="verifypassword"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">VerifyPassword</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> hash, <span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset?</span> now = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Verifies whether a given password matches the provided hash and optionally checks for expiration.  
***password***: The plain text password to verify.
***hash***: The hashed string containing iterations, expiration time, salt, and expected hash.
***now***: Optional parameter representing the current date and time. Defaults to current UTC time if not provided.  
**Returns**: True if the password matches the hash and is within the valid expiration period; otherwise, false.  

</pre></function>
* <function><a id="passwordentropybits"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PasswordEntropyBits</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the entropy in bits of a given password based on its character set diversity and length.  
***password***: The input password whose entropy is to be calculated.  
**Returns**: The entropy value in bits, representing the unpredictability or randomness of the password.  

</pre></function>
* <function><a id="isstrongpassword"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsStrongPassword</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> minEntropyBits = <span style="color:#5FAFAF; margin-right:1px">80</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified password meets the minimum entropy requirement.  
***password***: The password to evaluate.
***minEntropyBits***: The minimum number of bits of entropy required for a strong password. 
Default is 80 bits.  
**Returns**: True if the password&apos;s entropy meets or exceeds the specified threshold; otherwise, false.  

</pre></function>
