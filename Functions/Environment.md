## Environment
* <function><a id="getenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> defaultValue = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the value of an environment variable specified by the given key.  
***key***: The name of the environment variable to retrieve.
***defaultValue***: The default value to return if the environment variable is not found or its value is null.
This parameter is optional and defaults to null.  
**Returns**: The value of the environment variable as a string, or the specified default value
if the environment variable does not exist or has a null value.  
**Exceptions**:
**Type**: ArgumentNullException
**Description**: Thrown when the key argument is null or empty.  

</pre></function>
* <function><a id="getenvorthrow"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetEnvOrThrow</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the value of a specified environment variable or throws an exception if it is not set.  
***key***: The key of the environment variable to retrieve.  
**Returns**: The value of the specified environment variable.  
**Exceptions**:
**Type**: ArgumentNullException
**Description**: Thrown when the provided key is null or empty.  
**Type**: InvalidOperationException
**Description**: Thrown when the environment variable with the specified key is not set.  

</pre></function>
* <function><a id="hasenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HasEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Checks if a specified environment variable exists.  
***key***: The key of the environment variable to check.  
**Returns**: True if the environment variable with the given key exists and is not null; otherwise, false.  
**Exceptions**:
**Type**: ArgumentNullException
**Description**: Thrown when the provided key is null or empty.  

</pre></function>
* <function><a id="getallenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetAllEnv</span>() -> <span style="color:#87AF00">Dictionary\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves all environment variables as a dictionary with the variable names as keys and their corresponding values as strings.  
**Returns**: A dictionary where each key is an environment variable name (string) and each value is its associated value (string), or null if not set.  

</pre></function>
* <function><a id="expandenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExpandEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Expands any environment variables contained within the specified string.  
***value***: The input string that may contain environment variable references.  
**Returns**: A new string with all environment variables in &quot;value&quot; replaced by their corresponding values.  
**Exceptions**:
**Type**: ArgumentNullException
**Description**: Thrown when the provided value is null.  

</pre></function>
* <function><a id="setenv"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">SetEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Sets an environment variable for the current process.  
***key***: The name of the environment variable to set. Cannot be null or empty.
***value***: The value of the environment variable. Can be null, which removes any existing value for the key.  
**Exceptions**:
**Type**: ArgumentNullException
**Description**: Thrown when the key is null or an empty string.  

</pre></function>
* <function><a id="clearenv"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">ClearEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Clears the environment variable specified by the given key. If the key exists in the environment variables, 
it is removed by setting its value to null.  
***key***: The name of the environment variable to clear.  

</pre></function>
