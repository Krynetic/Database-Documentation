## Temperature
* <function><a id="fahrenheittocelsius"></a><b>fn</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FahrenheitToCelsius</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> f) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">FtoC</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a temperature from Fahrenheit to Celsius.  
***f***: The temperature in Fahrenheit.  
**Returns**: The equivalent temperature in Celsius.  

</pre></function>
* <function><a id="fahrenheittokelvin"></a><b>fn</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FahrenheitToKelvin</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> f) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">FtoK</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a temperature from Fahrenheit to Kelvin.  
***f***: The temperature in degrees Fahrenheit.  
**Returns**: The equivalent temperature in Kelvin.  

</pre></function>
* <function><a id="celsiustokelvin"></a><b>fn</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CelsiusToKelvin</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> c) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">CtoK</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a temperature value from Celsius to Kelvin.  
***c***: The temperature in degrees Celsius.  
**Returns**: The equivalent temperature in Kelvin.  

</pre></function>
* <function><a id="celsiustofahrenheit"></a><b>fn</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CelsiusToFahrenheit</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> c) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">CtoF</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a temperature value from Celsius to Fahrenheit.  
***c***: The temperature in degrees Celsius.  
**Returns**: The equivalent temperature in degrees Fahrenheit.  

</pre></function>
* <function><a id="kelvintocelsius"></a><b>fn</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">KelvinToCelsius</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> k) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">KtoC</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a temperature from Kelvin to Celsius.  
***k***: The temperature in Kelvin.  
**Returns**: The equivalent temperature in Celsius.  

</pre></function>
* <function><a id="kelvintofahrenheit"></a><b>fn</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">KelvinToFahrenheit</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> k) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">KtoF</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a temperature from Kelvin to Fahrenheit.  
***k***: The temperature in Kelvin.  
**Returns**: The equivalent temperature in Fahrenheit.  

</pre></function>
* <function><a id="isfreezingcelsius"></a><b>fn</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsFreezingCelsius</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> c) -> <span style="color:#5FAFAF">bool</span> -- (alias <span style="color:#D75F00">IsFreezingC</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether a Celsius temperature is at or below the freezing point of water.  

</pre></function>
* <function><a id="isfreezingfahrenheit"></a><b>fn</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsFreezingFahrenheit</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> f) -> <span style="color:#5FAFAF">bool</span> -- (alias <span style="color:#D75F00">IsFreezingF</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether a Fahrenheit temperature is at or below the freezing point of water.  

</pre></function>
* <function><a id="isfreezingkelvin"></a><b>fn</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsFreezingKelvin</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> k) -> <span style="color:#5FAFAF">bool</span> -- (alias <span style="color:#D75F00">IsFreezingK</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether a Kelvin temperature is at or below the freezing point of water.  

</pre></function>
* <function><a id="isboilingcelsius"></a><b>fn</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsBoilingCelsius</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> c) -> <span style="color:#5FAFAF">bool</span> -- (alias <span style="color:#D75F00">IsBoilingC</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether a Celsius temperature is at or above the boiling point of water (sea level).  

</pre></function>
* <function><a id="isboilingfahrenheit"></a><b>fn</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsBoilingFahrenheit</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> f) -> <span style="color:#5FAFAF">bool</span> -- (alias <span style="color:#D75F00">IsBoilingF</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether a Fahrenheit temperature is at or above the boiling point of water (sea level).  

</pre></function>
* <function><a id="isboilingkelvin"></a><b>fn</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsBoilingKelvin</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> k) -> <span style="color:#5FAFAF">bool</span> -- (alias <span style="color:#D75F00">IsBoilingK</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether a Kelvin temperature is at or above the boiling point of water (sea level).  

</pre></function>
* <function><a id="windchillcelsius"></a><b>fn</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">WindChillCelsius</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> c, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> windSpeedKmh) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">WindChillC</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a Celsius temperature to its &quot;feels like&quot; wind chill approximation
using a simplified linear model (for demonstration; not scientifically precise
for all wind speeds).  
***c***: The air temperature in degrees Celsius.
***windSpeedKmh***: The wind speed in kilometers per hour.  
**Returns**: The approximate wind chill temperature in degrees Celsius.  

</pre></function>
