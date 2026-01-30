## Large Language Model (LLM)
* <function><a id="ailmstudio"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AI_LMStudio</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> prompt, <span style="color:#87AF00; margin-left:1px; margin-right:1px">LMStudioConfig</span> config) -> <span style="color:#87AF00">Task\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Asynchronously communicates with the LMStudio AI model to generate a chat completion response.
The function creates and sends a request using specified configurations, then returns the generated content as a string.
&lt;/summary&gt;
&lt;param name=&quot;prompt&quot;&gt;The user input prompt for the AI model.&lt;/param&gt;
&lt;param name=&quot;config&quot;&gt;
Configuration settings for the LMStudioClient, including endpoint URL, model type, maximum tokens,
and temperature. The configuration cannot be null.
&lt;/param&gt;
&lt;returns&gt;A task representing the asynchronous operation, which upon completion provides a string
containing the AI\-generated response based on the given prompt.&lt;/returns&gt;</pre></function>
* <function><a id="aiopenai"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AI_OpenAI</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> prompt, <span style="color:#87AF00; margin-left:1px; margin-right:1px">OpenAIConfig</span> config) -> <span style="color:#87AF00">Task\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Asynchronously interacts with OpenAI&apos;s API to generate a response based on the provided prompt.
Utilizes configuration settings for API key or endpoint, model specification,
and various other parameters such as maximum tokens and temperature for generation.
&lt;/summary&gt;
&lt;param name=&quot;prompt&quot;&gt;The user input string prompting the AI for a specific task.&lt;/param&gt;
&lt;param name=&quot;config&quot;&gt;Configuration object containing OpenAI API details like API key, model type,
endpoint URI, max tokens limit, and temperature settings.&lt;/param&gt;
&lt;returns&gt;A Task that represents the asynchronous operation, which upon completion yields
the generated response string from the AI based on the user prompt.&lt;/returns&gt;</pre></function>
