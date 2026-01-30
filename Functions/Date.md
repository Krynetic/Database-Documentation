## Date
* <function><a id="tounixtimeseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToUnixTimeSeconds</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset</span> dt) -> <span style="color:#5FAFAF">long</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a given DateTimeOffset to its Unix timestamp in seconds.
The Unix timestamp represents the number of seconds that have elapsed since 
00:00:00 UTC on 1 January 1970, not counting leap seconds.
&lt;/summary&gt;
&lt;param name=&quot;dt&quot;&gt;The DateTimeOffset value to convert.&lt;/param&gt;
&lt;returns&gt;A long integer representing the Unix timestamp in seconds.&lt;/returns&gt;</pre></function>
* <function><a id="tounixtimemilliseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToUnixTimeMilliseconds</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset</span> dt) -> <span style="color:#5FAFAF">long</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the given DateTimeOffset to Unix time expressed in milliseconds.
Unix time is defined as the number of milliseconds that have elapsed since 00:00:00 UTC on January 1, 1970 (excluding leap seconds).
&lt;/summary&gt;
&lt;param name=&quot;dt&quot;&gt;The DateTimeOffset value to convert.&lt;/param&gt;
&lt;returns&gt;A long integer representing the number of milliseconds since the Unix epoch.&lt;/returns&gt;</pre></function>
* <function><a id="fromunixtimeseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromUnixTimeSeconds</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">long</span> seconds) -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a Unix timestamp (seconds since January 1, 1970) to a 
DateTimeOffset value in the local time zone.
&lt;/summary&gt;
&lt;param name=&quot;seconds&quot;&gt;The number of seconds that have elapsed since January 1, 1970.&lt;/param&gt;
&lt;returns&gt;A DateTimeOffset object representing the equivalent date and time in the local time zone.&lt;/returns&gt;</pre></function>
* <function><a id="fromunixtimemilliseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromUnixTimeMilliseconds</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">long</span> milliseconds) -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the specified Unix time in milliseconds to a &lt;see cref=&quot;DateTimeOffset&quot;/&gt; value.
&lt;/summary&gt;
&lt;param name=&quot;milliseconds&quot;&gt;The number of 100\-nanosecond intervals since January 1, 1970 (midnight UTC).&lt;/param&gt;
&lt;returns&gt;A &lt;see cref=&quot;DateTimeOffset&quot;/&gt; value that is equivalent to the specified Unix time in milliseconds.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentOutOfRangeException&quot;&gt;Thrown when the input value represents a date earlier than January 1, 0001. \-OR\- Thrown when the input value represents a date later than December 31, 9999.&lt;/exception&gt;</pre></function>
* <function><a id="nowprecise"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NowPrecise</span>() -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Provides the current date and time in UTC with high precision.
&lt;/summary&gt;
&lt;returns&gt;A &lt;see cref=&quot;DateTimeOffset&quot;/&gt; object representing the current date and time in Coordinated Universal Time (UTC).&lt;/returns&gt;</pre></function>
* <function><a id="now"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Now</span>() -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the current date and time based on the loading options provided in the context.
This function returns a DateTimeOffset value representing &quot;now&quot; as defined within the context&apos;s 
LoadingOptions. It is used to ensure consistency in timing across different parts of an application 
or plugin system that share the same context configuration.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The LoaderContextData containing information about loading options, including the shared current time.&lt;/param&gt;
&lt;returns&gt;A DateTimeOffset value representing the current date and time as specified by the context&apos;s LoadingOptions.NowShared property.&lt;/returns&gt;</pre></function>
* <function><a id="nowntp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NowNtp</span>() -> <span style="color:#87AF00">Task\<DateTimeOffset\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the current network time from an NTP server asynchronously.
&lt;/summary&gt;
&lt;returns&gt;A task that represents the asynchronous operation, and contains a &lt;see cref=&quot;DateTimeOffset&quot;/&gt; object representing the current date and time as reported by the NTP server.&lt;/returns&gt;</pre></function>
