## Random
* <function><a id="randombool"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomBool</span>() -> <span style="color:#5FAFAF">bool</span></function>
* <function><a id="randomint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomInt64</span>() -> <span style="color:#5FAFAF">long</span></function>
* <function><a id="randomuint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomUInt64</span>() -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a random unsigned 64\-bit integer using the underlying random number generator.
This function is marked as a plugin function and can be used to obtain random values for various purposes.
&lt;/summary&gt;
&lt;returns&gt;A randomly generated 64\-bit unsigned integer.&lt;/returns&gt;</pre></function>
* <function><a id="randomint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomInt32</span>() -> <span style="color:#5FAFAF">int</span></function>
* <function><a id="randomuint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomUInt32</span>() -> <span style="color:#5FAFAF">uint</span></function>
* <function><a id="randomint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomInt16</span>() -> <span style="color:#5FAFAF">short</span></function>
* <function><a id="randomuint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomUInt16</span>() -> <span style="color:#5FAFAF">ushort</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates and returns a random 16\-bit unsigned integer.
&lt;/summary&gt;
&lt;returns&gt;A random ushort value.&lt;/returns&gt;</pre></function>
* <function><a id="randomsbyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomSByte</span>() -> <span style="color:#5FAFAF">sbyte</span></function>
* <function><a id="randombyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomByte</span>() -> <span style="color:#5FAFAF">byte</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a random byte using the underlying random number generator.
&lt;/summary&gt;</pre></function>
* <function><a id="randomfloat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomFloat</span>() -> <span style="color:#5FAFAF">float</span></function>
* <function><a id="randomdouble"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomDouble</span>() -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates and returns a random double value using the underlying random number generator.
&lt;/summary&gt;
&lt;returns&gt;A randomly generated double value.&lt;/returns&gt;</pre></function>
* <function><a id="randomdecimal"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomDecimal</span>() -> <span style="color:#87AF00">decimal</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a random decimal number using a predefined random number generator.
&lt;/summary&gt;
&lt;returns&gt;A randomly generated decimal value. The characteristics of the randomness depend on the implementation within rng.Decimal().&lt;/returns&gt;</pre></function>
* <function><a id="randomstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomString</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a random string of the specified length using a predefined random number generator.
&lt;/summary&gt;
&lt;param name=&quot;length&quot;&gt;The desired length of the generated random string.&lt;/param&gt;
&lt;returns&gt;A randomly generated string with the given length. The content and characteristics of the randomness depend on the implementation within rng.String(length).&lt;/returns&gt;</pre></function>
* <function><a id="randombytes"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomBytes</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> count) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates an array of random bytes with the specified length.
&lt;/summary&gt;
&lt;param name=&quot;count&quot;&gt;The number of random bytes to generate.&lt;/param&gt;
&lt;returns&gt;An array containing &apos;count&apos; randomly generated bytes.&lt;/returns&gt;</pre></function>
* <function><a id="randomdatetime"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomDateTime</span>() -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates and returns a random &lt;see cref=&quot;DateTimeOffset&quot;/&gt; with the current date and 
time offset set to zero. The function utilizes a pseudo\-random number generator 
to produce a random long value representing seconds since Unix epoch (1970\-01\-01T00:00:00Z).
This ensures that the returned DateTimeOffset is within plausible historical bounds.
&lt;/summary&gt;
&lt;returns&gt;A random &lt;see cref=&quot;DateTimeOffset&quot;/&gt; with an offset of zero.&lt;/returns&gt;</pre></function>
