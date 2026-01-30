## Compression
* <function><a id="zstdcompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ZstdCompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data, <span style="color:#87AF00; margin-left:1px; margin-right:1px">CompressionLevel</span> level = <span style="color:#87AF00; margin-right:1px">System.IO.Compression.CompressionLevel.Optimal</span>) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Compresses a byte array using the Zstandard compression algorithm with specified level.
&lt;/summary&gt;
&lt;param name=&quot;data&quot;&gt;The input byte array to be compressed.&lt;/param&gt;
&lt;param name=&quot;level&quot;&gt;The compression level. Can be one of the following values:
&nbsp;&nbsp;\- NoCompression
&nbsp;&nbsp;\- Fastest
&nbsp;&nbsp;\- Optimal
&nbsp;&nbsp;\- SmallestSize
&lt;/param&gt;
&lt;returns&gt;The compressed byte array.&lt;/returns&gt;</pre></function>
* <function><a id="zstddecompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ZstdDecompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Decompression of Zstd compressed byte array to a bytes array
&lt;/summary&gt;
&lt;param name=&quot;data&quot;&gt;The input byte array&lt;/param&gt;
&lt;returns&gt;The decompressed byte array&lt;/returns&gt;</pre></function>
* <function><a id="gzipcompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GzipCompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data, <span style="color:#87AF00; margin-left:1px; margin-right:1px">CompressionLevel</span> level = <span style="color:#87AF00; margin-right:1px">System.IO.Compression.CompressionLevel.Optimal</span>) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Compresses the given byte array to a Gzip compressed stream.
&lt;/summary&gt;
&lt;param name=&quot;data&quot;&gt;The input byte array to be compressed.&lt;/param&gt;
&lt;param name=&quot;level&quot;&gt;The compression level. Can be one of the following values:
&nbsp;&nbsp;\- NoCompression
&nbsp;&nbsp;\- Fastest
&nbsp;&nbsp;\- Optimal
&nbsp;&nbsp;\- SmallestSize
&lt;/param&gt;
&lt;returns&gt;The compressed byte array as a bytes array.&lt;/returns&gt;</pre></function>
* <function><a id="gzipdecompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GzipDecompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Decompresses a byte array from GZip format to the caller&apos;s memory stream.
&lt;/summary&gt;
&lt;param name=&quot;data&quot;&gt;The input byte array in GZip format.&lt;/param&gt;
&lt;returns&gt;The decompressed data as an array of bytes.&lt;/returns&gt;</pre></function>
* <function><a id="zipcompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ZipCompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data, <span style="color:#87AF00; margin-left:1px; margin-right:1px">CompressionLevel</span> level = <span style="color:#87AF00; margin-right:1px">System.IO.Compression.CompressionLevel.Optimal</span>, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> entryName = <span style="color:#D70000; margin-right:1px">"data"</span>) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Compresses the given byte array to a Zip compressed stream.
&lt;/summary&gt;
&lt;param name=&quot;data&quot;&gt;The data to be compressed.&lt;/param&gt;
&lt;param name=&quot;level&quot;&gt;The compression level. Can be one of the following values:
&nbsp;&nbsp;\- NoCompression
&nbsp;&nbsp;\- Fastest
&nbsp;&nbsp;\- Optimal
&nbsp;&nbsp;\- SmallestSize
&lt;/param&gt;
&lt;param name=&quot;entryName&quot;&gt;The name of the entry in the archive. Defaults to &quot;data&quot;.&lt;/returns&gt;
&lt;returns&gt;A byte array containing the zipped data.&lt;/returns&gt;</pre></function>
* <function><a id="zipdecompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ZipDecompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> entryName = <span style="color:#D70000; margin-right:1px">"data"</span>) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Decompresses a ZIP file by extracting the specified entry.
&lt;/summary&gt;
&lt;returns&gt;A byte array representing the decompressed data.&lt;/returns&gt;</pre></function>
* <function><a id="brotlicompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">BrotliCompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data, <span style="color:#87AF00; margin-left:1px; margin-right:1px">CompressionLevel</span> level = <span style="color:#87AF00; margin-right:1px">System.IO.Compression.CompressionLevel.Optimal</span>) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Compresses the input byte array using Brotli algorithm with the specified compression level.
&lt;/summary&gt;
&lt;param name=&quot;data&quot;&gt;The byte array to be compressed.&lt;/param&gt;
&lt;param name=&quot;level&quot;&gt;The compression level. Can be one of the following values:
&nbsp;&nbsp;\- NoCompression
&nbsp;&nbsp;\- Fastest
&nbsp;&nbsp;\- Optimal
&nbsp;&nbsp;\- SmallestSize
&lt;/param&gt;
&lt;returns&gt;A byte array containing the compressed data.&lt;/returns&gt;</pre></function>
* <function><a id="brotlidecompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">BrotliDecompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Decompresses a byte array using the Brotli compression algorithm.
&lt;/summary&gt;
&lt;param name=&quot;data&quot;&gt;The compressed data to decompress.&lt;/param&gt;
&lt;returns&gt;A byte array containing the decompressed data.&lt;/returns&gt;</pre></function>
