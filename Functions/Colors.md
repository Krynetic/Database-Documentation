## Colors
* <function><a id="parsehexcolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseHexColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> hexColorString) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a hexadecimal color string to an ARGBColor object. The input string can be in the format of 6 characters (RRGGBB) or 8 characters (AARRGGBB), 
optionally prefixed with &apos;\#&apos;. The function parses the hex string into its corresponding alpha, red, green, and blue components.  
***hexColorString***: The hexadecimal color string to be converted. This should be in the format of &apos;\#RRGGBB&apos; or &apos;\#AARRGGBB&apos;, 
where RR is the red component, GG is the green component, BB is the blue component, and AA is the alpha component.  
**Returns**: An ARGBColor object representing the parsed color components from the hexadecimal string. The Alpha (A) component defaults to 255 if not specified.  
**Exceptions**:
**Type**: Exception
**Description**: Thrown when the input string is null or empty, when it does not conform to valid length 
requirements of 6 or 8 characters, contains non\-hexadecimal characters, or other parsing errors occur.  

</pre></function>
* <function><a id="rgbtohsv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RGBToHSV</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c) -> <span style="color:#87AF00">HSVColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts an RGB color (with alpha transparency) to its HSV equivalent.  
***c***: The ARGBColor object containing the red, green, blue, and alpha values.  
**Returns**: A new HSVColor object representing the hue, saturation, value, and alpha of the original color.  

</pre></function>
* <function><a id="hsvtorgb"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HSVToRGB</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">HSVColor</span> c) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a color from HSV (Hue, Saturation, Value) space to ARGB (Alpha, Red, Green, Blue) color format.  
***c***: The HSVColor object containing the hue, saturation, value, and alpha components to be converted.  
**Returns**: Returns an ARGBColor object representing the equivalent color in ARGB format.  

</pre></function>
* <function><a id="adjustcolorbrightness"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AdjustColorBrightness</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> factor) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Adjusts the brightness of an ARGB color by a specified factor. The factor should be between \-1 and 1, where negative values darken the color, positive values brighten it, and zero leaves it unchanged.  
***c***: The original ARGBColor to adjust.
***factor***: A double value representing the brightness adjustment factor. It must be within the range \[\-1, 1\].  
**Returns**: A new ARGBColor instance with adjusted brightness based on the specified factor.  

</pre></function>
* <function><a id="invertcolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">InvertColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Inverts the color of an ARGBColor object by subtracting each RGB component from 255, while retaining the alpha value.
This function utilizes a custom attribute PluginFunction to denote its behavior as part of a plugin system.  
***c***: The original ARGBColor object whose color is to be inverted.  
**Returns**: A new ARGBColor object with the inverted RGB values and unchanged alpha value.  

</pre></function>
* <function><a id="grayscalecolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GrayscaleColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a given color to its grayscale equivalent.  
***c***: The original color to be converted.  
**Returns**: A new ARGBColor instance representing the grayscale version of the input color, preserving the alpha channel.  

</pre></function>
* <function><a id="blendcolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">BlendColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> t) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Blends two ARGB colors based on the specified blend factor.  
***a***: The first color to blend.
***b***: The second color to blend.
***t***: The blend factor ranging from 0.0 to 1.0, where 0.0 returns &apos;a&apos;, and 1.0 returns &apos;b&apos;.  
**Returns**: A new ARGBColor representing the blended result of &apos;a&apos; and &apos;b&apos; based on the blend factor &apos;t&apos;.  

</pre></function>
* <function><a id="adjustcolorsaturation"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AdjustColorSaturation</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> factor) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Adjusts the saturation of a given ARGBColor by a specified factor.
The method converts the color to HSV (Hue, Saturation, Value), modifies 
its saturation component based on the input factor, and then converts it back 
to RGB. Saturation is clamped between 0 and 1 to ensure valid values.  
***c***: The ARGBColor object representing the color whose saturation will be adjusted.
***factor***: A double value by which the saturation of the color will be multiplied. 
A factor greater than 1 increases saturation, while a factor between 0 and 1 decreases it.  
**Returns**: An ARGBColor object with the adjusted saturation.  

</pre></function>
* <function><a id="adjustcolorhue"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AdjustColorHue</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> degrees) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Adjusts the hue of a given ARGBColor by a specified number of degrees.
This function converts the color from RGB to HSV, modifies the hue,
and then converts it back to RGB.  
***c***: The original ARGBColor that will have its hue adjusted.
***degrees***: The degree by which to adjust the hue. Positive values
increase the hue (clockwise), while negative values decrease it (counterclockwise).  
**Returns**: An ARGBColor with the adjusted hue based on the input degrees.  

</pre></function>
* <function><a id="adjustcoloralpha"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AdjustColorAlpha</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">byte</span> alpha) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Adjusts the alpha component of an ARGB color while preserving its red, green, and blue components.  
***c***: The original ARGBColor object whose alpha is to be adjusted.
***alpha***: The new alpha value to set for the ARGBColor. Must be a byte between 0 and 255.  
**Returns**: A new ARGBColor object with the specified alpha component and the same red, green, and blue components as the original color.  

</pre></function>
* <function><a id="multiplycolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">MultiplyColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Multiplies two ARGBColor values component\-wise and returns the result.
Each channel (A, R, G, B) of the resulting color is calculated by multiplying the corresponding channels
of the input colors and dividing by 255 to normalize the value back into a byte range.  
***a***: The first ARGBColor instance.
***b***: The second ARGBColor instance.  
**Returns**: A new ARGBColor where each channel is the product of the corresponding channels in &apos;a&apos; and &apos;b&apos;,
divided by 255 to fit within the byte range. This represents a blend between the two colors based on their
alpha, red, green, and blue values respectively.  

</pre></function>
* <function><a id="screencolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ScreenColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Combines two ARGBColor values using the &quot;screen&quot; blend mode. This method calculates the resulting color by applying the screen blending formula to each channel (red, green, and blue) while taking the maximum alpha value from either of the input colors.  
***a***: The first ARGBColor object representing a color with its alpha, red, green, and blue components.
***b***: The second ARGBColor object representing a color with its alpha, red, green, and blue components.  
**Returns**: A new ARGBColor object where the result of the screen blend is applied to the color channels. The alpha channel contains the maximum alpha value from both input colors.  

</pre></function>
* <function><a id="overlaycolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">OverlayColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Applies an overlay blending mode to two ARGBColor objects and returns the resulting color.
The overlay effect is a combination of multiply and screen blend modes, which enhances contrast by darkening or lightening colors depending on their luminance.  
***a***: The first ARGBColor object representing the background color.
***b***: The second ARGBColor object representing the overlay color.  
**Returns**: An ARGBColor object resulting from applying the overlay blending mode to the input colors.  

</pre></function>
* <function><a id="lightencolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">LightenColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Lightens two ARGBColor objects by comparing their respective channels and selecting the maximum value for each channel.  
***a***: The first ARGBColor object.
***b***: The second ARGBColor object.  
**Returns**: A new ARGBColor object where each channel is the maximum of the corresponding channels from the input colors.  

</pre></function>
* <function><a id="darkencolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DarkenColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Darkens the specified ARGBColor by combining it with another ARGBColor.
The alpha channel is set to the maximum of both colors,
while the red, green, and blue channels are set to the minimum of each respective pair from the two colors.  
***a***: The first ARGBColor.
***b***: The second ARGBColor used for darkening the first color.  
**Returns**: A new ARGBColor where:
\- The alpha channel is the maximum of both input colors&apos; alpha channels.
\- The red, green, and blue channels are the minimum of each respective pair from the two input colors.  

</pre></function>
