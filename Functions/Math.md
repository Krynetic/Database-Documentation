## Math
* <function><a id="acos"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Acos</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the arc cosine (inverse cosine) of a specified number.
The result is in radians and returns a value between 0 and π (inclusive).  
***input***: The number for which to calculate the inverse cosine. Must be within the range \[\-1, 1\].  
**Returns**: The arc cosine of the specified number.  

</pre></function>
* <function><a id="acosh"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Acosh</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the inverse hyperbolic cosine (acosh) of a specified number.  
***input***: The number for which to calculate the acosh value.  
**Returns**: The acosh of the specified number. Returns NaN if the input is less than 1.  

</pre></function>
* <function><a id="asin"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Asin</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the arc sine (inverse sine) of a specified number, returning the result in radians.
The value returned by this method is within the range \[\-π/2, π/2\].  
***input***: The angle, measured in radians, whose sine is to be calculated.  
**Returns**: The angle in radians from \-π/2 through π/2 whose sine is the specified number. If the value specified by input is less than \-1 or greater than 1, Asin returns NaN.  

</pre></function>
* <function><a id="asinh"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Asinh</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the inverse hyperbolic sine (asinh) of a specified number.  
***input***: The value for which to calculate the asinh.  
**Returns**: The inverse hyperbolic sine of the input number.  
**Examples**:
double result = MathExtension.Asinh(1.0);  

</pre></function>
* <function><a id="atan"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Atan</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the arctangent of a specified number.  
***input***: The angle in radians for which to calculate the tangent.  
**Returns**: The angle whose tangent is the specified number, measured in radians.  

</pre></function>
* <function><a id="atanh"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Atanh</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the inverse hyperbolic tangent (atanh) of a specified number.  
***input***: The number to calculate the inverse hyperbolic tangent for. The value must be in the range \-1 to 1, exclusive.  
**Returns**: The inverse hyperbolic tangent of the specified number.  

</pre></function>
* <function><a id="cbrt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Cbrt</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the cube root of a given number.  
***input***: The number for which to calculate the cube root.  
**Returns**: The cube root of the specified number.  

</pre></function>
* <function><a id="ceiling"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Ceiling</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Rounds the specified number up to the nearest whole number.
This function utilizes the built\-in System.Math.Ceiling method 
to perform the rounding operation and returns a double precision result.  
***input***: The decimal or floating\-point number to round up.  
**Returns**: A double representing the smallest integral value that is greater than or equal to the input.  

</pre></function>
* <function><a id="cos"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Cos</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the cosine of the specified angle, provided in radians.
The function leverages the System.Math library to perform this trigonometric computation.  
***input***: The angle in radians for which the cosine value is calculated.  
**Returns**: The cosine of the input angle as a double precision floating\-point number.  

</pre></function>
* <function><a id="cosh"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Cosh</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the hyperbolic cosine of a specified angle.
This method uses the built\-in Math.Cosh function to compute the result,
which represents the hyperbolic cosine for a given double precision floating\-point number.  
***input***: The angle in radians for which to calculate the hyperbolic cosine.  
**Returns**: The hyperbolic cosine of the specified input value.  

</pre></function>
* <function><a id="exp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Exp</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the exponential of the specified number using the mathematical constant e (Euler&apos;s number).
This function returns e raised to the power of the given input.  
***input***: The exponent value for which to calculate e^input.  
**Returns**: The result of e raised to the power of &apos;input&apos; as a double precision floating\-point number.  

</pre></function>
* <function><a id="floor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Floor</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the largest integer less than or equal to a specified decimal number.  
***input***: The decimal number to apply the floor operation.  
**Returns**: The largest integer less than or equal to the input value.  
**Remarks**:
This function is used for rounding down real numbers to their nearest integer.  

</pre></function>
* <function><a id="log"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Log</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the natural logarithm (base e) of a specified number.
This function is intended to be used as a plugin and logs 
its mathematical result. The input value must be greater than zero.  
***input***: The number for which to calculate the natural logarithm.  
**Returns**: The natural logarithm of the specified number.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when the input is less than or equal to zero.  

</pre></function>
* <function><a id="log2"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Log2</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the base\-2 logarithm of a given number.  
***input***: The value to compute the base\-2 logarithm for. Must be greater than zero.  
**Returns**: The base\-2 logarithm of the input value.  

</pre></function>
* <function><a id="log10"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Log10</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Computes the base\-10 logarithm of a specified number.  
***input***: The number to compute the logarithm for. Must be greater than zero.  
**Returns**: The base\-10 logarithm of the input value.  

</pre></function>
* <function><a id="sin"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Sin</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the sine of the specified angle, which is measured in radians.
This function uses the System.Math class&apos;s Sin method to perform the calculation.  
***input***: The angle in radians for which to calculate the sine.  
**Returns**: The sine of the specified angle as a double precision floating point number.  

</pre></function>
* <function><a id="sinh"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Sinh</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the hyperbolic sine of a specified number.
This function uses the built\-in System.Math.Sinh method to compute 
the hyperbolic sine, which is defined as (e^x \- e^\-x) / 2 for any real number x.  
***input***: The angle in radians whose hyperbolic sine value needs to be calculated.  
**Returns**: The hyperbolic sine of the specified input.  

