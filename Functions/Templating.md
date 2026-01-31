## Templating
* <function><a id="smartformat"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">SmartFormat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> format, <span style="color:#87AF00; margin-left:1px; margin-right:1px">param object[]</span> args) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Formats the input string using smart formatting with extended capabilities. This function leverages a custom formatter that can be influenced by context data passed as a parameter. The formatted output adheres to culture\-invariant rules.  
***format***: The format string specifying how the arguments should be formatted and combined.
***args***: An array of objects containing the data to format according to the specified format string.  
**Returns**: A string resulting from applying smart formatting rules to the input data, using culture\-invariant formatting conventions.  

</pre></function>
* <function><a id="scribanformat"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">ScribanFormat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> templateText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> model = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Formats a provided template text using the Scriban templating engine, optionally applying a model as context data.
Incorporates custom methods from the loader context into the rendering process if available.
Throws an InvalidOperationException if the parsed template contains errors.  
***templateText***: The template text to be formatted using Scriban.
***model***: An optional dictionary of string keys and object values representing the model data for rendering. Defaults to null if not provided.  
**Returns**: A string result of the rendered template after applying the given model data or default contexts.  

</pre></function>
* <function><a id="handlebarsformat"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">HandlebarsFormat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> templateText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> model = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Formats a given text using Handlebars syntax with an optional model for data binding.
The function creates a Handlebars instance and configures it to use custom compile\-time features,
then compiles the template and renders it with the provided model (or an empty dictionary if none is supplied).  
***templateText***: The text of the Handlebars template to be compiled and rendered.
***model***: An optional dictionary representing the model that provides values for the placeholders in the template.  
**Returns**: A formatted string resulting from rendering the Handlebars template with the provided model.  

</pre></function>
