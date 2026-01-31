## String
* <function><a id="reverse"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Reverse</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Reverses the order of characters in a given input string using an efficient method.
This function leverages the Span&lt;T&gt; and String.Create to perform the reversal operation 
in place, minimizing allocations and enhancing performance.  
***text***: The string whose characters are to be reversed.  
**Returns**: A new string with its characters in reverse order compared to the input.  

</pre></function>
* <function><a id="repeatstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RepeatString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> times) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Repeats the given input string a specified number of times.  
***input***: The string to be repeated.
***times***: The number of times to repeat the string. Must be non\-negative.  
**Returns**: A new string consisting of the input string repeated &apos;times&apos; times concatenated together. If &apos;times&apos; is zero, an empty string is returned.  

</pre></function>
* <function><a id="truncate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Truncate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> suffix = <span style="color:#D70000; margin-right:1px">"…"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Truncates the given input string to a specified length and appends a suffix if truncation occurs.  
***input***: The original string to be truncated.
***length***: The maximum allowed length for the output string. If the input is shorter, it&apos;s returned unchanged.
***suffix***: The string to append at the end if truncation occurs, defaulting to an ellipsis character (…).  
**Returns**: The truncated string with suffix appended if necessary; otherwise, returns the original string.  

</pre></function>
* <function><a id="countwords"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CountWords</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Counts the number of words in the provided input string using a regular expression pattern.  
***input***: The input string from which to count the words.  
**Returns**: The total number of words found in the input string.  

</pre></function>
* <function><a id="randomstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomString</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> allowedChars = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a random string of the specified length using either provided allowed characters or a default character set.  
***length***: The length of the random string to generate. Must be non\-negative.
***allowedChars***: An optional parameter specifying which characters can be used in the generated string. 
If null, a default set of alphanumeric characters is used.  
**Returns**: A randomly generated string of specified length using allowed or default characters.  
**Exceptions**:
**Type**: ArgumentOutOfRangeException
**Description**: Thrown when the specified length is negative.  
**Type**: ArgumentException
**Description**: Thrown when the character set (either provided or default) is empty.  

</pre></function>
* <function><a id="slugify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Slugify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> separator = <span style="color:#D70000; margin-right:1px">"-"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Transforms the input string into a URL\-friendly slug format.
Converts all characters to lowercase, replaces non\-alphanumeric 
characters with hyphens, and trims leading/trailing hyphens.  
***input***: The input string to be converted into a slug.  
**Returns**: A URL\-friendly version of the input string as a lowercase string with hyphens.  

</pre></function>
* <function><a id="joinstrings"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">JoinStrings</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IEnumerable\<string\></span> items, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> delimiter = <span style="color:#D70000; margin-right:1px">","</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Joins a collection of strings into a single string using the specified delimiter.  
***items***: The collection of strings to join.
***delimiter***: A string used to separate each element in the joined string. Defaults to &quot;,&quot; if not provided.  
**Returns**: A single string that is the concatenation of the elements in items, separated by occurrences of delimiter.  

</pre></function>
* <function><a id="splitstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SplitString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> delimiter = <span style="color:#D70000; margin-right:1px">","</span>) -> <span style="color:#87AF00">List\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Splits the input string into a list of substrings based on the specified delimiter.  
***input***: The string to be split.
***delimiter***: The delimiter used to separate the substrings. Defaults to a comma (&quot;,&quot;) if not provided.  
**Returns**: A list containing each substring resulting from the split operation.  

</pre></function>
* <function><a id="removewhitespace"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RemoveWhitespace</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Removes all whitespace characters from the specified input string.
This function utilizes a regular expression to identify and eliminate all forms of 
whitespace, including spaces, tabs, and newlines. The result is returned as a single,
contiguous string without any whitespace characters.  
***input***: The input string from which whitespace will be removed.  
**Returns**: A new string with all whitespace characters removed.  

</pre></function>
* <function><a id="countoccurrences"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CountOccurrences</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> source, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> substring) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Counts the occurrences of a specified substring within the provided source string.
Utilizes regular expressions to ensure accurate matching. If either input is null or empty, they are treated as empty strings by default.  
***source***: The string in which to search for occurrences.
***substring***: The substring to count within the source string.  
**Returns**: The number of times the specified substring occurs in the source string.  

</pre></function>
* <function><a id="startswithignorecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">StartsWithIgnoreCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> prefix) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified input string begins with a given prefix,
ignoring case differences.  
***input***: The string to test.
***prefix***: The prefix to look for at the start of the input string.  
**Returns**: true if input starts with prefix, ignoring case; otherwise, false.  

</pre></function>
* <function><a id="endswithignorecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EndsWithIgnoreCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> suffix) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether a specified string ends with the given suffix,
ignoring case. If either the input or the suffix is null, appropriate
handling ensures no exceptions are thrown.  
***input***: The string to be evaluated.
***suffix***: The suffix to compare against.  
**Returns**: True if the input ends with the specified suffix ignoring case; otherwise, false.  

</pre></function>
* <function><a id="containsignorecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ContainsIgnoreCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> source, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toCheck) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified substring is present in the given string, 
ignoring case sensitivity.  
***source***: The source string to search within.
***toCheck***: The substring to locate in the source string.  
**Returns**: True if the substring is found; otherwise, false. Returns false if either input is null.  

</pre></function>
* <function><a id="isalpha"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsAlpha</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified string contains only alphabetic characters.
Utilizes a regular expression to match the entire input against alphabet\-only patterns. 
If the input is null, it defaults to an empty string before performing the check.  
***input***: The string to evaluate.  
**Returns**: true if the input contains only alphabetic characters; otherwise, false.  

</pre></function>
* <function><a id="isalphanumeric"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsAlphaNumeric</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified string contains only alphanumeric characters.
Uses a predefined regular expression pattern to check if each character in the input 
is either a letter (uppercase or lowercase) or a digit. Returns true if all characters 
match this criteria, otherwise returns false. If the input is null or empty, it defaults 
to an empty string and evaluates accordingly.  
***input***: The string to be evaluated for alphanumeric content.  
**Returns**: True if the string is composed solely of letters and digits; otherwise, false.  

</pre></function>
* <function><a id="islowercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsLowerCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines if a given string is in lowercase.  
***input***: The string to check.  
**Returns**: True if the input string is entirely in lowercase, or null/empty; otherwise, false.  
**Remarks**:
Uses string.ToLowerInvariant to perform case\-insensitive comparison,
ensuring that culture\-specific casing rules do not affect the result.  

</pre></function>
* <function><a id="isuppercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsUpperCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified string is entirely in uppercase.  
***input***: The string to evaluate.  
**Returns**: true if the input is null or an empty string, or if all characters in the input are uppercase; otherwise, false.  

</pre></function>
* <function><a id="tostring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">Str</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the specified object to its string representation. Returns a special 
string for null objects, uses invariant culture formatting for convertible 
objects, and handles tracked dictionaries uniquely by including their Id.  
***input***: The input object to convert to string.  
**Returns**: A string representing the input object, or special representations
for null, tracked dictionaries, and convertible types. Returns null 
if conversion fails for non\-conformant objects.  

</pre></function>
* <function><a id="format"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Format</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> format, <span style="color:#87AF00; margin-left:1px; margin-right:1px">param object[]</span> args) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Formats the specified string using the provided arguments.  
***format***: The composite format string.
***args***: An array of objects to write using format.  
**Returns**: A formatted string according to the format and args specified.  

</pre></function>
