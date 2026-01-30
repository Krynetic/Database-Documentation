## Regex
* <function><a id="regexismatch"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RegexIsMatch</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> pattern, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines if the specified input string matches a given regular expression pattern.
&lt;/summary&gt;
&lt;param name=&quot;pattern&quot;&gt;The regular expression pattern to match against.&lt;/param&gt;
&lt;param name=&quot;input&quot;&gt;The input string to test for a match.&lt;/param&gt;
&lt;returns&gt;True if the input string matches the pattern; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="regexmatch"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RegexMatch</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> pattern, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">Match</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Finds the first match for a regular expression within a given input string.
&lt;/summary&gt;
&lt;param name=&quot;pattern&quot;&gt;The regex pattern to be matched against the input string.&lt;/param&gt;
&lt;param name=&quot;input&quot;&gt;The input string in which to search for matches.&lt;/param&gt;
&lt;returns&gt;A Match object representing the first successful match of the pattern in the input, or an empty match if no patterns were found.&lt;/returns&gt;</pre></function>
* <function><a id="regexmatches"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RegexMatches</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> pattern, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">Match[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves an array of matches based on a regular expression pattern applied to the input string.
&lt;/summary&gt;
&lt;param name=&quot;pattern&quot;&gt;The regex pattern used for matching.&lt;/param&gt;
&lt;param name=&quot;input&quot;&gt;The input string where the search is performed.&lt;/param&gt;
&lt;returns&gt;An array containing all matches found in the input string according to the specified pattern.&lt;/returns&gt;</pre></function>
