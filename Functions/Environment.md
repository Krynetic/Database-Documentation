## Environment
* <function><a id="getenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> defaultValue = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the value of an environment variable specified by the given key.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The name of the environment variable to retrieve.&lt;/param&gt;
&lt;param name=&quot;defaultValue&quot;&gt;
The default value to return if the environment variable is not found or its value is null.
This parameter is optional and defaults to null.
&lt;/param&gt;
&lt;returns&gt;The value of the environment variable as a string, or the specified default value
if the environment variable does not exist or has a null value.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;Thrown when the key argument is null or empty.&lt;/exception&gt;</pre></function>
* <function><a id="getenvorthrow"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetEnvOrThrow</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the value of a specified environment variable or throws an exception if it is not set.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The key of the environment variable to retrieve.&lt;/param&gt;
&lt;returns&gt;The value of the specified environment variable.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;
Thrown when the provided key is null or empty.
&lt;/exception&gt;
&lt;exception cref=&quot;InvalidOperationException&quot;&gt;
Thrown when the environment variable with the specified key is not set.
&lt;/exception&gt;</pre></function>
* <function><a id="hasenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HasEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Checks if a specified environment variable exists.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The key of the environment variable to check.&lt;/param&gt;
&lt;returns&gt;True if the environment variable with the given key exists and is not null; otherwise, false.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;Thrown when the provided key is null or empty.&lt;/exception&gt;</pre></function>
* <function><a id="getallenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetAllEnv</span>() -> <span style="color:#87AF00">Dictionary\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves all environment variables as a dictionary with the variable names as keys and their corresponding values as strings.
&lt;/summary&gt;
&lt;returns&gt;A dictionary where each key is an environment variable name (string) and each value is its associated value (string), or null if not set.&lt;/returns&gt;</pre></function>
* <function><a id="expandenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExpandEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Expands any environment variables contained within the specified string.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string that may contain environment variable references.&lt;/param&gt;
&lt;returns&gt;A new string with all environment variables in &quot;value&quot; replaced by their corresponding values.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;Thrown when the provided value is null.&lt;/exception&gt;</pre></function>
* <function><a id="setenv"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">SetEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Sets an environment variable for the current process.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The name of the environment variable to set. Cannot be null or empty.&lt;/param&gt;
&lt;param name=&quot;value&quot;&gt;The value of the environment variable. Can be null, which removes any existing value for the key.&lt;/param&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;
Thrown when the &lt;paramref name=&quot;key&quot;/&gt; is null or an empty string.
&lt;/exception&gt;</pre></function>
* <function><a id="clearenv"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">ClearEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Clears the environment variable specified by the given key. If the key exists in the environment variables, 
it is removed by setting its value to null.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The name of the environment variable to clear.&lt;/param&gt;</pre></function>
