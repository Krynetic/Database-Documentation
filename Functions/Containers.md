## Containers
* <function><a id="container"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Container</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> containerName, <span style="color:#87AF00; margin-left:1px; margin-right:1px">param string[]</span> command) -> <span style="color:#87AF00">Task\<object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Executes a command within the specified container asynchronously.  
***containerName***: The name of the container to execute the command in.
***command***: An array of strings representing the command and its arguments to be executed.  
**Returns**: A task that represents the asynchronous operation. The task result contains an anonymous object with properties: StandardOutput, StandardError, ExitCode if successful; otherwise, a string message indicating the container does not exist.  

</pre></function>
