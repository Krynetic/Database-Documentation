## Emojis
* <function><a id="emojiraw"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EmojiRaw</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> alias) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Gets the raw Unicode string of the emoji associated with the given alias.  
***alias***: The emoji alias (e.g. :tada:).  
**Returns**: The raw Unicode emoji, or an empty string if not found.  
**Examples**:
EmojiRaw(&quot;:tada:&quot;); // &quot;🎉&quot;  

</pre></function>
* <function><a id="emojialias"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EmojiAlias</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> raw) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Gets the primary alias of the emoji represented by the raw Unicode string.  
***raw***: The raw Unicode emoji (e.g. 🎉).  
**Returns**: The emoji alias, or an empty alias if not found.  
**Examples**:
EmojiAlias(&quot;🎉&quot;); // &quot;:tada:&quot;  

</pre></function>
* <function><a id="emojify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Emojify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Replaces emoji aliases in the input text with their raw Unicode equivalents.  
***text***: A text containing emoji aliases.  
**Returns**: The emojified text.  
**Examples**:
Emojify(&quot;initial :tada: commit&quot;); // &quot;initial 🎉 commit&quot;  

</pre></function>
* <function><a id="demojify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Demojify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Replaces raw Unicode emojis in the input text with their alias representations.  
***text***: A text containing raw Unicode emojis.  
**Returns**: The demojified text.  
**Examples**:
Demojify(&quot;initial 🎉 commit&quot;); // &quot;initial :tada: commit&quot;  

</pre></function>
* <function><a id="emojifind"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EmojiFind</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> query) -> <span style="color:#87AF00">string[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Finds emojis that match the given query and returns their raw Unicode values.  
***query***: A search value matched against emoji description, category, aliases or tags.  
**Returns**: An array of raw Unicode emojis.  
**Examples**:
EmojiFind(&quot;party&quot;); // \[&quot;🎉&quot;, &quot;🥳&quot;, ...\]  

</pre></function>
* <function><a id="emojifindaliases"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EmojiFindAliases</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> query) -> <span style="color:#87AF00">string[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Finds emojis that match the given query and returns their primary aliases.  
***query***: A search value matched against emoji description, category, aliases or tags.  
**Returns**: An array of emoji aliases.  
**Examples**:
EmojiFindAliases(&quot;party&quot;); // \[&quot;:tada:&quot;, &quot;:partying\_face:&quot;, ...\]  

</pre></function>
* <function><a id="emojiskintonevariants"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EmojiSkinToneVariants</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Gets all raw Unicode skin tone variants for the specified emoji.  
***value***: An emoji alias or raw Unicode string that supports skin tone modifiers.  
**Returns**: An array of raw Unicode skin tone variants.  
**Examples**:
EmojiSkinToneVariants(&quot;✌️&quot;); // \[&quot;✌🏻&quot;,&quot;✌🏼&quot;,&quot;✌🏽&quot;,&quot;✌🏾&quot;,&quot;✌🏿&quot;\]  

</pre></function>
* <function><a id="emojirandom"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EmojiRandom</span>() -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Gets a random emoji from the global emoji set.  
**Returns**: A raw Unicode emoji.  
**Examples**:
EmojiRandom(); // &quot;🎉&quot;  

</pre></function>
