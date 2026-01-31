## Geolocation
* <function><a id="haversine"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Haversine</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat2, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon2) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">GeoDistance</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the Haversine distance between two points on the Earth specified by their latitude and longitude.  
***lat1***: Latitude of the first point in degrees.
***lon1***: Longitude of the first point in degrees.
***lat2***: Latitude of the second point in degrees.
***lon2***: Longitude of the second point in degrees.  
**Returns**: The distance between the two points in kilometers.  

</pre></function>
* <function><a id="vincenty"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Vincenty</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat2, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon2) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the distance between two points on Earth using the Vincenty formula for an ellipsoidal model.
This method accounts for the Earth&apos;s flattening and is highly accurate over long distances.  
***lat1***: Latitude of the first point in degrees.
***lon1***: Longitude of the first point in degrees.
***lat2***: Latitude of the second point in degrees.
***lon2***: Longitude of the second point in degrees.  
**Returns**: The distance between the two points in kilometers.  

</pre></function>
* <function><a id="initialbearing"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">InitialBearing</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat2, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon2) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the initial bearing or forward azimuth needed to get from one geographic point 
to another. The result is expressed in degrees as a compass direction.  
***lat1***: Latitude of the start point in degrees.
***lon1***: Longitude of the start point in degrees.
***lat2***: Latitude of the end point in degrees.
***lon2***: Longitude of the end point in degrees.  
**Returns**: The initial bearing from the start point to the end point in degrees, ranging from 0 to 360.  

</pre></function>
* <function><a id="pointalongroute"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PointAlongRoute</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat2, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon2, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> fraction) -> <span style="color:#87AF00">ValueTuple\<double, double\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Computes a point along the great\-circle route between two geographic coordinates.  
***lat1***: Latitude of the starting point in degrees.
***lon1***: Longitude of the starting point in degrees.
***lat2***: Latitude of the ending point in degrees.
***lon2***: Longitude of the ending point in degrees.
***fraction***: A fraction (0..1) representing how far along the route to calculate the point.
A value of 0.5 represents the midpoint, for example.  
**Returns**: A tuple containing the latitude and longitude of the computed point along the route.  

</pre></function>
* <function><a id="degreestometerslat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DegreesToMetersLat</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> degreesLat) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts latitude in degrees to meters. 
The conversion assumes a spherical Earth model.  
***degreesLat***: The latitude angle in degrees.  
**Returns**: The equivalent distance in meters along the surface of the Earth at that latitude.  

</pre></function>
* <function><a id="meterstodegreeslon"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">MetersToDegreesLon</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> meters, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> atLat) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a distance in meters to an equivalent angular distance in degrees of longitude at a given latitude.  
***meters***: The distance in meters to be converted.
***atLat***: The latitude (in degrees) at which the conversion is performed. This affects the result due to Earth&apos;s curvature.  
**Returns**: The equivalent angular distance in degrees of longitude corresponding to the given distance at the specified latitude.  

</pre></function>
* <function><a id="compassdirection"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CompassDirection</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> bearingDegrees) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a given bearing in degrees to one of the 16 compass directions.
The function rounds the input bearing to the nearest compass direction using the specified formula.  
***bearingDegrees***: The bearing angle in degrees, which should be between 0 and 360.  
**Returns**: A string representing one of the 16 compass directions (e.g., &quot;N&quot;, &quot;NE&quot;, &quot;E&quot;).  
**Remarks**:
This function assumes a predefined array \`directions\` containing the 16 compass points
in clockwise order starting from &quot;N&quot; (North), such as {&quot;N&quot;, &quot;NNE&quot;, &quot;NE&quot;, ...}.  

</pre></function>
* <function><a id="isvalidlat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsValidLat</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Checks if the provided latitude value is valid.
A valid latitude must be in the range from \-90 to 90 degrees, inclusive.  
***lat***: The latitude value to check.  
**Returns**: True if the latitude is within the valid range; otherwise, false.  

</pre></function>
* <function><a id="isvalidlon"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsValidLon</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified longitude value is valid.
A valid longitude must be within the range of \-180 to 180 degrees, inclusive.  
***lon***: The longitude value to validate.  
**Returns**: true if the longitude is valid; otherwise, false.  

</pre></function>
* <function><a id="normalizelat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NormalizeLat</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Normalizes a given latitude to fall within the range of \-90 to 90 degrees.  
***lat***: The latitude value in degrees to be normalized.  
**Returns**: A normalized latitude value within the range of \-90 to 90 degrees.  

</pre></function>
* <function><a id="normalizelon"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NormalizeLon</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Normalizes a given longitude value to the range of \[\-180, 180\].  
***lon***: The longitude in degrees that needs normalization.  
**Returns**: The normalized longitude within the range of \[\-180, 180\] degrees.  

</pre></function>
* <function><a id="parselatlon"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseLatLon</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">ValueTuple\<double, double\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a given string containing latitude and longitude information 
in various formats and returns them as double values representing 
the latitude and longitude.  
***input***: A string containing latitude and longitude 
details. The input can be in different notations including degrees,
minutes, seconds (DMS) format and decimal degrees.  
**Returns**: A tuple containing two doubles where the first value is 
the latitude and the second is the longitude parsed from the given input.  

</pre></function>
* <function><a id="parselatlonwithmetadata"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseLatLonWithMetadata</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">CoordinateResult</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the input string to extract latitude and longitude information along with metadata about the coordinate format.  
***input***: The input string containing latitude and longitude data.  
**Returns**: A CoordinateResult object that includes parsed latitude, longitude, the detected format,
whether the coordinates are in DMS (Degrees, Minutes, Seconds) or Decimal format, and the original input string.  

</pre></function>
* <function><a id="geocodelocation"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GeocodeLocation</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> location, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> openweathermapApiKey) -> <span style="color:#87AF00">Task\<Dictionary\<string, double\>\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Geocodes the specified location using OpenWeatherMap&apos;s Geo API.  
***location***: The location string to geocode.
***openweathermapApiKey***: Your OpenWeatherMap API key for authentication.  
**Returns**: A dictionary containing latitude and longitude as keys with their respective double values,
or an empty dictionary if the location cannot be geocoded.  

</pre></function>
