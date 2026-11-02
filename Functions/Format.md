## Format
* <function><a id="formatbytes"></a><b>fn</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">FormatBytes</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">long</span> bytes) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Formats a byte count using the largest appropriate binary unit
(B, KB, MB, GB, etc.), with one decimal place.  
***bytes***: The number of bytes to format. May be negative.  
**Returns**: A human\-readable representation of bytes,
for example &quot;1.5 KB&quot;, &quot;\-2.0 MB&quot;, or &quot;0.0 B&quot;.  
**Remarks**:
Uses binary multiples: 1 KB = 1024 B, 1 MB = 1024 KB, and so on.
Values are always scaled by their absolute size, so negative values
retain their sign while using the same unit as the corresponding
positive value.  

</pre></function>
