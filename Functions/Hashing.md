## Hashing
* <function><a id="crc32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CRC32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">uint</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the CRC\-32 hash of a given string using UTF\-8 encoding.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string for which to compute the CRC\-32 hash.&lt;/param&gt;
&lt;returns&gt;A uint representing the computed CRC\-32 hash value.&lt;/returns&gt;</pre></function>
* <function><a id="crc64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CRC64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the CRC\-64 checksum for a given input string.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string to calculate the checksum for.&lt;/param&gt;
&lt;returns&gt;An unsigned long representing the 64\-bit CRC checksum of the input string.&lt;/returns&gt;
&lt;remarks&gt;
This function uses UTF\-8 encoding to convert the input string into bytes and then computes the CRC\-64 hash.
&lt;/remarks&gt;</pre></function>
* <function><a id="xxhash32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">XXHash32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> seed = <span style="color:#5FAFAF; margin-right:1px">0</span>) -> <span style="color:#5FAFAF">uint</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes a 32\-bit hash value for the specified input string using the XXHash algorithm.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;param name=&quot;seed&quot;&gt;An optional seed value to initialize the hashing process. Default is 0.&lt;/param&gt;
&lt;returns&gt;A uint representing the computed hash value of the input string.&lt;/returns&gt;</pre></function>
* <function><a id="xxhash64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">XXHash64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">long</span> seed = <span style="color:#5FAFAF; margin-right:1px">0</span>) -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the XXH64 hash of a given input string using the specified seed value.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;param name=&quot;seed&quot;&gt;An optional seed value for the hash function. Defaults to 0 if not provided.&lt;/param&gt;
&lt;returns&gt;Returns the computed XXH64 hash as an unsigned long (ulong).&lt;/returns&gt;</pre></function>
* <function><a id="sha1"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA1</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the SHA\-1 hash for a given input string and returns it as a hexadecimal string.
This method utilizes the provided hashing function from the SHA1 class to ensure 
secure hashing of the specified value. The result is returned in a standard format 
suitable for verification or storage purposes. Usage involves passing the target 
string which will be hashed using the SHA\-1 algorithm, leveraging an external plugin 
mechanism.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to hash.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representation of the SHA\-1 hash of the input value.&lt;/returns&gt;</pre></function>
* <function><a id="sha256"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA256</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHA\-256 hash of the specified input string.
Utilizes a plugin function mechanism to apply the SHA\-256 hashing algorithm.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representing the SHA\-256 hash of the input.&lt;/returns&gt;</pre></function>
* <function><a id="sha512"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA512</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHA\-512 hash of a given input string.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representation of the SHA\-512 hash.&lt;/returns&gt;
&lt;remarks&gt;This method is marked as a plugin function for dynamic loading.&lt;/remarks&gt;</pre></function>
* <function><a id="md5"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">MD5</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the MD5 hash of a given input string.
This method utilizes a custom plugin function mechanism to process the string.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representing the MD5 hash of the input.&lt;/returns&gt;</pre></function>
* <function><a id="hmacsha256"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMAC_SHA256</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the HMAC\-SHA256 hash for a given key and value.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The secret key used in the hashing process.&lt;/param&gt;
&lt;param name=&quot;value&quot;&gt;The data to be hashed using the provided key.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representing the HMAC\-SHA256 hash of the input value.&lt;/returns&gt;</pre></function>
* <function><a id="hmacsha512"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMAC_SHA512</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the HMAC\-SHA512 hash for the given key and value.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The secret key used for hashing.&lt;/param&gt;
&lt;param name=&quot;value&quot;&gt;The input data to be hashed.&lt;/param&gt;
&lt;returns&gt;A string representation of the resulting HMAC\-SHA512 hash.&lt;/returns&gt;</pre></function>
