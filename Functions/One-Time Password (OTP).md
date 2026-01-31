## One-Time Password (OTP)
* <function><a id="generatetotp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateTOTP</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset?</span> at = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a Time\-based One\-Time Password (TOTP) based on the provided secret key.  
***key***: The base32 encoded secret key used to generate the TOTP.
***at***: An optional DateTimeOffset representing the time for which the TOTP is calculated. 
If not specified, the current UTC time is used.  
**Returns**: A string representation of the 6\-digit TOTP code generated from the provided key and time.  

</pre></function>
* <function><a id="verifytotp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">VerifyTOTP</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> window = <span style="color:#5FAFAF; margin-right:1px">0</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Verifies a Time\-based One\-Time Password (TOTP) against the provided key and time window.  
***key***: The base32\-encoded secret key used to generate TOTP.
***code***: The TOTP code to be verified.
***window***: The number of past and future intervals (default is 0) to check for validity, where each interval is 30 seconds.  
**Returns**: True if the provided code matches a valid TOTP generated within the specified time window; otherwise, false.  

</pre></function>
* <function><a id="remainingtotpseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RemainingTOTPSeconds</span>() -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the remaining time in seconds until the next Time\-based One\-Time Password (TOTP) changes.
TOTPs are typically refreshed every 30 seconds, and this function computes how many seconds 
remain before the next refresh. This can be useful for applications requiring synchronization
or timing\-related operations based on TOTP intervals.  
**Returns**: An integer representing the number of seconds remaining until the next TOTP change.
The return value will be an integer between 0 and 29, inclusive.  

</pre></function>
