## System
* <function><a id="systemthrottlercallspersecond"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">System_ThrottlerCallsPerSecond</span>() -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the number of allowed calls per second for the current throttler.  
**Returns**: The calls per second limit set by the Throttler. Returns double.MaxValue if no Throttler is present.  

</pre></function>
* <function><a id="systemisinmemory"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">System_IsInMemory</span>() -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the system is operating in memory mode.  
**Returns**: A boolean value indicating if the store configuration specifies an in\-memory mode.  

</pre></function>
* <function><a id="systemcompact"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_Compact</span>() -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Initiates a compaction process on the data store associated with the given loader context.
This operation reduces storage space and improves efficiency by optimizing stored data.  

</pre></function>
* <function><a id="systemimportfromfile"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_ImportFromFile</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> filepath) -> <span style="color:#87AF00">DataChangeType</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Imports data from a specified JSON file and applies import options through the given context.  
***filepath***: The path to the JSON file that should be imported.  
**Returns**: A DataChangeType indicating the result of the import operation.  

</pre></function>
* <function><a id="systemexporttofile"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_ExportToFile</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> filepath, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> indent = <span style="color:#5FAFAF; margin-right:1px">false</span>) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Exports the data from the provided LoaderContextData store to a specified file.  
***filepath***: The path of the file where the data should be exported.
***indent***: A boolean value indicating whether the exported data should be formatted with indentation.
Default is false, which results in no indentation.  

</pre></function>
* <function><a id="systemshutdowm"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_Shutdowm</span>() -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Initiates the shutdown process for the system by cancelling the 
ongoing operations linked to a specific shutdown token source. This 
function is protected and should be executed within contexts where
it&apos;s safe to invoke system\-level shutdown procedures.  

</pre></function>
* <function><a id="systeminfo"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_Info</span>() -> <span style="color:#87AF00">SystemInfo</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves system information including runtime statistics, memory usage,
disk status, and environment details. The method calculates CPU usage percentage
based on the current process&apos;s processor time relative to uptime, checks for degraded 
performance conditions (e.g., high CPU or memory usage), and gathers comprehensive 
data about the system&apos;s runtime environment, memory utilization, and available disk space.  
**Returns**: A SystemInfo object containing detailed information
about the current state of the system including uptime, CPU load, memory allocation,
garbage collection metrics, disk drive details, and environmental settings such as OS 
architecture and processor count.  

</pre></function>