</pre></function>
* <function><a id="sqrt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Sqrt</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the square root of a specified number.  
***input***: The non\-negative value for which to compute the square root.  
**Returns**: The square root of the specified number.  

</pre></function>
* <function><a id="tan"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Tan</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the tangent of the specified angle.  
***input***: The angle in radians for which to calculate the tangent.  
**Returns**: The tangent of the specified angle.  

</pre></function>
* <function><a id="tanh"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Tanh</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the hyperbolic tangent of a specified number using the Math.Tanh method.
This function is decorated with the PluginFunction attribute to register it as &quot;Tanh&quot;.  
***input***: The input value for which to compute the hyperbolic tangent.  
**Returns**: The hyperbolic tangent of the input value.  

</pre></function>
* <function><a id="abs"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Abs</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the absolute value of a specified number.  
***input***: The number for which to calculate the absolute value.  
**Returns**: The absolute value of the provided number.  

</pre></function>
* <function><a id="round"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Round</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Rounds the specified input to the nearest integer using default rounding rules.  
***input***: The value to round.  
**Returns**: A double representing the rounded value.  

</pre></function>
* <function><a id="truncate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Truncate</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> input) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Provides a plugin function to truncate a given double\-precision floating\-point number.
This function removes the fractional part of the number, returning only the integer part.
The result is equivalent to rounding towards zero and returns the nearest integral value.  
***input***: The input double\-precision floating\-point number to be truncated.  
**Returns**: The truncated value as a double\-precision number with no fractional component.  

</pre></function>
* <function><a id="degreestoradians"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DegreesToRadians</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> degrees) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts an angle measured in degrees to its equivalent in radians.
The conversion is based on the mathematical relationship that π radians 
is equal to 180 degrees. This function multiplies the input degrees by 
(π/180) to perform the conversion and returns the result as a double precision number.  
***degrees***: The angle in degrees to be converted.  
**Returns**: The equivalent angle measured in radians.  

</pre></function>
* <function><a id="radianstodegrees"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RadiansToDegrees</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> radians) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts an angle from radians to degrees.
Multiplies the input radians by 180 and divides by Math.PI to perform the conversion.  
***radians***: The angle in radians to be converted.  
**Returns**: The equivalent angle in degrees.  

</pre></function>
* <function><a id="pow"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Pow</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> a, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> b) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Computes the power of a number. Returns the result of raising &apos;a&apos; to the power of &apos;b&apos;.  
***a***: The base number.
***b***: The exponent value.  
**Returns**: The result of &apos;a&apos; raised to the power of &apos;b&apos; as a double precision floating point number.  

</pre></function>
* <function><a id="clamp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Clamp</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> min, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> max) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Clamps a specified value within the inclusive range of a minimum and maximum value.
If the value is less than the minimum, the method returns the minimum value.
If the value is greater than the maximum, it returns the maximum value.
Otherwise, it returns the value itself. This function utilizes .NET&apos;s built\-in Math.Clamp method for efficiency.  
***value***: The value to clamp.
***min***: The minimum allowable value.
***max***: The maximum allowable value.  
**Returns**: The clamped value within the specified range.  

</pre></function>
* <function><a id="isprime"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsPrime</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">ulong</span> number) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether a given unsigned long integer is a prime number.
A prime number is a natural number greater than 1 that has no positive divisors other than 1 and itself.  
***number***: The unsigned long integer to be tested for primality.  
**Returns**: Returns true if the specified number is prime; otherwise, false.  

</pre></function>
* <function><a id="greatestcommondivisor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GreatestCommonDivisor</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> a, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> b) -> <span style="color:#5FAFAF">int</span> -- (alias <span style="color:#D75F00">Gcd</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Computes the greatest common divisor (GCD) of two integers using the Euclidean algorithm.
Also known as Highest Common Factor (HCF).  
***a***: The first integer.
***b***: The second integer.  
**Returns**: The greatest common divisor of the absolute values of the provided integers.  

</pre></function>
* <function><a id="leastcommonmultiple"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">LeastCommonMultiple</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> a, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> b) -> <span style="color:#5FAFAF">int</span> -- (alias <span style="color:#D75F00">Lcm</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Computes the Least Common Multiple (LCM) of two integers.  
***a***: The first integer.
***b***: The second integer.  
**Returns**: The LCM of the two integers. Returns 0 if either input is zero, as the LCM is undefined in that case.  

</pre></function>
* <function><a id="ispoweroftwo"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsPowerOfTwo</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> value) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether a specified integer is a power of two.  
***value***: The integer to check.  
**Returns**: True if the provided integer is greater than zero and a power of two; otherwise, false.  

</pre></function>
* <function><a id="nextpoweroftwo"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NextPowerOfTwo</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> value) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the next power of two greater than or equal to a given integer.  
***value***: The input integer for which the next power of two is calculated. Must be a non\-negative integer.  
**Returns**: An integer representing the smallest power of two that is greater than or equal to the provided value. If the input is less than 1, returns 1.  

</pre></function>
* <function><a id="signum"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Signum</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines the sign of a given double value.  
***value***: The double value whose sign is to be determined.  
**Returns**: Returns:
    * 0 if the value is zero,
    * 1 if the value is positive,
    * \-1 if the value is negative.  

</pre></function>
