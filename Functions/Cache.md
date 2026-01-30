## Cache
* <function><a id="cacheget"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CacheGet</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">object</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Caches a value retrieved from the application cache. If the key is not found in the cache, the method returns null.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The key of the value to retrieve.&lt;/param&gt;
&lt;returns&gt;The cached value or null if it was not found.&lt;/returns&gt;</pre></function>
* <function><a id="cacheset"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">CacheSet</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">TimeSpan?</span> ttl = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Sets a value in the cache with an optional time\-to\-live (TTL).
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The key to set.&lt;/param&gt;
&lt;param name=&quot;value&quot;&gt;The value to store.&lt;/param&gt;
&lt;param name=&quot;ttl&quot;&gt;Optional TTL, defaults to null.&lt;/param&gt;
&lt;returns&gt;&lt;c&gt;True if the cache was successfully set. False otherwise.&lt;/c&gt;&lt;/returns&gt;</pre></function>
* <function><a id="cacheremove"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">CacheRemove</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Removes the specified key from the cache.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The key to be removed.&lt;/param&gt;</pre></function>
* <function><a id="cacheclear"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">CacheClear</span>() -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Clears the cache by calling the Clear method on the underlying cache.
&lt;/summary&gt;</pre></function>
