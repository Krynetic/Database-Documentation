## Regex
* <function><a id="regexismatch"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RegexIsMatch</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> pattern, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines if the specified input string matches a given regular expression pattern.  
***pattern***: The regular expression pattern to match against.
***input***: The input string to test for a match.  
**Returns**: True if the input string matches the pattern; otherwise, false.  

</pre></function>
* <function><a id="regexmatch"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RegexMatch</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> pattern, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">Match</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Finds the first match for a regular expression within a given input string.  
***pattern***: The regex pattern to be matched against the input string.
***input***: The input string in which to search for matches.  
**Returns**: A Match object representing the first successful match of the pattern in the input, or an empty match if no patterns were found.  

</pre></function>
* <function><a id="regexmatches"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RegexMatches</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> pattern, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">Match[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves an array of matches based on a regular expression pattern applied to the input string.  
***pattern***: The regex pattern used for matching.
***input***: The input string where the search is performed.  
**Returns**: An array containing all matches found in the input string according to the specified pattern.  

</pre></function>
