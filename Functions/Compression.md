## Compression
* <function><a id="zstdcompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ZstdCompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data, <span style="color:#87AF00; margin-left:1px; margin-right:1px">CompressionLevel</span> level = <span style="color:#87AF00; margin-right:1px">System.IO.Compression.CompressionLevel.Optimal</span>) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Compresses a byte array using the Zstandard compression algorithm with specified level.  
***data***: The input byte array to be compressed.
***level***: The compression level. Can be one of the following values:
  \- NoCompression
  \- Fastest
  \- Optimal
  \- SmallestSize  
**Returns**: The compressed byte array.  

</pre></function>
* <function><a id="zstddecompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ZstdDecompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Decompression of Zstd compressed byte array to a bytes array  
***data***: The input byte array  
**Returns**: The decompressed byte array  

</pre></function>
* <function><a id="gzipcompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GzipCompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data, <span style="color:#87AF00; margin-left:1px; margin-right:1px">CompressionLevel</span> level = <span style="color:#87AF00; margin-right:1px">System.IO.Compression.CompressionLevel.Optimal</span>) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Compresses the given byte array to a Gzip compressed stream.  
***data***: The input byte array to be compressed.
***level***: The compression level. Can be one of the following values:
  \- NoCompression
  \- Fastest
  \- Optimal
  \- SmallestSize  
**Returns**: The compressed byte array as a bytes array.  

</pre></function>
* <function><a id="gzipdecompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GzipDecompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Decompresses a byte array from GZip format to the caller&apos;s memory stream.  
***data***: The input byte array in GZip format.  
**Returns**: The decompressed data as an array of bytes.  

</pre></function>
* <function><a id="zipcompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ZipCompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data, <span style="color:#87AF00; margin-left:1px; margin-right:1px">CompressionLevel</span> level = <span style="color:#87AF00; margin-right:1px">System.IO.Compression.CompressionLevel.Optimal</span>, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> entryName = <span style="color:#D70000; margin-right:1px">"data"</span>) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Compresses the given byte array to a Zip compressed stream.  
***data***: The data to be compressed.
***level***: The compression level. Can be one of the following values:
  \- NoCompression
  \- Fastest
  \- Optimal
  \- SmallestSize
***entryName***: The name of the entry in the archive. Defaults to &quot;data&quot;.  
**Returns**: A byte array containing the zipped data.  

</pre></function>
* <function><a id="zipdecompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ZipDecompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> entryName = <span style="color:#D70000; margin-right:1px">"data"</span>) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Decompresses a ZIP file by extracting the specified entry.  
**Returns**: A byte array representing the decompressed data.  

</pre></function>
* <function><a id="brotlicompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">BrotliCompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data, <span style="color:#87AF00; margin-left:1px; margin-right:1px">CompressionLevel</span> level = <span style="color:#87AF00; margin-right:1px">System.IO.Compression.CompressionLevel.Optimal</span>) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Compresses the input byte array using Brotli algorithm with the specified compression level.  
***data***: The byte array to be compressed.
***level***: The compression level. Can be one of the following values:
  \- NoCompression
  \- Fastest
  \- Optimal
  \- SmallestSize  
**Returns**: A byte array containing the compressed data.  

</pre></function>
* <function><a id="brotlidecompress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">BrotliDecompress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> data) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Decompresses a byte array using the Brotli compression algorithm.  
***data***: The compressed data to decompress.  
**Returns**: A byte array containing the decompressed data.  

</pre></function>
