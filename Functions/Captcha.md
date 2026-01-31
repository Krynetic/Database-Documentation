## Captcha
* <function><a id="createcaptcha"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CreateCaptcha</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length = <span style="color:#5FAFAF; margin-right:1px">6</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> width = <span style="color:#5FAFAF; margin-right:1px">200</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> height = <span style="color:#5FAFAF; margin-right:1px">70</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> ttlSeconds = <span style="color:#5FAFAF; margin-right:1px">300</span>) -> <span style="color:#87AF00">ValueTuple\<string, byte[]\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Creates a CAPTCHA challenge with the specified parameters.
&lt;/summary&gt;
&lt;returns&gt;A tuple containing the generated token and PNG image.&lt;/returns&gt;
&lt;param name=&quot;length&quot;&gt;The length of the CAPTCHA code. Defaults to 6.&lt;/param&gt;
&lt;param name=&quot;width&quot;&gt;The width of the CAPTCHA image. Defaults to 200 pixels.&lt;/param&gt;
&lt;param name=&quot;height&quot;&gt;The height of the CAPTCHA image. Defaults to 70 pixels.&lt;/param&gt;
&lt;param name=&quot;ttlSeconds&quot;&gt;The time\-to\-live (TTL) for the CAPTCHA in seconds. Defaults to 300.&lt;/param&gt;</pre></function>
* <function><a id="validatecaptcha"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ValidateCaptcha</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> token, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> userInput) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Validates a CAPTCHA token against the stored tokens.
&lt;/summary&gt;
&lt;param name=&quot;token&quot;&gt;The CAPTCHA token to validate.&lt;/param&gt;
&lt;param name=&quot;userInput&quot;&gt;The user&apos;s input string for comparison.&lt;/param&gt;
&lt;returns&gt;True if the token is valid, false otherwise.&lt;/returns&gt;</pre></function>
