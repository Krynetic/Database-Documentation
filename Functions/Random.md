## Random
* <function><a id="randombool"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomBool</span>() -> <span style="color:#5FAFAF">bool</span></function>
* <function><a id="randomint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomInt64</span>() -> <span style="color:#5FAFAF">long</span></function>
* <function><a id="randomuint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomUInt64</span>() -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a random unsigned 64\-bit integer using the underlying random number generator.
This function is marked as a plugin function and can be used to obtain random values for various purposes.  
**Returns**: A randomly generated 64\-bit unsigned integer.  

</pre></function>
* <function><a id="randomint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomInt32</span>() -> <span style="color:#5FAFAF">int</span></function>
* <function><a id="randomuint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomUInt32</span>() -> <span style="color:#5FAFAF">uint</span></function>
* <function><a id="randomint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomInt16</span>() -> <span style="color:#5FAFAF">short</span></function>
* <function><a id="randomuint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomUInt16</span>() -> <span style="color:#5FAFAF">ushort</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates and returns a random 16\-bit unsigned integer.  
**Returns**: A random ushort value.  

</pre></function>
* <function><a id="randomsbyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomSByte</span>() -> <span style="color:#5FAFAF">sbyte</span></function>
* <function><a id="randombyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomByte</span>() -> <span style="color:#5FAFAF">byte</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a random byte using the underlying random number generator.  

</pre></function>
* <function><a id="randomfloat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomFloat</span>() -> <span style="color:#5FAFAF">float</span></function>
* <function><a id="randomdouble"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomDouble</span>() -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates and returns a random double value using the underlying random number generator.  
**Returns**: A randomly generated double value.  

</pre></function>
* <function><a id="randomdecimal"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomDecimal</span>() -> <span style="color:#87AF00">decimal</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a random decimal number using a predefined random number generator.  
**Returns**: A randomly generated decimal value. The characteristics of the randomness depend on the implementation within rng.Decimal().  

</pre></function>
* <function><a id="randomstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomString</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a random string of the specified length using a predefined random number generator.  
***length***: The desired length of the generated random string.  
**Returns**: A randomly generated string with the given length. The content and characteristics of the randomness depend on the implementation within rng.String(length).  

</pre></function>
* <function><a id="randombytes"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomBytes</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> count) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates an array of random bytes with the specified length.  
***count***: The number of random bytes to generate.  
**Returns**: An array containing &apos;count&apos; randomly generated bytes.  

</pre></function>
* <function><a id="randomdatetime"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomDateTime</span>() -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates and returns a random DateTimeOffset with the current date and 
time offset set to zero. The function utilizes a pseudo\-random number generator 
to produce a random long value representing seconds since Unix epoch (1970\-01\-01T00:00:00Z).
This ensures that the returned DateTimeOffset is within plausible historical bounds.  
**Returns**: A random DateTimeOffset with an offset of zero.  

</pre></function>
