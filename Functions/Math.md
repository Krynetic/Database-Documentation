## Math
* <function><a id="acos"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Acos</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the arc cosine (inverse cosine) of a specified number.
The result is in radians and returns a value between 0 and π (inclusive).
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The number for which to calculate the inverse cosine. Must be within the range \[\-1, 1\].&lt;/param&gt;
&lt;returns&gt;The arc cosine of the specified number.&lt;/returns&gt;</pre></function>
* <function><a id="acosh"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Acosh</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the inverse hyperbolic cosine (acosh) of a specified number.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The number for which to calculate the acosh value.&lt;/param&gt;
&lt;returns&gt;The acosh of the specified number. Returns NaN if the input is less than 1.&lt;/returns&gt;</pre></function>
* <function><a id="asin"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Asin</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the arc sine (inverse sine) of a specified number, returning the result in radians.
The value returned by this method is within the range \[\-π/2, π/2\].
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The angle, measured in radians, whose sine is to be calculated.&lt;/param&gt;
&lt;returns&gt;The angle in radians from \-π/2 through π/2 whose sine is the specified number. If the value specified by input is less than \-1 or greater than 1, Asin returns NaN.&lt;/returns&gt;</pre></function>
* <function><a id="asinh"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Asinh</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the inverse hyperbolic sine (asinh) of a specified number.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The value for which to calculate the asinh.&lt;/param&gt;
&lt;returns&gt;The inverse hyperbolic sine of the input number.&lt;/returns&gt;
&lt;example&gt;
This method is an extension and can be used as follows:
&lt;code&gt;
double result = MathExtension.Asinh(1.0);
&lt;/code&gt;
&lt;/example&gt;</pre></function>
* <function><a id="atan"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Atan</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the arctangent of a specified number.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The angle in radians for which to calculate the tangent.&lt;/param&gt;
&lt;returns&gt;The angle whose tangent is the specified number, measured in radians.&lt;/returns&gt;</pre></function>
* <function><a id="atanh"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Atanh</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the inverse hyperbolic tangent (atanh) of a specified number.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The number to calculate the inverse hyperbolic tangent for. The value must be in the range \-1 to 1, exclusive.&lt;/param&gt;
&lt;returns&gt;The inverse hyperbolic tangent of the specified number.&lt;/returns&gt;</pre></function>
* <function><a id="cbrt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Cbrt</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the cube root of a given number.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The number for which to calculate the cube root.&lt;/param&gt;
&lt;returns&gt;The cube root of the specified number.&lt;/returns&gt;</pre></function>
* <function><a id="ceiling"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Ceiling</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Rounds the specified number up to the nearest whole number.
This function utilizes the built\-in System.Math.Ceiling method 
to perform the rounding operation and returns a double precision result.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The decimal or floating\-point number to round up.&lt;/param&gt;
&lt;returns&gt;A double representing the smallest integral value that is greater than or equal to the input.&lt;/returns&gt;</pre></function>
* <function><a id="cos"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Cos</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the cosine of the specified angle, provided in radians.
The function leverages the System.Math library to perform this trigonometric computation.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The angle in radians for which the cosine value is calculated.&lt;/param&gt;
&lt;returns&gt;The cosine of the input angle as a double precision floating\-point number.&lt;/returns&gt;</pre></function>
* <function><a id="cosh"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Cosh</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the hyperbolic cosine of a specified angle.
This method uses the built\-in Math.Cosh function to compute the result,
which represents the hyperbolic cosine for a given double precision floating\-point number.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The angle in radians for which to calculate the hyperbolic cosine.&lt;/param&gt;
&lt;returns&gt;The hyperbolic cosine of the specified input value.&lt;/returns&gt;</pre></function>
* <function><a id="exp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Exp</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the exponential of the specified number using the mathematical constant e (Euler&apos;s number).
This function returns e raised to the power of the given input.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The exponent value for which to calculate e^input.&lt;/param&gt;
&lt;returns&gt;The result of e raised to the power of &apos;input&apos; as a double precision floating\-point number.&lt;/returns&gt;</pre></function>
* <function><a id="floor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Floor</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the largest integer less than or equal to a specified decimal number.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The decimal number to apply the floor operation.&lt;/param&gt;
&lt;returns&gt;The largest integer less than or equal to the input value.&lt;/returns&gt;
&lt;remarks&gt;This function is used for rounding down real numbers to their nearest integer.&lt;/remarks&gt;</pre></function>
* <function><a id="log"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Log</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the natural logarithm (base e) of a specified number.
This function is intended to be used as a plugin and logs 
its mathematical result. The input value must be greater than zero.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The number for which to calculate the natural logarithm.&lt;/param&gt;
&lt;returns&gt;The natural logarithm of the specified number.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when the input is less than or equal to zero.&lt;/exception&gt;</pre></function>
* <function><a id="log2"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Log2</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the base\-2 logarithm of a given number.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The value to compute the base\-2 logarithm for. Must be greater than zero.&lt;/param&gt;
&lt;returns&gt;The base\-2 logarithm of the input value.&lt;/returns&gt;</pre></function>
* <function><a id="log10"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Log10</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the base\-10 logarithm of a specified number.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The number to compute the logarithm for. Must be greater than zero.&lt;/param&gt;
&lt;returns&gt;The base\-10 logarithm of the input value.&lt;/returns&gt;</pre></function>
* <function><a id="sin"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Sin</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the sine of the specified angle, which is measured in radians.
This function uses the System.Math class&apos;s Sin method to perform the calculation.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The angle in radians for which to calculate the sine.&lt;/param&gt;
&lt;returns&gt;The sine of the specified angle as a double precision floating point number.&lt;/returns&gt;</pre></function>
* <function><a id="sinh"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Sinh</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the hyperbolic sine of a specified number.
This function uses the built\-in System.Math.Sinh method to compute 
the hyperbolic sine, which is defined as (e^x \- e^\-x) / 2 for any real number x.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The angle in radians whose hyperbolic sine value needs to be calculated.&lt;/param&gt;
&lt;returns&gt;The hyperbolic sine of the specified input.&lt;/returns&gt;</pre></function>
* <function><a id="sqrt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Sqrt</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the square root of a specified number.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The non\-negative value for which to compute the square root.&lt;/param&gt;
&lt;returns&gt;The square root of the specified number.&lt;/returns&gt;</pre></function>
* <function><a id="tan"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Tan</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the tangent of the specified angle.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The angle in radians for which to calculate the tangent.&lt;/param&gt;
&lt;returns&gt;The tangent of the specified angle.&lt;/returns&gt;</pre></function>
* <function><a id="tanh"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Tanh</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the hyperbolic tangent of a specified number using the Math.Tanh method.
This function is decorated with the PluginFunction attribute to register it as &quot;Tanh&quot;.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input value for which to compute the hyperbolic tangent.&lt;/param&gt;
&lt;returns&gt;The hyperbolic tangent of the input value.&lt;/returns&gt;</pre></function>
* <function><a id="abs"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Abs</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the absolute value of a specified number.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The number for which to calculate the absolute value.&lt;/param&gt;
&lt;returns&gt;The absolute value of the provided number.&lt;/returns&gt;</pre></function>
* <function><a id="round"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Round</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Rounds the specified input to the nearest integer using default rounding rules.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The value to round.&lt;/param&gt;
&lt;returns&gt;A double representing the rounded value.&lt;/returns&gt;</pre></function>
* <function><a id="truncate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Truncate</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Provides a plugin function to truncate a given double\-precision floating\-point number.
This function removes the fractional part of the number, returning only the integer part.
The result is equivalent to rounding towards zero and returns the nearest integral value.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input double\-precision floating\-point number to be truncated.&lt;/param&gt;
&lt;returns&gt;The truncated value as a double\-precision number with no fractional component.&lt;/returns&gt;</pre></function>
* <function><a id="degreestoradians"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DegreesToRadians</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> degrees) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts an angle measured in degrees to its equivalent in radians.
The conversion is based on the mathematical relationship that π radians 
is equal to 180 degrees. This function multiplies the input degrees by 
(π/180) to perform the conversion and returns the result as a double precision number.
&lt;/summary&gt;
&lt;param name=&quot;degrees&quot;&gt;The angle in degrees to be converted.&lt;/param&gt;
&lt;returns&gt;The equivalent angle measured in radians.&lt;/returns&gt;</pre></function>
* <function><a id="radianstodegrees"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RadiansToDegrees</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> radians) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts an angle from radians to degrees.
Multiplies the input radians by 180 and divides by Math.PI to perform the conversion.
&lt;/summary&gt;
&lt;param name=&quot;radians&quot;&gt;The angle in radians to be converted.&lt;/param&gt;
&lt;returns&gt;The equivalent angle in degrees.&lt;/returns&gt;</pre></function>
* <function><a id="pow"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Pow</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> a, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> b) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the power of a number. Returns the result of raising &apos;a&apos; to the power of &apos;b&apos;.
&lt;/summary&gt;
&lt;param name=&quot;a&quot;&gt;The base number.&lt;/param&gt;
&lt;param name=&quot;b&quot;&gt;The exponent value.&lt;/param&gt;
&lt;returns&gt;The result of &apos;a&apos; raised to the power of &apos;b&apos; as a double precision floating point number.&lt;/returns&gt;</pre></function>
* <function><a id="clamp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Clamp</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> min, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> max) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Clamps a specified value within the inclusive range of a minimum and maximum value.
If the value is less than the minimum, the method returns the minimum value.
If the value is greater than the maximum, it returns the maximum value.
Otherwise, it returns the value itself. This function utilizes .NET&apos;s built\-in Math.Clamp method for efficiency.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The value to clamp.&lt;/param&gt;
&lt;param name=&quot;min&quot;&gt;The minimum allowable value.&lt;/param&gt;
&lt;param name=&quot;max&quot;&gt;The maximum allowable value.&lt;/param&gt;
&lt;returns&gt;The clamped value within the specified range.&lt;/returns&gt;</pre></function>
* <function><a id="isprime"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsPrime</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">ulong</span> number) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether a given unsigned long integer is a prime number.
A prime number is a natural number greater than 1 that has no positive divisors other than 1 and itself.
&lt;/summary&gt;
&lt;param name=&quot;number&quot;&gt;The unsigned long integer to be tested for primality.&lt;/param&gt;
&lt;returns&gt;Returns true if the specified number is prime; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="greatestcommondivisor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GreatestCommonDivisor</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> a, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> b) -> <span style="color:#5FAFAF">int</span> -- (alias <span style="color:#D75F00">Gcd</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the greatest common divisor (GCD) of two integers using the Euclidean algorithm.
Also known as Highest Common Factor (HCF).
&lt;/summary&gt;
&lt;param name=&quot;a&quot;&gt;The first integer.&lt;/param&gt;
&lt;param name=&quot;b&quot;&gt;The second integer.&lt;/param&gt;
&lt;returns&gt;The greatest common divisor of the absolute values of the provided integers.&lt;/returns&gt;</pre></function>
* <function><a id="leastcommonmultiple"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">LeastCommonMultiple</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> a, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> b) -> <span style="color:#5FAFAF">int</span> -- (alias <span style="color:#D75F00">Lcm</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the Least Common Multiple (LCM) of two integers.
&lt;/summary&gt;
&lt;param name=&quot;a&quot;&gt;The first integer.&lt;/param&gt;
&lt;param name=&quot;b&quot;&gt;The second integer.&lt;/param&gt;
&lt;returns&gt;The LCM of the two integers. Returns 0 if either input is zero, as the LCM is undefined in that case.&lt;/returns&gt;</pre></function>
* <function><a id="ispoweroftwo"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsPowerOfTwo</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> value) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether a specified integer is a power of two.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The integer to check.&lt;/param&gt;
&lt;returns&gt;
True if the provided integer is greater than zero and a power of two; otherwise, false.
&lt;/returns&gt;</pre></function>
* <function><a id="nextpoweroftwo"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NextPowerOfTwo</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> value) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the next power of two greater than or equal to a given integer.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input integer for which the next power of two is calculated. Must be a non\-negative integer.&lt;/param&gt;
&lt;returns&gt;An integer representing the smallest power of two that is greater than or equal to the provided value. If the input is less than 1, returns 1.&lt;/returns&gt;</pre></function>
* <function><a id="signum"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Signum</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines the sign of a given double value.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The double value whose sign is to be determined.&lt;/param&gt;
&lt;returns&gt;Returns:
&nbsp;&nbsp;&nbsp;&nbsp;\* 0 if the value is zero,
&nbsp;&nbsp;&nbsp;&nbsp;\* 1 if the value is positive,
&nbsp;&nbsp;&nbsp;&nbsp;\* \-1 if the value is negative.&lt;/returns&gt;</pre></function>
