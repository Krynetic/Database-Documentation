## Parsing
* <function><a id="parsebool"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseBool</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Attempts to parse the provided string as a boolean value.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a boolean value.&lt;/param&gt;
&lt;returns&gt;A boolean value that represents the parsed result from the input text.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string cannot be parsed into a boolean value.
The exception message includes the invalid input string for clarity.
&lt;/exception&gt;</pre></function>
* <function><a id="parsesbyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseSByte</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">sbyte</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the given string into an sbyte value. Throws a FormatException if parsing fails.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a number to parse.&lt;/param&gt;
&lt;returns&gt;The parsed sbyte value.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input cannot be converted to an sbyte, indicating that
the format is invalid for parsing into the specified range.
&lt;/exception&gt;</pre></function>
* <function><a id="parsebyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseByte</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">byte</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the specified string into a byte using invariant culture and integer number styles.
If parsing fails, a &lt;see cref=&quot;FormatException&quot;/&gt; is thrown.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The input string to parse.&lt;/param&gt;
&lt;returns&gt;The parsed byte value.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the format of the string is invalid or if it does not represent a valid byte value.
&lt;/exception&gt;</pre></function>
* <function><a id="parseint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseInt16</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">short</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the specified text into a 16\-bit signed integer (Int16).
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of the number to parse.&lt;/param&gt;
&lt;returns&gt;A short value parsed from the input text.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input cannot be parsed as Int16, indicating that
the format is not valid for an Int16 within the range of 
{short.MinValue}..{short.MaxValue}.
&lt;/exception&gt;</pre></function>
* <function><a id="parseuint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUInt16</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">ushort</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the given string representation of a number into an unsigned 16\-bit integer (UInt16).
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string that contains the number to be parsed.&lt;/param&gt;
&lt;returns&gt;The UInt16 value that results from parsing the specified string.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the format of the string is invalid or if it falls outside
the range of a UInt16 (0..65535).
&lt;/exception&gt;</pre></function>
* <function><a id="parseint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseInt32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a string into an integer (Int32) using invariant culture formatting. 
Throws a FormatException if the parsing is unsuccessful.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The text to parse as an Int32.&lt;/param&gt;
&lt;returns&gt;The parsed integer value.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string cannot be parsed into a valid Int32.
&lt;/exception&gt;</pre></function>
* <function><a id="parseuint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUInt32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">uint</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a string into an unsigned 32\-bit integer.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of the number to be parsed.&lt;/param&gt;
&lt;returns&gt;The parsed unsigned 32\-bit integer value.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string cannot be converted to a valid UInt32 value within the range of uint.MinValue and uint.MaxValue.
&lt;/exception&gt;</pre></function>
* <function><a id="parseint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseInt64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">long</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Attempts to parse the provided string into a 64\-bit integer (Int64). If parsing fails, it throws a FormatException.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a number to be parsed.&lt;/param&gt;
&lt;returns&gt;The successfully parsed long value if the conversion succeeds.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown when the input string cannot be parsed as an Int64.&lt;/exception&gt;</pre></function>
* <function><a id="parseuint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUInt64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the specified string representation of a number into its equivalent unsigned 64\-bit integer (ulong).
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;A string containing the number to convert.&lt;/param&gt;
&lt;returns&gt;The parsed unsigned 64\-bit integer value.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string does not represent a valid unsigned 64\-bit integer.
The exception message includes the text that could not be parsed and the range of valid values for an unsigned 64\-bit integer.
&lt;/exception&gt;</pre></function>
* <function><a id="parsefloat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseFloat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">float</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Attempts to parse the specified string into a single\-precision floating\-point number.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a number to parse.&lt;/param&gt;
&lt;returns&gt;A float value parsed from the given text if successful.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the parsing operation fails, indicating that the input string does not represent a valid single\-precision floating\-point number.
&lt;/exception&gt;</pre></function>
* <function><a id="parsedouble"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseDouble</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a string representation of a number into a double value.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string to be parsed.&lt;/param&gt;
&lt;returns&gt;The parsed double value if successful.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown when the input string cannot be parsed as a valid double.&lt;/exception&gt;</pre></function>
* <function><a id="parsedecimal"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseDecimal</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">decimal</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Attempts to parse a string into a decimal number using invariant culture and specific number styles.
If parsing is unsuccessful, it throws a FormatException with a message indicating the failure.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a decimal number to be parsed.&lt;/param&gt;
&lt;returns&gt;The parsed decimal value if successful.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string cannot be converted to a decimal using the specified parsing settings.
The exception message includes the input text that failed to parse.
&lt;/exception&gt;</pre></function>
* <function><a id="parsetimespan"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseTimeSpan</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">TimeSpan</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the specified string and converts it into a &lt;see cref=&quot;TimeSpan&quot;/&gt; object using invariant culture settings.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of time duration to parse.&lt;/param&gt;
&lt;returns&gt;A &lt;see cref=&quot;TimeSpan&quot;/&gt; representing the parsed time duration.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the format of the specified string is invalid or it does not represent a valid &lt;see cref=&quot;TimeSpan&quot;/&gt;.
&lt;/exception&gt;</pre></function>
* <function><a id="parsedatetimeoffset"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseDateTimeOffset</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a string into a DateTimeOffset object using the specified culture (InvariantCulture).
Throws a FormatException if parsing fails.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of the date and time offset.&lt;/param&gt;
&lt;returns&gt;A DateTimeOffset object parsed from the input string.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown when the input string cannot be parsed as a DateTimeOffset.&lt;/exception&gt;</pre></function>
* <function><a id="parseipaddress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseIPAddress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">IPAddress</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a string representation of an IP address into an IPAddress object.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string containing the IP address.&lt;/param&gt;
&lt;returns&gt;An IPAddress object representing the parsed IP address.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input text cannot be parsed as a valid IP address.
The exception message will specify the input string that failed to parse.
&lt;/exception&gt;</pre></function>
* <function><a id="parseguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseGuid</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Attempts to parse the specified string into a GUID (Globally Unique Identifier).
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a GUID to be parsed.&lt;/param&gt;
&lt;returns&gt;A GUID that matches the text if parsing succeeds.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string does not represent a valid GUID.
&lt;/exception&gt;</pre></function>
* <function><a id="parsesemver"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseSemVer</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> version) -> <span style="color:#87AF00">SemVer</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a given string into a Semantic Version (SemVer) object.
This method uses a regular expression to validate and extract version components: major, minor, and patch.
&lt;/summary&gt;
&lt;param name=&quot;version&quot;&gt;The semantic version string to be parsed.&lt;/param&gt;
&lt;returns&gt;A SemVer object containing the major, minor, and patch numbers extracted from the input string.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the provided version string does not match the semantic version format,
or if any of the numeric components (major, minor, patch) cannot be parsed as integers.
&lt;/exception&gt;</pre></function>
