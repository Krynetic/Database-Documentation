## Globally Unique Identifier (Guid)
* <function><a id="generateuuid1"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid1</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a UUID version 1 which is based on the current date and time, ensuring uniqueness through node and clock sequence identifiers.
This function creates a new GUID by manually setting its components to align with the UUID v1 specification.  
**Returns**: A Guid representing a UUID version 1.  

</pre></function>
* <function><a id="generateuuid3"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid3</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">Guid</span> namespaceId, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> name) -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a UUID version 3 using MD5 hashing algorithm based on the provided namespace identifier and name.  
***namespaceId***: The GUID representing the UUID namespace.
***name***: The name used to generate the UUID.  
**Returns**: A new Guid instance that represents a UUID version 3.  

</pre></function>
* <function><a id="generateuuid4"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid4</span>() -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">GenerateUuid</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a Version 4 Universally Unique Identifier (UUID) as a string.  
**Returns**: A string representing the generated UUID in its canonical form.  

</pre></function>
* <function><a id="generateuuid5"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid5</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> namespaceId, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> name) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a UUID version 5 based on the given namespace ID and name.
This method utilizes SHA1 hashing to ensure uniqueness according to RFC 4122 specifications.  
***namespaceId***: A valid GUID string representing the namespace.
***name***: The name or identifier for which the UUID is generated.  
**Returns**: A string representation of the generated UUID version 5.  

</pre></function>
* <function><a id="generateuuid6"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid6</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a version 1.6 UUID using the current system time as its basis.
The function creates a GUID by combining a timestamp and random bytes,
conforming to the variant 1.6 specification of the UUID standard.  
**Returns**: A unique identifier (GUID) formatted according to Version 1.6.  

</pre></function>
* <function><a id="generatecombguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateCombGuid</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a COMB (combined) GUID which is sorted lexicographically. 
The method creates a new GUID using the current time in UTC and combines it with 
a date\-based prefix to ensure that the GUIDs are ordered by creation time.  
**Returns**: A new Guid object containing a timestamp component for sorting purposes.  

</pre></function>
* <function><a id="generatetimeorderedguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateTimeOrderedGuid</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a time\-ordered GUID using the current system ticks to ensure temporal order.
This function is marked as unsafe and serves as a plugin function with the specified identifier.  
**Returns**: A unique identifier (GUID) that incorporates the current UTC timestamp for ordering.  

</pre></function>
