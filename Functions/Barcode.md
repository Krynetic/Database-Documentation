## Barcode
* <function><a id="generateqrcode"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateQRCode</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> payload, <span style="color:#87AF00; margin-left:1px; margin-right:1px">Generator</span> generator = <span style="color:#87AF00; margin-right:1px">Krynetic.Database.Plugins.BarcodePlugin+Generator.PNG</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> pixelsPerModule = <span style="color:#5FAFAF; margin-right:1px">20</span>) -> <span style="color:#87AF00">object</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a QR code based on the provided payload and image generator.
&lt;/summary&gt;
&lt;param name=&quot;payload&quot;&gt;The data to encode in the QR code.&lt;/param&gt;
&lt;param name=&quot;generator&quot;&gt;The type of image generator to use. Defaults to PNG.&lt;/param&gt;
&lt;param name=&quot;pixelsPerModule&quot;&gt;The number of pixels per module in the generated QR code.&lt;/param&gt;
&lt;returns&gt;An object representing the generated QR code, string or byte\[\].&lt;/returns&gt;</pre></function>
