## Date
* <function><a id="tounixtimeseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToUnixTimeSeconds</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset</span> dt) -> <span style="color:#5FAFAF">long</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a given DateTimeOffset to its Unix timestamp in seconds.
The Unix timestamp represents the number of seconds that have elapsed since 
00:00:00 UTC on 1 January 1970, not counting leap seconds.  
***dt***: The DateTimeOffset value to convert.  
**Returns**: A long integer representing the Unix timestamp in seconds.  

</pre></function>
* <function><a id="tounixtimemilliseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToUnixTimeMilliseconds</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset</span> dt) -> <span style="color:#5FAFAF">long</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the given DateTimeOffset to Unix time expressed in milliseconds.
Unix time is defined as the number of milliseconds that have elapsed since 00:00:00 UTC on January 1, 1970 (excluding leap seconds).  
***dt***: The DateTimeOffset value to convert.  
**Returns**: A long integer representing the number of milliseconds since the Unix epoch.  

</pre></function>
* <function><a id="fromunixtimeseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromUnixTimeSeconds</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">long</span> seconds) -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a Unix timestamp (seconds since January 1, 1970) to a 
DateTimeOffset value in the local time zone.  
***seconds***: The number of seconds that have elapsed since January 1, 1970.  
**Returns**: A DateTimeOffset object representing the equivalent date and time in the local time zone.  

</pre></function>
* <function><a id="fromunixtimemilliseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromUnixTimeMilliseconds</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">long</span> milliseconds) -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the specified Unix time in milliseconds to a DateTimeOffset value.  
***milliseconds***: The number of 100\-nanosecond intervals since January 1, 1970 (midnight UTC).  
**Returns**: A DateTimeOffset value that is equivalent to the specified Unix time in milliseconds.  
**Exceptions**:
**Type**: ArgumentOutOfRangeException
**Description**: Thrown when the input value represents a date earlier than January 1, 0001. \-OR\- Thrown when the input value represents a date later than December 31, 9999.  

</pre></function>
* <function><a id="nowprecise"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NowPrecise</span>() -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Provides the current date and time in UTC with high precision.  
**Returns**: A DateTimeOffset object representing the current date and time in Coordinated Universal Time (UTC).  

</pre></function>
* <function><a id="now"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Now</span>() -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the current date and time based on the loading options provided in the context.
This function returns a DateTimeOffset value representing &quot;now&quot; as defined within the context&apos;s 
LoadingOptions. It is used to ensure consistency in timing across different parts of an application 
or plugin system that share the same context configuration.  
**Returns**: A DateTimeOffset value representing the current date and time as specified by the context&apos;s LoadingOptions.NowShared property.  

</pre></function>
* <function><a id="nowntp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NowNtp</span>() -> <span style="color:#87AF00">Task\<DateTimeOffset\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the current network time from an NTP server asynchronously.  
**Returns**: A task that represents the asynchronous operation, and contains a DateTimeOffset object representing the current date and time as reported by the NTP server.  

</pre></function>
