## Conversions
* <function><a id="convertangle"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertAngle</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts an angle value from one unit to another.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The numeric value of the angle.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;The current unit of the angle, which can be &quot;rad&quot;, &quot;radian&quot;, &quot;radians&quot;, &quot;deg&quot;, &quot;degree&quot;, &quot;degrees&quot;, &quot;grad&quot;, &quot;gradian&quot;, or &quot;gradians&quot;.&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;The desired unit for conversion, which can be &quot;rad&quot;, &quot;radian&quot;, &quot;radians&quot;, &quot;deg&quot;, &quot;degree&quot;, &quot;degrees&quot;, &quot;grad&quot;, &quot;gradian&quot;, or &quot;gradians&quot;.&lt;/param&gt;
&lt;returns&gt;The angle converted to the specified unit.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when either &apos;fromUnit&apos; or &apos;toUnit&apos; is unsupported.&lt;/exception&gt;</pre></function>
* <function><a id="convertfuelefficiency"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertFuelEfficiency</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts fuel efficiency between different units.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The value of fuel efficiency in the source unit.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;The current unit of measurement (&quot;l/100km&quot;, &quot;mpg&quot; for US miles per gallon, or &quot;ukmpg&quot; for UK miles per gallon).&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;The target unit of measurement (&quot;l/100km&quot;, &quot;mpg&quot; for US miles per gallon, or &quot;ukmpg&quot; for UK miles per gallon).&lt;/param&gt;
&lt;returns&gt;The converted value in the target unit.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when an unsupported fromUnit or toUnit is specified.&lt;/exception&gt;</pre></function>
* <function><a id="convertluminance"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertLuminance</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a luminance value from one unit to another.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The luminance value to be converted.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;The unit of the input luminance value. Supported units are &quot;cd/m2&quot;, &quot;candela per square meter&quot;, &quot;nits&quot;, &quot;lambert&quot;, and &quot;foot\-lambert&quot;.&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;The target unit for conversion. Supported units are &quot;cd/m2&quot;, &quot;candela per square meter&quot;, &quot;nits&quot;, &quot;lambert&quot;, and &quot;foot\-lambert&quot;.&lt;/param&gt;
&lt;returns&gt;The luminance value converted to the specified target unit.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when an unsupported fromUnit or toUnit is provided.&lt;/exception&gt;</pre></function>
* <function><a id="convertfrequency"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertFrequency</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a frequency value from one unit of measurement to another.
The function supports conversions between Hertz (Hz), Kilohertz (kHz),
Megahertz (MHz), and Gigahertz (GHz).
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The numerical frequency value to be converted.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;The unit of the input frequency. Supported units include &quot;hz&quot;, &quot;hertz&quot;,
&quot;khz&quot;, &quot;kilohertz&quot;, &quot;mhz&quot;, &quot;megahertz&quot;, &quot;ghz&quot;, and &quot;gigahertz&quot;.&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;The target unit for conversion. Supported units include &quot;hz&quot;, &quot;hertz&quot;,
&quot;khz&quot;, &quot;kilohertz&quot;, &quot;mhz&quot;, &quot;megahertz&quot;, &quot;ghz&quot;, and &quot;gigahertz&quot;.&lt;/param&gt;
&lt;returns&gt;The converted frequency value in the specified target unit.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when either \`fromUnit\` or \`toUnit\` is not supported.&lt;/exception&gt;</pre></function>
* <function><a id="convertforce"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertForce</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a force value from one unit to another.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The magnitude of the force to convert.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;The original unit of the force. Supported units are &quot;N&quot;, &quot;newton&quot;, &quot;newtons&quot;, 
&quot;kgf&quot;, &quot;kilogram\-force&quot; for conversion from, and &quot;N&quot;, &quot;newton&quot;, &quot;newtons&quot;, &quot;kgf&quot;, &quot;kilogram\-force&quot;,
&quot;lbf&quot;, &quot;pound\-force&quot; for conversion to.&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;The target unit of the force. Supported units are &quot;N&quot;, &quot;newton&quot;, &quot;newtons&quot;, 
&quot;kgf&quot;, &quot;kilogram\-force&quot;, &quot;lbf&quot;, &quot;pound\-force&quot;.&lt;/param&gt;
&lt;returns&gt;The converted force value in the specified toUnit.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when an unsupported fromUnit or toUnit is provided.&lt;/exception&gt;</pre></function>
* <function><a id="convertsoundlevel"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertSoundLevel</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a sound level between decibels (dB) and power ratio.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The value to convert.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;The unit of the input value. Supported values are &quot;db&quot; or &quot;ratio&quot;.&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;The target unit for conversion. Only &quot;ratio&quot; is supported as a conversion from &quot;db&quot;.&lt;/param&gt;
&lt;returns&gt;The converted sound level in the specified target unit.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;
Thrown when unsupported units are provided or if there&apos;s an attempt to convert between unsupported units.
&lt;/exception&gt;</pre></function>
* <function><a id="convertpressure"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertPressure</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a pressure value from one unit of measurement to another.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The numerical value of the pressure to convert.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;The unit of measurement of the input pressure. Supported units are &apos;Pa&apos;, &apos;Pascal&apos;, &apos;Pascals&apos;, &apos;bar&apos;, &apos;bars&apos;, &apos;psi&apos;, &apos;pound per square inch&apos;, &apos;pounds per square inch&apos;, &apos;atm&apos;, &apos;atmosphere&apos;, and &apos;atmospheres&apos;.&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;The unit of measurement for the output pressure. Supported units are &apos;Pa&apos;, &apos;Pascal&apos;, &apos;Pascals&apos;, &apos;bar&apos;, &apos;bars&apos;, &apos;psi&apos;, &apos;pound per square inch&apos;, &apos;pounds per square inch&apos;, &apos;atm&apos;, &apos;atmosphere&apos;, and &apos;atmospheres&apos;.&lt;/param&gt;
&lt;returns&gt;The converted pressure value in the specified output unit of measurement.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when an unsupported fromUnit or toUnit is provided.&lt;/exception&gt;</pre></function>
* <function><a id="convertenergy"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertEnergy</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts an energy value from one unit to another.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The energy value to convert.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;The unit of the input energy value. Supported units include:
&quot;j&quot;, &quot;joule&quot;, &quot;joules&quot; (J),
&quot;kj&quot;, &quot;kilojoule&quot;, &quot;kilojoules&quot; (kJ),
&quot;cal&quot;, &quot;calorie&quot;, &quot;calories&quot; (cal),
&quot;kcal&quot;, &quot;kilocalorie&quot;, &quot;kilocalories&quot; (kcal),
&quot;wh&quot;, &quot;watt hour&quot;, &quot;watt hours&quot; (Wh).&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;The unit to convert the energy value into. Supported units include:
&quot;j&quot;, &quot;joule&quot;, &quot;joules&quot; (J),
&quot;kj&quot;, &quot;kilojoule&quot;, &quot;kilojoules&quot; (kJ),
&quot;cal&quot;, &quot;calorie&quot;, &quot;calories&quot; (cal),
&quot;kcal&quot;, &quot;kilocalorie&quot;, &quot;kilocalories&quot; (kcal),
&quot;wh&quot;, &quot;watt hour&quot;, &quot;watt hours&quot; (Wh).&lt;/param&gt;
&lt;returns&gt;The energy value converted to the specified unit.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when an unsupported fromUnit or toUnit is provided.&lt;/exception&gt;</pre></function>
* <function><a id="convertpower"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertPower</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a power value from one unit to another.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The numerical value of the power.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;The unit of the input power, supported units are: &quot;w&quot;, &quot;watt&quot;, &quot;watts&quot;, &quot;kw&quot;, &quot;kilowatt&quot;, &quot;kilowatts&quot;, &quot;hp&quot;, &quot;horsepower&quot;.&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;The target unit for conversion, supported units are: &quot;w&quot;, &quot;watt&quot;, &quot;watts&quot;, &quot;kw&quot;, &quot;kilowatt&quot;, &quot;kilowatts&quot;, &quot;hp&quot;, &quot;horsepower&quot;.&lt;/param&gt;
&lt;returns&gt;The converted power value in the specified target unit.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when an unsupported fromUnit or toUnit is provided.&lt;/exception&gt;</pre></function>
* <function><a id="convertdatasize"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertDataSize</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a data size from one unit to another.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The numeric value representing the amount of data.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;The unit of measurement for the input value (e.g., &quot;bytes&quot;, &quot;KB&quot;).&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;The target unit of measurement to convert to (e.g., &quot;MB&quot;, &quot;bits&quot;).&lt;/param&gt;
&lt;returns&gt;The converted data size in the specified target unit.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;
Thrown when an unsupported fromUnit or toUnit is provided.
&lt;/exception&gt;</pre></function>
* <function><a id="convertmass"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertMass</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a mass value from one unit to another.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The numeric value of the mass to be converted.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;A string representing the initial unit of measurement (e.g., &quot;kg&quot;, &quot;g&quot;, &quot;lb&quot;).&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;A string representing the target unit of measurement (e.g., &quot;kg&quot;, &quot;g&quot;, &quot;oz&quot;).&lt;/param&gt;
&lt;returns&gt;A double representing the converted mass in the target unit.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when an unsupported fromUnit or toUnit is provided.&lt;/exception&gt;</pre></function>
* <function><a id="convertvolume"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertVolume</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a volume from one unit to another.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The numerical value of the volume to convert.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;The unit of the input volume. Supported units include liters (l, liter, liters), milliliters (ml, milliliter, milliliters), gallons (gal, gallon, gallons), cups (cup, cups), and fluid ounces (floz, fluid ounce, fluid ounces).&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;The unit to convert the volume into. Supported units include those listed for fromUnit.&lt;/param&gt;
&lt;returns&gt;The converted volume in the specified target unit.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;
Thrown when either the \`fromUnit\` or \`toUnit\` is unsupported.
&lt;/exception&gt;</pre></function>
* <function><a id="convertarea"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertArea</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a specified area value from one unit of measurement to another.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The numeric value representing the area to convert.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;The unit of measurement for the input area (e.g., &quot;m2&quot;, &quot;km2&quot;, &quot;ft2&quot;).&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;The target unit of measurement for conversion (e.g., &quot;m2&quot;, &quot;in2&quot;, &quot;acre&quot;).&lt;/param&gt;
&lt;returns&gt;The converted area value in the specified target unit.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when an unsupported fromUnit or toUnit is provided.&lt;/exception&gt;</pre></function>
* <function><a id="convertspeed"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertSpeed</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a speed value from one unit of measurement to another.
Supported units for conversion are meters per second (mps, m/s, meters per second),
kilometers per hour (kmh, km/h, kilometers per hour), miles per hour (mph, miles per hour),
and knots (knot, knots). The function first converts the input speed to meters per second,
then converts it to the desired output unit.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The speed value to convert.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;The unit of measurement for the input speed. Valid units include &quot;mps&quot;, &quot;m/s&quot;,
&quot;meters per second&quot;, &quot;kmh&quot;, &quot;km/h&quot;, &quot;kilometers per hour&quot;, &quot;mph&quot;, &quot;miles per hour&quot;, &quot;knot&quot;, and &quot;knots&quot;.&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;The unit of measurement for the output speed. Valid units include &quot;mps&quot;, &quot;m/s&quot;,
&quot;meters per second&quot;, &quot;kmh&quot;, &quot;km/h&quot;, &quot;kilometers per hour&quot;, &quot;mph&quot;, &quot;miles per hour&quot;, &quot;knot&quot;, and &quot;knots&quot;.&lt;/param&gt;
&lt;returns&gt;The converted speed value in the desired unit of measurement.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when an unsupported fromUnit or toUnit is provided.&lt;/exception&gt;</pre></function>
* <function><a id="converttime"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertTime</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a time value from one unit to another.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The numeric value representing the time.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;The unit of the input time value. Supported units are &quot;s&quot;, &quot;sec&quot;, &quot;second&quot;, &quot;seconds&quot;,
&quot;min&quot;, &quot;minute&quot;, &quot;minutes&quot;, &quot;h&quot;, &quot;hr&quot;, &quot;hour&quot;, &quot;hours&quot;, &quot;day&quot;, &quot;days&quot;, &quot;ms&quot;, 
&quot;millisecond&quot;, and &quot;milliseconds&quot;.&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;The unit to convert the input time value into. Supported units are &quot;s&quot;, &quot;sec&quot;,
&quot;second&quot;, &quot;seconds&quot;, &quot;min&quot;, &quot;minute&quot;, &quot;minutes&quot;, &quot;h&quot;, &quot;hr&quot;, &quot;hour&quot;, &quot;hours&quot;, &quot;day&quot;, 
&quot;days&quot;, &quot;ms&quot;, &quot;millisecond&quot;, and &quot;milliseconds&quot;.&lt;/param&gt;
&lt;returns&gt;A double representing the converted time value in the target unit.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when an unsupported fromUnit or toUnit is provided.&lt;/exception&gt;</pre></function>
* <function><a id="convertlength"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertLength</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a length value from one unit to another.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The numerical value representing the length.&lt;/param&gt;
&lt;param name=&quot;fromUnit&quot;&gt;The unit of measurement for the input value. Supported units include meters (m, meter, meters), kilometers (km, kilometer, kilometers), centimeters (cm, centimeter, centimeters), millimeters (mm, millimeter, millimeters), miles (mi, mile, miles), US miles (usmile, us mile, us miles), yards (yd, yard, yards), feet (ft, foot, feet), and inches (in, inch, inches).&lt;/param&gt;
&lt;param name=&quot;toUnit&quot;&gt;The unit of measurement for the output value. Supported units include meters (m, meter, meters), kilometers (km, kilometer, kilometers), centimeters (cm, centimeter, centimeters), millimeters (mm, millimeter, millimeters), miles (mi, mile, miles), US miles (usmile, us mile, us miles), yards (yd, yard, yards), feet (ft, foot, feet), and inches (in, inch, inches).&lt;/param&gt;
&lt;returns&gt;The converted length value in the specified toUnit.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when an unsupported fromUnit or toUnit is provided.&lt;/exception&gt;</pre></function>
