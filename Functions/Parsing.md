## Parsing
* <function><a id="parsebool"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseBool</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Attempts to parse the provided string as a boolean value.  
***text***: The string representation of a boolean value.  
**Returns**: A boolean value that represents the parsed result from the input text.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string cannot be parsed into a boolean value.
The exception message includes the invalid input string for clarity.  

</pre></function>
* <function><a id="parsesbyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseSByte</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">sbyte</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the given string into an sbyte value. Throws a FormatException if parsing fails.  
***text***: The string representation of a number to parse.  
**Returns**: The parsed sbyte value.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input cannot be converted to an sbyte, indicating that
the format is invalid for parsing into the specified range.  

</pre></function>
* <function><a id="parsebyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseByte</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">byte</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the specified string into a byte using invariant culture and integer number styles.
If parsing fails, a FormatException is thrown.  
***text***: The input string to parse.  
**Returns**: The parsed byte value.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the format of the string is invalid or if it does not represent a valid byte value.  

</pre></function>
* <function><a id="parseint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseInt16</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">short</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the specified text into a 16\-bit signed integer (Int16).  
***text***: The string representation of the number to parse.  
**Returns**: A short value parsed from the input text.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input cannot be parsed as Int16, indicating that
the format is not valid for an Int16 within the range of 
short.MinValue..short.MaxValue.  

</pre></function>
* <function><a id="parseuint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUInt16</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">ushort</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the given string representation of a number into an unsigned 16\-bit integer (UInt16).  
***text***: The string that contains the number to be parsed.  
**Returns**: The UInt16 value that results from parsing the specified string.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the format of the string is invalid or if it falls outside
the range of a UInt16 (0..65535).  

</pre></function>
* <function><a id="parseint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseInt32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a string into an integer (Int32) using invariant culture formatting. 
Throws a FormatException if the parsing is unsuccessful.  
***text***: The text to parse as an Int32.  
**Returns**: The parsed integer value.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string cannot be parsed into a valid Int32.  

</pre></function>
* <function><a id="parseuint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUInt32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">uint</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a string into an unsigned 32\-bit integer.  
***text***: The string representation of the number to be parsed.  
**Returns**: The parsed unsigned 32\-bit integer value.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string cannot be converted to a valid UInt32 value within the range of uint.MinValue and uint.MaxValue.  

</pre></function>
* <function><a id="parseint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseInt64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">long</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Attempts to parse the provided string into a 64\-bit integer (Int64). If parsing fails, it throws a FormatException.  
***text***: The string representation of a number to be parsed.  
**Returns**: The successfully parsed long value if the conversion succeeds.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string cannot be parsed as an Int64.  

</pre></function>
* <function><a id="parseuint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUInt64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the specified string representation of a number into its equivalent unsigned 64\-bit integer (ulong).  
***text***: A string containing the number to convert.  
**Returns**: The parsed unsigned 64\-bit integer value.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string does not represent a valid unsigned 64\-bit integer.
The exception message includes the text that could not be parsed and the range of valid values for an unsigned 64\-bit integer.  

</pre></function>
* <function><a id="parsefloat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseFloat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">float</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Attempts to parse the specified string into a single\-precision floating\-point number.  
***text***: The string representation of a number to parse.  
**Returns**: A float value parsed from the given text if successful.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the parsing operation fails, indicating that the input string does not represent a valid single\-precision floating\-point number.  

</pre></function>
* <function><a id="parsedouble"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseDouble</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a string representation of a number into a double value.  
***text***: The string to be parsed.  
**Returns**: The parsed double value if successful.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string cannot be parsed as a valid double.  

</pre></function>
* <function><a id="parsedecimal"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseDecimal</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">decimal</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Attempts to parse a string into a decimal number using invariant culture and specific number styles.
If parsing is unsuccessful, it throws a FormatException with a message indicating the failure.  
***text***: The string representation of a decimal number to be parsed.  
**Returns**: The parsed decimal value if successful.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string cannot be converted to a decimal using the specified parsing settings.
The exception message includes the input text that failed to parse.  

</pre></function>
* <function><a id="parsetimespan"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseTimeSpan</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">TimeSpan</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the specified string and converts it into a TimeSpan object using invariant culture settings.  
***text***: The string representation of time duration to parse.  
**Returns**: A TimeSpan representing the parsed time duration.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the format of the specified string is invalid or it does not represent a valid TimeSpan.  

</pre></function>
* <function><a id="parsedatetimeoffset"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseDateTimeOffset</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a string into a DateTimeOffset object using the specified culture (InvariantCulture).
Throws a FormatException if parsing fails.  
***text***: The string representation of the date and time offset.  
**Returns**: A DateTimeOffset object parsed from the input string.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string cannot be parsed as a DateTimeOffset.  

</pre></function>
* <function><a id="parseipaddress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseIPAddress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">IPAddress</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a string representation of an IP address into an IPAddress object.  
***text***: The string containing the IP address.  
**Returns**: An IPAddress object representing the parsed IP address.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input text cannot be parsed as a valid IP address.
The exception message will specify the input string that failed to parse.  

</pre></function>
* <function><a id="parseguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseGuid</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Attempts to parse the specified string into a GUID (Globally Unique Identifier).  
***text***: The string representation of a GUID to be parsed.  
**Returns**: A GUID that matches the text if parsing succeeds.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string does not represent a valid GUID.  

</pre></function>
* <function><a id="parsesemver"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseSemVer</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> version) -> <span style="color:#87AF00">SemVer</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a given string into a Semantic Version (SemVer) object.
This method uses a regular expression to validate and extract version components: major, minor, and patch.  
***version***: The semantic version string to be parsed.  
**Returns**: A SemVer object containing the major, minor, and patch numbers extracted from the input string.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the provided version string does not match the semantic version format,
or if any of the numeric components (major, minor, patch) cannot be parsed as integers.  

</pre></function>
