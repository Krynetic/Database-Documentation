# Krynetic Expression Function Reference

## Overview

This document is the authoritative reference for the **Krynetic Expression System**.  
It provides a complete, structured overview of all built-in and plugin-exposed functions available within Krynetic, spanning multiple runtimes, languages, and functional domains.

Krynetic is designed as a **high-performance, multi-language execution and expression platform**, combining deterministic utility functions with powerful evaluators such as **C#**, **JavaScript**, **Lua**, **Python**, **Ruby**, and **WASM**. The function set documented here covers cryptography, compression, encoding, math, parsing, templating, system utilities, networking, geolocation, security, and more—each engineered for composability, safety, and predictable behavior.

This document defines exactly what it can execute, compute, validate, and transform.

## Purpose of This Document

This reference serves as:

- **📘 A definitive function manual**  
  Complete signatures, return types, purity guarantees, and side-effect behavior.

- **🧭 A navigation index**  
  Functions are grouped by category and language for fast lookup and exploration.

- **📐 An execution contract**  
  Clear distinction between pure and state-modifying operations, ensuring deterministic usage in critical systems.

- **🧩 A composability guide**  
  Designed to encourage safe, expressive composition of functions across domains, enabling complex behavior to be built from small, well-defined primitives.

<br>

## Intended Audience

This documentation is intended for developers integrating Krynetic into:

- Automation and rule engines  
- Secure execution and sandboxed evaluation environments  
- Data processing and transformation pipelines  
- Templating and dynamic content systems  
- Infrastructure, observability, and platform tooling  

It assumes familiarity with programming concepts and focuses on precision, completeness, and technical clarity rather than introductory explanations.

## How to Use This Reference

- Use the **navigation index** to jump directly to a function or category  
- Treat each function entry as a **stable contract**  

<hr>

## Documentation Navigation Index
- <a id="index_csharp"></a>[CSharp](#csharp)
  - <a id="index_CSharp"></a>[CSharp](#csharp)
- <a id="index_javascript"></a>[JavaScript](#javascript)
  - <a id="index_JavaScript"></a>[JavaScript](#javascript)
- <a id="index_lua"></a>[Lua](#lua)
  - <a id="index_Lua"></a>[Lua](#lua)
- <a id="index_python"></a>[Python](#python)
  - <a id="index_Python"></a>[Python](#python)
- <a id="index_ruby"></a>[Ruby](#ruby)
  - <a id="index_Ruby"></a>[Ruby](#ruby)
- <a id="index_webassembly-wasm"></a>[WebAssembly (WASM)](#webassembly-wasm)
  - <a id="index_Wasm"></a>[Wasm](#wasm)
- <a id="index_elliptic-curve-digital-signature-algorithm-esdsa"></a>[Elliptic Curve Digital Signature Algorithm (ESDSA)](#elliptic-curve-digital-signature-algorithm-esdsa)
  - <a id="index_ECDSAGenerate"></a>[ECDSAGenerate](#ecdsagenerate)
  - <a id="index_ECDSASign"></a>[ECDSASign](#ecdsasign)
  - <a id="index_ECDSAVerify"></a>[ECDSAVerify](#ecdsaverify)
- <a id="index_hash-based-message-authentication-code-hmac"></a>[Hash-based Message Authentication Code (HMAC)](#hash-based-message-authentication-code-hmac)
  - <a id="index_HMACGenerate"></a>[HMACGenerate](#hmacgenerate)
  - <a id="index_HMACSign"></a>[HMACSign](#hmacsign)
  - <a id="index_HMACVerify"></a>[HMACVerify](#hmacverify)
- <a id="index_advanced-encryption-standard-aes"></a>[Advanced Encryption Standard (AES)](#advanced-encryption-standard-aes)
  - <a id="index_AESGenerate"></a>[AESGenerate](#aesgenerate)
  - <a id="index_AESEncrypt"></a>[AESEncrypt](#aesencrypt)
  - <a id="index_AESDecrypt"></a>[AESDecrypt](#aesdecrypt)
- <a id="index_rivest-shamir-adleman-rsa"></a>[Rivest Shamir Adleman (RSA)](#rivest-shamir-adleman-rsa)
  - <a id="index_RSAGenerate"></a>[RSAGenerate](#rsagenerate)
  - <a id="index_RSAEncrypt"></a>[RSAEncrypt](#rsaencrypt)
  - <a id="index_RSADecrypt"></a>[RSADecrypt](#rsadecrypt)
- <a id="index_barcode"></a>[Barcode](#barcode)
  - <a id="index_GenerateQRCode"></a>[GenerateQRCode](#generateqrcode)
- <a id="index_built-in"></a>[Built-In](#built-in)
  - <a id="index_Count"></a>[Count](#count)
  - <a id="index_Type"></a>[Type](#type)
- <a id="index_cache"></a>[Cache](#cache)
  - <a id="index_CacheGet"></a>[CacheGet](#cacheget)
  - <a id="index_CacheSet"></a>[CacheSet](#cacheset)
  - <a id="index_CacheRemove"></a>[CacheRemove](#cacheremove)
  - <a id="index_CacheClear"></a>[CacheClear](#cacheclear)
- <a id="index_captcha"></a>[Captcha](#captcha)
  - <a id="index_CreateCaptcha"></a>[CreateCaptcha](#createcaptcha)
  - <a id="index_ValidateCaptcha"></a>[ValidateCaptcha](#validatecaptcha)
- <a id="index_colors"></a>[Colors](#colors)
  - <a id="index_ParseHexColor"></a>[ParseHexColor](#parsehexcolor)
  - <a id="index_RGBToHSV"></a>[RGBToHSV](#rgbtohsv)
  - <a id="index_HSVToRGB"></a>[HSVToRGB](#hsvtorgb)
  - <a id="index_AdjustColorBrightness"></a>[AdjustColorBrightness](#adjustcolorbrightness)
  - <a id="index_InvertColor"></a>[InvertColor](#invertcolor)
  - <a id="index_GrayscaleColor"></a>[GrayscaleColor](#grayscalecolor)
  - <a id="index_BlendColor"></a>[BlendColor](#blendcolor)
  - <a id="index_AdjustColorSaturation"></a>[AdjustColorSaturation](#adjustcolorsaturation)
  - <a id="index_AdjustColorHue"></a>[AdjustColorHue](#adjustcolorhue)
  - <a id="index_AdjustColorAlpha"></a>[AdjustColorAlpha](#adjustcoloralpha)
  - <a id="index_MultiplyColor"></a>[MultiplyColor](#multiplycolor)
  - <a id="index_ScreenColor"></a>[ScreenColor](#screencolor)
  - <a id="index_OverlayColor"></a>[OverlayColor](#overlaycolor)
  - <a id="index_LightenColor"></a>[LightenColor](#lightencolor)
  - <a id="index_DarkenColor"></a>[DarkenColor](#darkencolor)
- <a id="index_compression"></a>[Compression](#compression)
  - <a id="index_ZstdCompress"></a>[ZstdCompress](#zstdcompress)
  - <a id="index_ZstdDecompress"></a>[ZstdDecompress](#zstddecompress)
  - <a id="index_GzipCompress"></a>[GzipCompress](#gzipcompress)
  - <a id="index_GzipDecompress"></a>[GzipDecompress](#gzipdecompress)
  - <a id="index_ZipCompress"></a>[ZipCompress](#zipcompress)
  - <a id="index_ZipDecompress"></a>[ZipDecompress](#zipdecompress)
  - <a id="index_BrotliCompress"></a>[BrotliCompress](#brotlicompress)
  - <a id="index_BrotliDecompress"></a>[BrotliDecompress](#brotlidecompress)
- <a id="index_containers"></a>[Containers](#containers)
  - <a id="index_Container"></a>[Container](#container)
- <a id="index_conversions"></a>[Conversions](#conversions)
  - <a id="index_ConvertAngle"></a>[ConvertAngle](#convertangle)
  - <a id="index_ConvertFuelEfficiency"></a>[ConvertFuelEfficiency](#convertfuelefficiency)
  - <a id="index_ConvertLuminance"></a>[ConvertLuminance](#convertluminance)
  - <a id="index_ConvertFrequency"></a>[ConvertFrequency](#convertfrequency)
  - <a id="index_ConvertForce"></a>[ConvertForce](#convertforce)
  - <a id="index_ConvertSoundLevel"></a>[ConvertSoundLevel](#convertsoundlevel)
  - <a id="index_ConvertPressure"></a>[ConvertPressure](#convertpressure)
  - <a id="index_ConvertEnergy"></a>[ConvertEnergy](#convertenergy)
  - <a id="index_ConvertPower"></a>[ConvertPower](#convertpower)
  - <a id="index_ConvertDataSize"></a>[ConvertDataSize](#convertdatasize)
  - <a id="index_ConvertMass"></a>[ConvertMass](#convertmass)
  - <a id="index_ConvertVolume"></a>[ConvertVolume](#convertvolume)
  - <a id="index_ConvertArea"></a>[ConvertArea](#convertarea)
  - <a id="index_ConvertSpeed"></a>[ConvertSpeed](#convertspeed)
  - <a id="index_ConvertTime"></a>[ConvertTime](#converttime)
  - <a id="index_ConvertLength"></a>[ConvertLength](#convertlength)
- <a id="index_cookies"></a>[Cookies](#cookies)
  - <a id="index_ParseCookie"></a>[ParseCookie](#parsecookie)
  - <a id="index_CreateCookie"></a>[CreateCookie](#createcookie)
- <a id="index_date"></a>[Date](#date)
  - <a id="index_ToUnixTimeSeconds"></a>[ToUnixTimeSeconds](#tounixtimeseconds)
  - <a id="index_ToUnixTimeMilliseconds"></a>[ToUnixTimeMilliseconds](#tounixtimemilliseconds)
  - <a id="index_FromUnixTimeSeconds"></a>[FromUnixTimeSeconds](#fromunixtimeseconds)
  - <a id="index_FromUnixTimeMilliseconds"></a>[FromUnixTimeMilliseconds](#fromunixtimemilliseconds)
  - <a id="index_NowPrecise"></a>[NowPrecise](#nowprecise)
  - <a id="index_Now"></a>[Now](#now)
  - <a id="index_NowNtp"></a>[NowNtp](#nowntp)
- <a id="index_documentation"></a>[Documentation](#documentation)
  - <a id="index_DocumentationTyped"></a>[DocumentationTyped](#documentationtyped)
  - <a id="index_Documentation"></a>[Documentation](#documentation)
- <a id="index_encoding"></a>[Encoding](#encoding)
  - <a id="index_Base64Encode"></a>[Base64Encode](#base64encode)
  - <a id="index_Base64Decode"></a>[Base64Decode](#base64decode)
- <a id="index_environment"></a>[Environment](#environment)
  - <a id="index_GetEnv"></a>[GetEnv](#getenv)
  - <a id="index_GetEnvOrThrow"></a>[GetEnvOrThrow](#getenvorthrow)
  - <a id="index_HasEnv"></a>[HasEnv](#hasenv)
  - <a id="index_GetAllEnv"></a>[GetAllEnv](#getallenv)
  - <a id="index_ExpandEnv"></a>[ExpandEnv](#expandenv)
  - <a id="index_SetEnv"></a>[SetEnv](#setenv)
  - <a id="index_ClearEnv"></a>[ClearEnv](#clearenv)
- <a id="index_exchange-rate"></a>[Exchange rate](#exchange-rate)
  - <a id="index_ExchangeRate"></a>[ExchangeRate](#exchangerate)
- <a id="index_extraction"></a>[Extraction](#extraction)
  - <a id="index_ExtractEmails"></a>[ExtractEmails](#extractemails)
  - <a id="index_ExtractUrls"></a>[ExtractUrls](#extracturls)
  - <a id="index_ExtractEmailUser"></a>[ExtractEmailUser](#extractemailuser)
- <a id="index_geolocation"></a>[Geolocation](#geolocation)
  - <a id="index_Haversine"></a>[Haversine](#haversine)
  - <a id="index_Vincenty"></a>[Vincenty](#vincenty)
  - <a id="index_InitialBearing"></a>[InitialBearing](#initialbearing)
  - <a id="index_PointAlongRoute"></a>[PointAlongRoute](#pointalongroute)
  - <a id="index_DegreesToMetersLat"></a>[DegreesToMetersLat](#degreestometerslat)
  - <a id="index_MetersToDegreesLon"></a>[MetersToDegreesLon](#meterstodegreeslon)
  - <a id="index_CompassDirection"></a>[CompassDirection](#compassdirection)
  - <a id="index_IsValidLat"></a>[IsValidLat](#isvalidlat)
  - <a id="index_IsValidLon"></a>[IsValidLon](#isvalidlon)
  - <a id="index_NormalizeLat"></a>[NormalizeLat](#normalizelat)
  - <a id="index_NormalizeLon"></a>[NormalizeLon](#normalizelon)
  - <a id="index_ParseLatLon"></a>[ParseLatLon](#parselatlon)
  - <a id="index_ParseLatLonWithMetadata"></a>[ParseLatLonWithMetadata](#parselatlonwithmetadata)
  - <a id="index_GeocodeLocation"></a>[GeocodeLocation](#geocodelocation)
- <a id="index_git"></a>[Git](#git)
  - <a id="index_GitCommits"></a>[GitCommits](#gitcommits)
- <a id="index_globally-unique-identifier-guid"></a>[Globally Unique Identifier (Guid)](#globally-unique-identifier-guid)
  - <a id="index_GenerateUuid1"></a>[GenerateUuid1](#generateuuid1)
  - <a id="index_GenerateUuid3"></a>[GenerateUuid3](#generateuuid3)
  - <a id="index_GenerateUuid4"></a>[GenerateUuid4](#generateuuid4)
  - <a id="index_GenerateUuid5"></a>[GenerateUuid5](#generateuuid5)
  - <a id="index_GenerateUuid6"></a>[GenerateUuid6](#generateuuid6)
  - <a id="index_GenerateCombGuid"></a>[GenerateCombGuid](#generatecombguid)
  - <a id="index_GenerateTimeOrderedGuid"></a>[GenerateTimeOrderedGuid](#generatetimeorderedguid)
- <a id="index_hashing"></a>[Hashing](#hashing)
  - <a id="index_CRC32"></a>[CRC32](#crc32)
  - <a id="index_CRC64"></a>[CRC64](#crc64)
  - <a id="index_XXHash32"></a>[XXHash32](#xxhash32)
  - <a id="index_XXHash64"></a>[XXHash64](#xxhash64)
  - <a id="index_Shake128"></a>[Shake128](#shake128)
  - <a id="index_Shake256"></a>[Shake256](#shake256)
  - <a id="index_SHA1"></a>[SHA1](#sha1)
  - <a id="index_SHA256"></a>[SHA256](#sha256)
  - <a id="index_SHA512"></a>[SHA512](#sha512)
  - <a id="index_SHA3_256"></a>[SHA3_256](#sha3256)
  - <a id="index_SHA3_384"></a>[SHA3_384](#sha3384)
  - <a id="index_SHA3_512"></a>[SHA3_512](#sha3512)
  - <a id="index_MD5"></a>[MD5](#md5)
  - <a id="index_HMAC_SHA256"></a>[HMAC_SHA256](#hmacsha256)
  - <a id="index_HMAC_SHA512"></a>[HMAC_SHA512](#hmacsha512)
- <a id="index_hypertext-transfer-protocol-http"></a>[Hypertext Transfer Protocol (HTTP)](#hypertext-transfer-protocol-http)
  - <a id="index_HTTP"></a>[HTTP](#http)
- <a id="index_json"></a>[JSON](#json)
  - <a id="index_ToJSON"></a>[ToJSON](#tojson)
  - <a id="index_FormatJSON"></a>[FormatJSON](#formatjson)
  - <a id="index_ParseJSON"></a>[ParseJSON](#parsejson)
- <a id="index_json-web-token-jwt"></a>[JSON Web Token (JWT)](#json-web-token-jwt)
  - <a id="index_EncodeJwt"></a>[EncodeJwt](#encodejwt)
  - <a id="index_DecodeJwt"></a>[DecodeJwt](#decodejwt)
  - <a id="index_IsJwt"></a>[IsJwt](#isjwt)
- <a id="index_large-language-model-llm"></a>[Large Language Model (LLM)](#large-language-model-llm)
  - <a id="index_AI_LMStudio"></a>[AI_LMStudio](#ailmstudio)
  - <a id="index_AI_OpenAI"></a>[AI_OpenAI](#aiopenai)
- <a id="index_lookup"></a>[Lookup](#lookup)
  - <a id="index_Lookup"></a>[Lookup](#lookup)
  - <a id="index_Parent"></a>[Parent](#parent)
  - <a id="index_Self"></a>[Self](#self)
- <a id="index_math"></a>[Math](#math)
  - <a id="index_Acos"></a>[Acos](#acos)
  - <a id="index_Acosh"></a>[Acosh](#acosh)
  - <a id="index_Asin"></a>[Asin](#asin)
  - <a id="index_Asinh"></a>[Asinh](#asinh)
  - <a id="index_Atan"></a>[Atan](#atan)
  - <a id="index_Atanh"></a>[Atanh](#atanh)
  - <a id="index_Cbrt"></a>[Cbrt](#cbrt)
  - <a id="index_Ceiling"></a>[Ceiling](#ceiling)
  - <a id="index_Cos"></a>[Cos](#cos)
  - <a id="index_Cosh"></a>[Cosh](#cosh)
  - <a id="index_Exp"></a>[Exp](#exp)
  - <a id="index_Floor"></a>[Floor](#floor)
  - <a id="index_Log"></a>[Log](#log)
  - <a id="index_Log2"></a>[Log2](#log2)
  - <a id="index_Log10"></a>[Log10](#log10)
  - <a id="index_Sin"></a>[Sin](#sin)
  - <a id="index_Sinh"></a>[Sinh](#sinh)
  - <a id="index_Sqrt"></a>[Sqrt](#sqrt)
  - <a id="index_Tan"></a>[Tan](#tan)
  - <a id="index_Tanh"></a>[Tanh](#tanh)
  - <a id="index_Abs"></a>[Abs](#abs)
  - <a id="index_Round"></a>[Round](#round)
  - <a id="index_Truncate"></a>[Truncate](#truncate)
  - <a id="index_DegreesToRadians"></a>[DegreesToRadians](#degreestoradians)
  - <a id="index_RadiansToDegrees"></a>[RadiansToDegrees](#radianstodegrees)
  - <a id="index_Pow"></a>[Pow](#pow)
  - <a id="index_Clamp"></a>[Clamp](#clamp)
  - <a id="index_IsPrime"></a>[IsPrime](#isprime)
  - <a id="index_GreatestCommonDivisor"></a>[GreatestCommonDivisor](#greatestcommondivisor)
  - <a id="index_LeastCommonMultiple"></a>[LeastCommonMultiple](#leastcommonmultiple)
  - <a id="index_IsPowerOfTwo"></a>[IsPowerOfTwo](#ispoweroftwo)
  - <a id="index_NextPowerOfTwo"></a>[NextPowerOfTwo](#nextpoweroftwo)
  - <a id="index_Signum"></a>[Signum](#signum)
- <a id="index_multipurpose-internet-mail-extensions-mime"></a>[Multipurpose Internet Mail Extensions (MIME)](#multipurpose-internet-mail-extensions-mime)
  - <a id="index_GetMimeFromExtension"></a>[GetMimeFromExtension](#getmimefromextension)
  - <a id="index_GetExtensionFromMime"></a>[GetExtensionFromMime](#getextensionfrommime)
- <a id="index_networking"></a>[Networking](#networking)
  - <a id="index_IsTcpPortOpen"></a>[IsTcpPortOpen](#istcpportopen)
  - <a id="index_Whois"></a>[Whois](#whois)
  - <a id="index_IsVPN"></a>[IsVPN](#isvpn)
- <a id="index_one-time-password-otp"></a>[One-Time Password (OTP)](#one-time-password-otp)
  - <a id="index_GenerateTOTP"></a>[GenerateTOTP](#generatetotp)
  - <a id="index_VerifyTOTP"></a>[VerifyTOTP](#verifytotp)
  - <a id="index_RemainingTOTPSeconds"></a>[RemainingTOTPSeconds](#remainingtotpseconds)
- <a id="index_parsing"></a>[Parsing](#parsing)
  - <a id="index_ParseBool"></a>[ParseBool](#parsebool)
  - <a id="index_ParseSByte"></a>[ParseSByte](#parsesbyte)
  - <a id="index_ParseByte"></a>[ParseByte](#parsebyte)
  - <a id="index_ParseInt16"></a>[ParseInt16](#parseint16)
  - <a id="index_ParseUInt16"></a>[ParseUInt16](#parseuint16)
  - <a id="index_ParseInt32"></a>[ParseInt32](#parseint32)
  - <a id="index_ParseUInt32"></a>[ParseUInt32](#parseuint32)
  - <a id="index_ParseInt64"></a>[ParseInt64](#parseint64)
  - <a id="index_ParseUInt64"></a>[ParseUInt64](#parseuint64)
  - <a id="index_ParseFloat"></a>[ParseFloat](#parsefloat)
  - <a id="index_ParseDouble"></a>[ParseDouble](#parsedouble)
  - <a id="index_ParseDecimal"></a>[ParseDecimal](#parsedecimal)
  - <a id="index_ParseTimeSpan"></a>[ParseTimeSpan](#parsetimespan)
  - <a id="index_ParseDateTimeOffset"></a>[ParseDateTimeOffset](#parsedatetimeoffset)
  - <a id="index_ParseIPAddress"></a>[ParseIPAddress](#parseipaddress)
  - <a id="index_ParseGuid"></a>[ParseGuid](#parseguid)
  - <a id="index_ParseSemVer"></a>[ParseSemVer](#parsesemver)
- <a id="index_password"></a>[Password](#password)
  - <a id="index_HashPassword"></a>[HashPassword](#hashpassword)
  - <a id="index_VerifyPassword"></a>[VerifyPassword](#verifypassword)
  - <a id="index_PasswordEntropyBits"></a>[PasswordEntropyBits](#passwordentropybits)
  - <a id="index_IsStrongPassword"></a>[IsStrongPassword](#isstrongpassword)
- <a id="index_path"></a>[Path](#path)
  - <a id="index_PathCombine"></a>[PathCombine](#pathcombine)
  - <a id="index_PathChild"></a>[PathChild](#pathchild)
  - <a id="index_PathParent"></a>[PathParent](#pathparent)
  - <a id="index_PathParts"></a>[PathParts](#pathparts)
  - <a id="index_PathId"></a>[PathId](#pathid)
  - <a id="index_PathDepth"></a>[PathDepth](#pathdepth)
- <a id="index_print"></a>[Print](#print)
  - <a id="index_Print"></a>[Print](#print)
- <a id="index_random"></a>[Random](#random)
  - <a id="index_RandomBool"></a>[RandomBool](#randombool)
  - <a id="index_RandomInt64"></a>[RandomInt64](#randomint64)
  - <a id="index_RandomUInt64"></a>[RandomUInt64](#randomuint64)
  - <a id="index_RandomInt32"></a>[RandomInt32](#randomint32)
  - <a id="index_RandomUInt32"></a>[RandomUInt32](#randomuint32)
  - <a id="index_RandomInt16"></a>[RandomInt16](#randomint16)
  - <a id="index_RandomUInt16"></a>[RandomUInt16](#randomuint16)
  - <a id="index_RandomSByte"></a>[RandomSByte](#randomsbyte)
  - <a id="index_RandomByte"></a>[RandomByte](#randombyte)
  - <a id="index_RandomFloat"></a>[RandomFloat](#randomfloat)
  - <a id="index_RandomDouble"></a>[RandomDouble](#randomdouble)
  - <a id="index_RandomDecimal"></a>[RandomDecimal](#randomdecimal)
  - <a id="index_RandomString"></a>[RandomString](#randomstring)
  - <a id="index_RandomBytes"></a>[RandomBytes](#randombytes)
  - <a id="index_RandomDateTime"></a>[RandomDateTime](#randomdatetime)
- <a id="index_really-simple-syndication-rss"></a>[Really Simple Syndication (RSS)](#really-simple-syndication-rss)
  - <a id="index_FetchRSS"></a>[FetchRSS](#fetchrss)
- <a id="index_regex"></a>[Regex](#regex)
  - <a id="index_RegexIsMatch"></a>[RegexIsMatch](#regexismatch)
  - <a id="index_RegexMatch"></a>[RegexMatch](#regexmatch)
  - <a id="index_RegexMatches"></a>[RegexMatches](#regexmatches)
- <a id="index_roman-numerals"></a>[Roman Numerals](#roman-numerals)
  - <a id="index_ToRomanNumeral"></a>[ToRomanNumeral](#toromannumeral)
  - <a id="index_FromRomanNumeral"></a>[FromRomanNumeral](#fromromannumeral)
- <a id="index_secure-string"></a>[Secure String](#secure-string)
  - <a id="index_ToSecureString"></a>[ToSecureString](#tosecurestring)
  - <a id="index_FromSecureString"></a>[FromSecureString](#fromsecurestring)
- <a id="index_string"></a>[String](#string)
  - <a id="index_Reverse"></a>[Reverse](#reverse)
  - <a id="index_RepeatString"></a>[RepeatString](#repeatstring)
  - <a id="index_Truncate"></a>[Truncate](#truncate)
  - <a id="index_CountWords"></a>[CountWords](#countwords)
  - <a id="index_RandomString"></a>[RandomString](#randomstring)
  - <a id="index_Slugify"></a>[Slugify](#slugify)
  - <a id="index_JoinStrings"></a>[JoinStrings](#joinstrings)
  - <a id="index_SplitString"></a>[SplitString](#splitstring)
  - <a id="index_RemoveWhitespace"></a>[RemoveWhitespace](#removewhitespace)
  - <a id="index_CountOccurrences"></a>[CountOccurrences](#countoccurrences)
  - <a id="index_StartsWithIgnoreCase"></a>[StartsWithIgnoreCase](#startswithignorecase)
  - <a id="index_EndsWithIgnoreCase"></a>[EndsWithIgnoreCase](#endswithignorecase)
  - <a id="index_ContainsIgnoreCase"></a>[ContainsIgnoreCase](#containsignorecase)
  - <a id="index_IsAlpha"></a>[IsAlpha](#isalpha)
  - <a id="index_IsAlphaNumeric"></a>[IsAlphaNumeric](#isalphanumeric)
  - <a id="index_IsLowerCase"></a>[IsLowerCase](#islowercase)
  - <a id="index_IsUpperCase"></a>[IsUpperCase](#isuppercase)
  - <a id="index_ToString"></a>[ToString](#tostring)
  - <a id="index_Format"></a>[Format](#format)
- <a id="index_string-casing"></a>[String Casing](#string-casing)
  - <a id="index_ToLowerCase"></a>[ToLowerCase](#tolowercase)
  - <a id="index_ToUpperCase"></a>[ToUpperCase](#touppercase)
  - <a id="index_ToTitleCase"></a>[ToTitleCase](#totitlecase)
  - <a id="index_ToKebabCase"></a>[ToKebabCase](#tokebabcase)
  - <a id="index_ToCamelCase"></a>[ToCamelCase](#tocamelcase)
  - <a id="index_ToSnakeCase"></a>[ToSnakeCase](#tosnakecase)
  - <a id="index_ToSentenceCase"></a>[ToSentenceCase](#tosentencecase)
- <a id="index_system"></a>[System](#system)
  - <a id="index_System_ThrottlerCallsPerSecond"></a>[System_ThrottlerCallsPerSecond](#systemthrottlercallspersecond)
  - <a id="index_System_IsInMemory"></a>[System_IsInMemory](#systemisinmemory)
  - <a id="index_System_Compact"></a>[System_Compact](#systemcompact)
  - <a id="index_System_ImportFromFile"></a>[System_ImportFromFile](#systemimportfromfile)
  - <a id="index_System_ExportToFile"></a>[System_ExportToFile](#systemexporttofile)
  - <a id="index_System_Shutdowm"></a>[System_Shutdowm](#systemshutdowm)
  - <a id="index_System_Info"></a>[System_Info](#systeminfo)
- <a id="index_temperature"></a>[Temperature](#temperature)
  - <a id="index_FahrenheitToCelsius"></a>[FahrenheitToCelsius](#fahrenheittocelsius)
  - <a id="index_FahrenheitToKelvin"></a>[FahrenheitToKelvin](#fahrenheittokelvin)
  - <a id="index_CelsiusToKelvin"></a>[CelsiusToKelvin](#celsiustokelvin)
  - <a id="index_CelsiusToFahrenheit"></a>[CelsiusToFahrenheit](#celsiustofahrenheit)
  - <a id="index_KelvinToCelsius"></a>[KelvinToCelsius](#kelvintocelsius)
  - <a id="index_KelvinToFahrenheit"></a>[KelvinToFahrenheit](#kelvintofahrenheit)
- <a id="index_templating"></a>[Templating](#templating)
  - <a id="index_SmartFormat"></a>[SmartFormat](#smartformat)
  - <a id="index_ScribanFormat"></a>[ScribanFormat](#scribanformat)
  - <a id="index_HandlebarsFormat"></a>[HandlebarsFormat](#handlebarsformat)
- <a id="index_uniform-resource-locator-url"></a>[Uniform Resource Locator (URL)](#uniform-resource-locator-url)
  - <a id="index_ParseUriQuery"></a>[ParseUriQuery](#parseuriquery)
  - <a id="index_ParseUriParts"></a>[ParseUriParts](#parseuriparts)
- <a id="index_user-agent-ua"></a>[User agent (UA)](#user-agent-ua)
  - <a id="index_ParseUserAgent"></a>[ParseUserAgent](#parseuseragent)
- <a id="index_validation"></a>[Validation](#validation)
  - <a id="index_IsValidEmail"></a>[IsValidEmail](#isvalidemail)
  - <a id="index_IsValidPhoneNumber"></a>[IsValidPhoneNumber](#isvalidphonenumber)
  - <a id="index_IsCreditCardInfoValid"></a>[IsCreditCardInfoValid](#iscreditcardinfovalid)
  - <a id="index_ValidateJson"></a>[ValidateJson](#validatejson)
  - <a id="index_IsUrl"></a>[IsUrl](#isurl)
  - <a id="index_IsNumeric"></a>[IsNumeric](#isnumeric)
  - <a id="index_IsGuid"></a>[IsGuid](#isguid)
- <a id="index_weather"></a>[Weather](#weather)
  - <a id="index_FetchWeather"></a>[FetchWeather](#fetchweather)
- <a id="index_x509certificates"></a>[X509Certificates](#x509certificates)
  - <a id="index_ParseX509"></a>[ParseX509](#parsex509)
  - <a id="index_CreateSelfSignedCertificate"></a>[CreateSelfSignedCertificate](#createselfsignedcertificate)
  - <a id="index_CreateCertificateAuthority"></a>[CreateCertificateAuthority](#createcertificateauthority)
  - <a id="index_SignCertificate"></a>[SignCertificate](#signcertificate)
  - <a id="index_CreateCertificateChain"></a>[CreateCertificateChain](#createcertificatechain)
## <a id="csharp" href="#index_csharp">CSharp</a>
* <function><a id="csharp"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">CSharp</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">CSharpScript</span>, <span style="color:#D75F00">Cs</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Evaluates C\# code using the CSharpScript runtime
&lt;/summary&gt;
&lt;example&gt;
&lt;code&gt;
{
&nbsp;&nbsp;&nbsp;&nbsp;&quot;input&quot;: {
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&quot;Globals.expression&quot;: &quot;$()&quot;,
&nbsp;&nbsp;&nbsp;&nbsp;},
&nbsp;&nbsp;&nbsp;&nbsp;&quot;code&quot;: &quot;&quot;&quot;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;using System; 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return 1234 \+ 5678;
&nbsp;&nbsp;&nbsp;&nbsp;&quot;&quot;&quot;,
&nbsp;&nbsp;&nbsp;&nbsp;&quot;result.expression&quot;: &quot;CSharp(code, input)&quot;
}
CSharp(
&lt;/code&gt;
&lt;/example&gt;
&lt;param name=&quot;code&quot;&gt;C\# code that should be executed&lt;/param&gt;
&lt;param name=&quot;input&quot;&gt;Configuration parameters when executing&lt;/param&gt;
&lt;returns&gt;Output from execution&lt;/returns&gt;</pre></function>
## CSharp
* <function><a id="csharp"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">CSharp</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">CSharpScript</span>, <span style="color:#D75F00">Cs</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Evaluates C\# code using the CSharpScript runtime
&lt;/summary&gt;
&lt;example&gt;
&lt;code&gt;
{
&nbsp;&nbsp;&nbsp;&nbsp;&quot;input&quot;: {
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&quot;Globals.expression&quot;: &quot;$()&quot;,
&nbsp;&nbsp;&nbsp;&nbsp;},
&nbsp;&nbsp;&nbsp;&nbsp;&quot;code&quot;: &quot;&quot;&quot;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;using System; 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return 1234 \+ 5678;
&nbsp;&nbsp;&nbsp;&nbsp;&quot;&quot;&quot;,
&nbsp;&nbsp;&nbsp;&nbsp;&quot;result.expression&quot;: &quot;CSharp(code, input)&quot;
}
CSharp(
&lt;/code&gt;
&lt;/example&gt;
&lt;param name=&quot;code&quot;&gt;C\# code that should be executed&lt;/param&gt;
&lt;param name=&quot;input&quot;&gt;Configuration parameters when executing&lt;/param&gt;
&lt;returns&gt;Output from execution&lt;/returns&gt;</pre></function>
## <a id="javascript" href="#index_javascript">JavaScript</a>
* <function><a id="javascript"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">JavaScript</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">Js</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Evaluates Javascript code using the YantraJS runtime
&lt;/summary&gt;
&lt;example&gt;
&lt;code&gt;
{
&nbsp;&nbsp;&nbsp;&nbsp;&quot;code&quot;: &quot;&quot;&quot;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;function fib(n) {
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return n &lt;= 1 ? n : fib(n \- 1) \+ fib(n \- 2);
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return fib(7);
&nbsp;&nbsp;&nbsp;&nbsp;&quot;&quot;&quot;,
&nbsp;&nbsp;&nbsp;&nbsp;&quot;result.expression&quot;: &quot;JavaScript(code)&quot;
}
&lt;/code&gt;
&lt;/example&gt;
&lt;param name=&quot;code&quot;&gt;Javascript code that should be executed&lt;/param&gt;
&lt;param name=&quot;input&quot;&gt;Configuration parameters when executing&lt;/param&gt;
&lt;returns&gt;Output from execution&lt;/returns&gt;</pre></function>
## JavaScript
* <function><a id="javascript"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">JavaScript</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">Js</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Evaluates Javascript code using the YantraJS runtime
&lt;/summary&gt;
&lt;example&gt;
&lt;code&gt;
{
&nbsp;&nbsp;&nbsp;&nbsp;&quot;code&quot;: &quot;&quot;&quot;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;function fib(n) {
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return n &lt;= 1 ? n : fib(n \- 1) \+ fib(n \- 2);
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return fib(7);
&nbsp;&nbsp;&nbsp;&nbsp;&quot;&quot;&quot;,
&nbsp;&nbsp;&nbsp;&nbsp;&quot;result.expression&quot;: &quot;JavaScript(code)&quot;
}
&lt;/code&gt;
&lt;/example&gt;
&lt;param name=&quot;code&quot;&gt;Javascript code that should be executed&lt;/param&gt;
&lt;param name=&quot;input&quot;&gt;Configuration parameters when executing&lt;/param&gt;
&lt;returns&gt;Output from execution&lt;/returns&gt;</pre></function>
## <a id="lua" href="#index_lua">Lua</a>
* <function><a id="lua"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Lua</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span></function>
## Lua
* <function><a id="lua"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Lua</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span></function>
## <a id="python" href="#index_python">Python</a>
* <function><a id="python"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Python</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">Py</span>)</function>
## Python
* <function><a id="python"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Python</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">Py</span>)</function>
## <a id="ruby" href="#index_ruby">Ruby</a>
* <function><a id="ruby"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Ruby</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">Rb</span>)</function>
## Ruby
* <function><a id="ruby"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Ruby</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">Rb</span>)</function>
## <a id="webassembly-wasm" href="#index_webassembly-wasm">WebAssembly (WASM)</a>
* <function><a id="wasm"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Wasm</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> wasmBytes, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> function = <span style="color:#D70000; margin-right:1px">"main"</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">WASM</span>)</function>
## WebAssembly (WASM)
* <function><a id="wasm"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Wasm</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">byte[]</span> wasmBytes, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> function = <span style="color:#D70000; margin-right:1px">"main"</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">WASM</span>)</function>
## <a id="elliptic-curve-digital-signature-algorithm-esdsa" href="#index_elliptic-curve-digital-signature-algorithm-esdsa">Elliptic Curve Digital Signature Algorithm (ESDSA)</a>
* <function><a id="ecdsagenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ECDSAGenerate</span>() -> <span style="color:#87AF00">ValueTuple\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates an ECDSA key pair using the NIST P\-256 curve.
&lt;/summary&gt;
&lt;returns&gt;A tuple containing the Base64\-encoded&lt;/returns&gt;</pre></function>
* <function><a id="ecdsasign"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ECDSASign</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64PrivateKey) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Signs a message using the ECDSA algorithm with a provided
&lt;/summary&gt;
&lt;param name=&quot;message&quot;&gt;The original message to be signed.&lt;/param&gt;
&lt;param name=&quot;base64PrivateKey&quot;&gt;The base64 encoded private key&lt;/param&gt;</pre></function>
* <function><a id="ecdsaverify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ECDSAVerify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Signature, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64PublicKey) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Verifies an ECDSA (Elliptic Curve Digital Signature Algorithm) signature for a given message.
&lt;/summary&gt;
&lt;param name=&quot;message&quot;&gt;The original message that was signed.&lt;/param&gt;
&lt;param name=&quot;base64Signature&quot;&gt;The base64 encoded string representing the signature to be verified.&lt;/param&gt;
&lt;param name=&quot;base64PublicKey&quot;&gt;The base64 encoded public key&lt;/param&gt;</pre></function>
## Elliptic Curve Digital Signature Algorithm (ESDSA)
* <function><a id="ecdsagenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ECDSAGenerate</span>() -> <span style="color:#87AF00">ValueTuple\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates an ECDSA key pair using the NIST P\-256 curve.
&lt;/summary&gt;
&lt;returns&gt;A tuple containing the Base64\-encoded&lt;/returns&gt;</pre></function>
* <function><a id="ecdsasign"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ECDSASign</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64PrivateKey) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Signs a message using the ECDSA algorithm with a provided
&lt;/summary&gt;
&lt;param name=&quot;message&quot;&gt;The original message to be signed.&lt;/param&gt;
&lt;param name=&quot;base64PrivateKey&quot;&gt;The base64 encoded private key&lt;/param&gt;</pre></function>
* <function><a id="ecdsaverify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ECDSAVerify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Signature, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64PublicKey) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Verifies an ECDSA (Elliptic Curve Digital Signature Algorithm) signature for a given message.
&lt;/summary&gt;
&lt;param name=&quot;message&quot;&gt;The original message that was signed.&lt;/param&gt;
&lt;param name=&quot;base64Signature&quot;&gt;The base64 encoded string representing the signature to be verified.&lt;/param&gt;
&lt;param name=&quot;base64PublicKey&quot;&gt;The base64 encoded public key&lt;/param&gt;</pre></function>
## <a id="hash-based-message-authentication-code-hmac" href="#index_hash-based-message-authentication-code-hmac">Hash-based Message Authentication Code (HMAC)</a>
* <function><a id="hmacgenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMACGenerate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> algorithm = <span style="color:#D70000; margin-right:1px">"SHA256"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a Base64 encoded HMAC key for the specified algorithm.
&lt;/summary&gt;
&lt;param name=&quot;algorithm&quot;&gt;The hashing algorithm to use for HMAC (e.g., &quot;SHA256&quot;).&lt;/param&gt;
&lt;returns&gt;A string representing the Base64 encoded HMAC key.&lt;/returns&gt;</pre></function>
* <function><a id="hmacsign"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMACSign</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> algorithm = <span style="color:#D70000; margin-right:1px">"SHA256"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;  
Creates an HMAC (Hash\-based Message Authentication Code) signature for a given message using the specified key and algorithm.  
&lt;/summary&gt;  
&lt;param name=&quot;message&quot;&gt;The input string message to be signed.&lt;/param&gt;  
&lt;param name=&quot;base64Key&quot;&gt;The base64\-encoded secret key used for creating the HMAC signature.&lt;/param&gt;  
&lt;param name=&quot;algorithm&quot;&gt;The hashing algorithm to use, with a default of &quot;SHA256&quot;.&lt;/param&gt;  
&lt;returns&gt;A base64\-encoded string representing the HMAC signature of the message.&lt;/returns&gt;  
&lt;remarks&gt;
This function uses UTF\-8 encoding for converting the input message into bytes. 
It creates an HMAC using the specified or default algorithm and computes the hash of the input message bytes.
The computed hash is then converted to a base64 string and returned as the signature.
Ensure that the key provided in base64 format is correctly decoded to prevent errors during HMAC generation.
&lt;/remarks&gt;</pre></function>
* <function><a id="hmacverify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMACVerify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Signature, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> algorithm = <span style="color:#D70000; margin-right:1px">"SHA256"</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Verifies if the provided Base64\-encoded HMAC signature matches the expected HMAC 
signature generated from the given message and key using the specified hash algorithm.
&lt;/summary&gt;
&lt;param name=&quot;message&quot;&gt;The original message for which the HMAC signature is to be verified.&lt;/param&gt;
&lt;param name=&quot;base64Signature&quot;&gt;The Base64\-encoded HMAC signature to verify against the expected signature.&lt;/param&gt;
&lt;param name=&quot;base64Key&quot;&gt;The Base64\-encoded key used to generate the HMAC signature.&lt;/param&gt;
&lt;param name=&quot;algorithm&quot;&gt;The hash algorithm to use for generating the HMAC signature (default is &quot;SHA256&quot;).&lt;/param&gt;
&lt;returns&gt;True if the provided signature matches the generated signature; otherwise, false.&lt;/returns&gt;</pre></function>
## Hash-based Message Authentication Code (HMAC)
* <function><a id="hmacgenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMACGenerate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> algorithm = <span style="color:#D70000; margin-right:1px">"SHA256"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a Base64 encoded HMAC key for the specified algorithm.
&lt;/summary&gt;
&lt;param name=&quot;algorithm&quot;&gt;The hashing algorithm to use for HMAC (e.g., &quot;SHA256&quot;).&lt;/param&gt;
&lt;returns&gt;A string representing the Base64 encoded HMAC key.&lt;/returns&gt;</pre></function>
* <function><a id="hmacsign"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMACSign</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> algorithm = <span style="color:#D70000; margin-right:1px">"SHA256"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;  
Creates an HMAC (Hash\-based Message Authentication Code) signature for a given message using the specified key and algorithm.  
&lt;/summary&gt;  
&lt;param name=&quot;message&quot;&gt;The input string message to be signed.&lt;/param&gt;  
&lt;param name=&quot;base64Key&quot;&gt;The base64\-encoded secret key used for creating the HMAC signature.&lt;/param&gt;  
&lt;param name=&quot;algorithm&quot;&gt;The hashing algorithm to use, with a default of &quot;SHA256&quot;.&lt;/param&gt;  
&lt;returns&gt;A base64\-encoded string representing the HMAC signature of the message.&lt;/returns&gt;  
&lt;remarks&gt;
This function uses UTF\-8 encoding for converting the input message into bytes. 
It creates an HMAC using the specified or default algorithm and computes the hash of the input message bytes.
The computed hash is then converted to a base64 string and returned as the signature.
Ensure that the key provided in base64 format is correctly decoded to prevent errors during HMAC generation.
&lt;/remarks&gt;</pre></function>
* <function><a id="hmacverify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMACVerify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Signature, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> algorithm = <span style="color:#D70000; margin-right:1px">"SHA256"</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Verifies if the provided Base64\-encoded HMAC signature matches the expected HMAC 
signature generated from the given message and key using the specified hash algorithm.
&lt;/summary&gt;
&lt;param name=&quot;message&quot;&gt;The original message for which the HMAC signature is to be verified.&lt;/param&gt;
&lt;param name=&quot;base64Signature&quot;&gt;The Base64\-encoded HMAC signature to verify against the expected signature.&lt;/param&gt;
&lt;param name=&quot;base64Key&quot;&gt;The Base64\-encoded key used to generate the HMAC signature.&lt;/param&gt;
&lt;param name=&quot;algorithm&quot;&gt;The hash algorithm to use for generating the HMAC signature (default is &quot;SHA256&quot;).&lt;/param&gt;
&lt;returns&gt;True if the provided signature matches the generated signature; otherwise, false.&lt;/returns&gt;</pre></function>
## <a id="advanced-encryption-standard-aes" href="#index_advanced-encryption-standard-aes">Advanced Encryption Standard (AES)</a>
* <function><a id="aesgenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AESGenerate</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySizeBits = <span style="color:#5FAFAF; margin-right:1px">256</span>) -> <span style="color:#87AF00">ValueTuple\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a new pair of AES Key and Initial Vector (IV)
&lt;/summary&gt;
&lt;param name=&quot;keySizeBits&quot;&gt;AES key size to be created&lt;/param&gt;
&lt;returns&gt;Key and IV pair&lt;/returns&gt;</pre></function>
* <function><a id="aesencrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AESEncrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> plaintext, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64IV) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Encrypts a given plaintext using AES encryption with the provided base64 key and IV.
&lt;/summary&gt;
&lt;param name=&quot;plaintext&quot;&gt;The text to be encrypted.&lt;/param&gt;
&lt;param name=&quot;base64Key&quot;&gt;The base64\-encoded AES key.&lt;/param&gt;
&lt;param name=&quot;base64IV&quot;&gt;The base64\-encoded IV.&lt;/param&gt;
&lt;returns&gt;The base64\-encoded encrypted ciphertext.&lt;/returns&gt;</pre></function>
* <function><a id="aesdecrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AESDecrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64CipherText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64IV) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Decrypts a base64\-encrypted data using the provided key and initialization vector.
&lt;/summary&gt;
&lt;param name=&quot;base64CipherText&quot;&gt;The encrypted base64 string.&lt;/param&gt;
&lt;param name=&quot;base64Key&quot;&gt;The base64\-encoded encryption key.&lt;/param&gt;
&lt;param name=&quot;base64IV&quot;&gt;The base64\-encoded initialization vector.&lt;/param&gt;
&lt;returns&gt;The decrypted AES data as a UTF8 string.&lt;/returns&gt;</pre></function>
## Advanced Encryption Standard (AES)
* <function><a id="aesgenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AESGenerate</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySizeBits = <span style="color:#5FAFAF; margin-right:1px">256</span>) -> <span style="color:#87AF00">ValueTuple\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a new pair of AES Key and Initial Vector (IV)
&lt;/summary&gt;
&lt;param name=&quot;keySizeBits&quot;&gt;AES key size to be created&lt;/param&gt;
&lt;returns&gt;Key and IV pair&lt;/returns&gt;</pre></function>
* <function><a id="aesencrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AESEncrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> plaintext, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64IV) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Encrypts a given plaintext using AES encryption with the provided base64 key and IV.
&lt;/summary&gt;
&lt;param name=&quot;plaintext&quot;&gt;The text to be encrypted.&lt;/param&gt;
&lt;param name=&quot;base64Key&quot;&gt;The base64\-encoded AES key.&lt;/param&gt;
&lt;param name=&quot;base64IV&quot;&gt;The base64\-encoded IV.&lt;/param&gt;
&lt;returns&gt;The base64\-encoded encrypted ciphertext.&lt;/returns&gt;</pre></function>
* <function><a id="aesdecrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AESDecrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64CipherText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64IV) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Decrypts a base64\-encrypted data using the provided key and initialization vector.
&lt;/summary&gt;
&lt;param name=&quot;base64CipherText&quot;&gt;The encrypted base64 string.&lt;/param&gt;
&lt;param name=&quot;base64Key&quot;&gt;The base64\-encoded encryption key.&lt;/param&gt;
&lt;param name=&quot;base64IV&quot;&gt;The base64\-encoded initialization vector.&lt;/param&gt;
&lt;returns&gt;The decrypted AES data as a UTF8 string.&lt;/returns&gt;</pre></function>
## <a id="rivest-shamir-adleman-rsa" href="#index_rivest-shamir-adleman-rsa">Rivest Shamir Adleman (RSA)</a>
* <function><a id="rsagenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RSAGenerate</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySize = <span style="color:#5FAFAF; margin-right:1px">2048</span>) -> <span style="color:#87AF00">ValueTuple\<string, string\></span></function>
* <function><a id="rsaencrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RSAEncrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> plaintext, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64PublicKey) -> <span style="color:#87AF00">string</span></function>
* <function><a id="rsadecrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RSADecrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64CipherText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64PrivateKey) -> <span style="color:#87AF00">string</span></function>
## Rivest Shamir Adleman (RSA)
* <function><a id="rsagenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RSAGenerate</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySize = <span style="color:#5FAFAF; margin-right:1px">2048</span>) -> <span style="color:#87AF00">ValueTuple\<string, string\></span></function>
* <function><a id="rsaencrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RSAEncrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> plaintext, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64PublicKey) -> <span style="color:#87AF00">string</span></function>
* <function><a id="rsadecrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RSADecrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64CipherText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64PrivateKey) -> <span style="color:#87AF00">string</span></function>
## <a id="barcode" href="#index_barcode">Barcode</a>
* <function><a id="generateqrcode"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateQRCode</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> payload, <span style="color:#87AF00; margin-left:1px; margin-right:1px">Generator</span> generator = <span style="color:#87AF00; margin-right:1px">Krynetic.Database.Plugins.BarcodePlugin+Generator.PNG</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> pixelsPerModule = <span style="color:#5FAFAF; margin-right:1px">20</span>) -> <span style="color:#87AF00">object</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a QR code based on the provided payload and image generator.
&lt;/summary&gt;
&lt;param name=&quot;payload&quot;&gt;The data to encode in the QR code.&lt;/param&gt;
&lt;param name=&quot;generator&quot;&gt;The type of image generator to use. Defaults to PNG.&lt;/param&gt;
&lt;param name=&quot;pixelsPerModule&quot;&gt;The number of pixels per module in the generated QR code.&lt;/param&gt;
&lt;returns&gt;An object representing the generated QR code, string or byte\[\].&lt;/returns&gt;</pre></function>
## Barcode
* <function><a id="generateqrcode"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateQRCode</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> payload, <span style="color:#87AF00; margin-left:1px; margin-right:1px">Generator</span> generator = <span style="color:#87AF00; margin-right:1px">Krynetic.Database.Plugins.BarcodePlugin+Generator.PNG</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> pixelsPerModule = <span style="color:#5FAFAF; margin-right:1px">20</span>) -> <span style="color:#87AF00">object</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a QR code based on the provided payload and image generator.
&lt;/summary&gt;
&lt;param name=&quot;payload&quot;&gt;The data to encode in the QR code.&lt;/param&gt;
&lt;param name=&quot;generator&quot;&gt;The type of image generator to use. Defaults to PNG.&lt;/param&gt;
&lt;param name=&quot;pixelsPerModule&quot;&gt;The number of pixels per module in the generated QR code.&lt;/param&gt;
&lt;returns&gt;An object representing the generated QR code, string or byte\[\].&lt;/returns&gt;</pre></function>
## <a id="built-in" href="#index_built-in">Built-In</a>
* <function><a id="count"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Count</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> dict) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Counts the number of key\-value pairs in a dictionary by retrieving the length value from the &apos;LengthKey&apos; special key.
&lt;/summary&gt;
&lt;param name=&quot;dict&quot;&gt;The input dictionary to be searched.&lt;/param&gt;
&lt;returns&gt;The count of key\-value pairs in the dictionary.&lt;/returns&gt;</pre></function>
* <function><a id="type"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Type</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> data) -> <span style="color:#87AF00">DatabaseType</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Returns the database type based on the provided data.
&lt;/summary&gt;
&lt;param name=&quot;data&quot;&gt;The data to determine the database type for.&lt;/param&gt;
&lt;returns&gt;The database type.&lt;/returns&gt;</pre></function>
## Built-In
* <function><a id="count"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Count</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> dict) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Counts the number of key\-value pairs in a dictionary by retrieving the length value from the &apos;LengthKey&apos; special key.
&lt;/summary&gt;
&lt;param name=&quot;dict&quot;&gt;The input dictionary to be searched.&lt;/param&gt;
&lt;returns&gt;The count of key\-value pairs in the dictionary.&lt;/returns&gt;</pre></function>
* <function><a id="type"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Type</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> data) -> <span style="color:#87AF00">DatabaseType</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Returns the database type based on the provided data.
&lt;/summary&gt;
&lt;param name=&quot;data&quot;&gt;The data to determine the database type for.&lt;/param&gt;
&lt;returns&gt;The database type.&lt;/returns&gt;</pre></function>
## <a id="cache" href="#index_cache">Cache</a>
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
## <a id="captcha" href="#index_captcha">Captcha</a>
* <function><a id="createcaptcha"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">CreateCaptcha</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length = <span style="color:#5FAFAF; margin-right:1px">6</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> width = <span style="color:#5FAFAF; margin-right:1px">200</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> height = <span style="color:#5FAFAF; margin-right:1px">70</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> ttlSeconds = <span style="color:#5FAFAF; margin-right:1px">300</span>) -> <span style="color:#87AF00">ValueTuple\<string, byte[]\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Creates a CAPTCHA challenge with the specified parameters.
&lt;/summary&gt;
&lt;returns&gt;A tuple containing the generated token and PNG image.&lt;/returns&gt;
&lt;param name=&quot;length&quot;&gt;The length of the CAPTCHA code. Defaults to 6.&lt;/param&gt;
&lt;param name=&quot;width&quot;&gt;The width of the CAPTCHA image. Defaults to 200 pixels.&lt;/param&gt;
&lt;param name=&quot;height&quot;&gt;The height of the CAPTCHA image. Defaults to 70 pixels.&lt;/param&gt;
&lt;param name=&quot;ttlSeconds&quot;&gt;The time\-to\-live (TTL) for the CAPTCHA in seconds. Defaults to 300.&lt;/param&gt;</pre></function>
* <function><a id="validatecaptcha"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">ValidateCaptcha</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> token, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> userInput) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Validates a CAPTCHA token against the stored tokens.
&lt;/summary&gt;
&lt;param name=&quot;token&quot;&gt;The CAPTCHA token to validate.&lt;/param&gt;
&lt;param name=&quot;userInput&quot;&gt;The user&apos;s input string for comparison.&lt;/param&gt;
&lt;returns&gt;True if the token is valid, false otherwise.&lt;/returns&gt;</pre></function>
## Captcha
* <function><a id="createcaptcha"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">CreateCaptcha</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length = <span style="color:#5FAFAF; margin-right:1px">6</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> width = <span style="color:#5FAFAF; margin-right:1px">200</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> height = <span style="color:#5FAFAF; margin-right:1px">70</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> ttlSeconds = <span style="color:#5FAFAF; margin-right:1px">300</span>) -> <span style="color:#87AF00">ValueTuple\<string, byte[]\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Creates a CAPTCHA challenge with the specified parameters.
&lt;/summary&gt;
&lt;returns&gt;A tuple containing the generated token and PNG image.&lt;/returns&gt;
&lt;param name=&quot;length&quot;&gt;The length of the CAPTCHA code. Defaults to 6.&lt;/param&gt;
&lt;param name=&quot;width&quot;&gt;The width of the CAPTCHA image. Defaults to 200 pixels.&lt;/param&gt;
&lt;param name=&quot;height&quot;&gt;The height of the CAPTCHA image. Defaults to 70 pixels.&lt;/param&gt;
&lt;param name=&quot;ttlSeconds&quot;&gt;The time\-to\-live (TTL) for the CAPTCHA in seconds. Defaults to 300.&lt;/param&gt;</pre></function>
* <function><a id="validatecaptcha"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">ValidateCaptcha</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> token, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> userInput) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Validates a CAPTCHA token against the stored tokens.
&lt;/summary&gt;
&lt;param name=&quot;token&quot;&gt;The CAPTCHA token to validate.&lt;/param&gt;
&lt;param name=&quot;userInput&quot;&gt;The user&apos;s input string for comparison.&lt;/param&gt;
&lt;returns&gt;True if the token is valid, false otherwise.&lt;/returns&gt;</pre></function>
## <a id="colors" href="#index_colors">Colors</a>
* <function><a id="parsehexcolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseHexColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> hexColorString) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a hexadecimal color string to an ARGBColor object. The input string can be in the format of 6 characters (RRGGBB) or 8 characters (AARRGGBB), 
optionally prefixed with &apos;\#&apos;. The function parses the hex string into its corresponding alpha, red, green, and blue components.
&lt;/summary&gt;
&lt;param name=&quot;hexColorString&quot;&gt;The hexadecimal color string to be converted. This should be in the format of &apos;\#RRGGBB&apos; or &apos;\#AARRGGBB&apos;, 
where RR is the red component, GG is the green component, BB is the blue component, and AA is the alpha component.&lt;/param&gt;
&lt;returns&gt;An ARGBColor object representing the parsed color components from the hexadecimal string. The Alpha (A) component defaults to 255 if not specified.&lt;/returns&gt;
&lt;exception cref=&quot;Exception&quot;&gt;Thrown when the input string is null or empty, when it does not conform to valid length 
requirements of 6 or 8 characters, contains non\-hexadecimal characters, or other parsing errors occur.&lt;/exception&gt;</pre></function>
* <function><a id="rgbtohsv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RGBToHSV</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c) -> <span style="color:#87AF00">HSVColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts an RGB color (with alpha transparency) to its HSV equivalent.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The ARGBColor object containing the red, green, blue, and alpha values.&lt;/param&gt;
&lt;returns&gt;A new HSVColor object representing the hue, saturation, value, and alpha of the original color.&lt;/returns&gt;</pre></function>
* <function><a id="hsvtorgb"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HSVToRGB</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">HSVColor</span> c) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a color from HSV (Hue, Saturation, Value) space to ARGB (Alpha, Red, Green, Blue) color format.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The HSVColor object containing the hue, saturation, value, and alpha components to be converted.&lt;/param&gt;
&lt;returns&gt;Returns an ARGBColor object representing the equivalent color in ARGB format.&lt;/returns&gt;</pre></function>
* <function><a id="adjustcolorbrightness"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AdjustColorBrightness</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> factor) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Adjusts the brightness of an ARGB color by a specified factor. The factor should be between \-1 and 1, where negative values darken the color, positive values brighten it, and zero leaves it unchanged.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The original ARGBColor to adjust.&lt;/param&gt;
&lt;param name=&quot;factor&quot;&gt;A double value representing the brightness adjustment factor. It must be within the range \[\-1, 1\].&lt;/param&gt;
&lt;returns&gt;A new ARGBColor instance with adjusted brightness based on the specified factor.&lt;/returns&gt;</pre></function>
* <function><a id="invertcolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">InvertColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Inverts the color of an ARGBColor object by subtracting each RGB component from 255, while retaining the alpha value.
This function utilizes a custom attribute PluginFunction to denote its behavior as part of a plugin system.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The original ARGBColor object whose color is to be inverted.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor object with the inverted RGB values and unchanged alpha value.&lt;/returns&gt;</pre></function>
* <function><a id="grayscalecolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GrayscaleColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a given color to its grayscale equivalent.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The original color to be converted.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor instance representing the grayscale version of the input color, preserving the alpha channel.&lt;/returns&gt;</pre></function>
* <function><a id="blendcolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">BlendColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> t) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Blends two ARGB colors based on the specified blend factor.
&lt;/summary&gt;
&lt;param name=&quot;a&quot;&gt;The first color to blend.&lt;/param&gt;
&lt;param name=&quot;b&quot;&gt;The second color to blend.&lt;/param&gt;
&lt;param name=&quot;t&quot;&gt;The blend factor ranging from 0.0 to 1.0, where 0.0 returns &apos;a&apos;, and 1.0 returns &apos;b&apos;.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor representing the blended result of &apos;a&apos; and &apos;b&apos; based on the blend factor &apos;t&apos;.&lt;/returns&gt;</pre></function>
* <function><a id="adjustcolorsaturation"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AdjustColorSaturation</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> factor) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Adjusts the saturation of a given ARGBColor by a specified factor.
The method converts the color to HSV (Hue, Saturation, Value), modifies 
its saturation component based on the input factor, and then converts it back 
to RGB. Saturation is clamped between 0 and 1 to ensure valid values.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The ARGBColor object representing the color whose saturation will be adjusted.&lt;/param&gt;
&lt;param name=&quot;factor&quot;&gt;A double value by which the saturation of the color will be multiplied. 
A factor greater than 1 increases saturation, while a factor between 0 and 1 decreases it.&lt;/param&gt;
&lt;returns&gt;An ARGBColor object with the adjusted saturation.&lt;/returns&gt;</pre></function>
* <function><a id="adjustcolorhue"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AdjustColorHue</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> degrees) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Adjusts the hue of a given ARGBColor by a specified number of degrees.
This function converts the color from RGB to HSV, modifies the hue,
and then converts it back to RGB.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The original ARGBColor that will have its hue adjusted.&lt;/param&gt;
&lt;param name=&quot;degrees&quot;&gt;The degree by which to adjust the hue. Positive values
increase the hue (clockwise), while negative values decrease it (counterclockwise).&lt;/param&gt;
&lt;returns&gt;An ARGBColor with the adjusted hue based on the input degrees.&lt;/returns&gt;</pre></function>
* <function><a id="adjustcoloralpha"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AdjustColorAlpha</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">byte</span> alpha) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Adjusts the alpha component of an ARGB color while preserving its red, green, and blue components.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The original ARGBColor object whose alpha is to be adjusted.&lt;/param&gt;
&lt;param name=&quot;alpha&quot;&gt;The new alpha value to set for the ARGBColor. Must be a byte between 0 and 255.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor object with the specified alpha component and the same red, green, and blue components as the original color.&lt;/returns&gt;</pre></function>
* <function><a id="multiplycolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">MultiplyColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Multiplies two ARGBColor values component\-wise and returns the result.
Each channel (A, R, G, B) of the resulting color is calculated by multiplying the corresponding channels
of the input colors and dividing by 255 to normalize the value back into a byte range.
&lt;/summary&gt;
&lt;param name=&quot;a&quot;&gt;The first ARGBColor instance.&lt;/param&gt;
&lt;param name=&quot;b&quot;&gt;The second ARGBColor instance.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor where each channel is the product of the corresponding channels in &apos;a&apos; and &apos;b&apos;,
divided by 255 to fit within the byte range. This represents a blend between the two colors based on their
alpha, red, green, and blue values respectively.&lt;/returns&gt;</pre></function>
* <function><a id="screencolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ScreenColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Combines two ARGBColor values using the &quot;screen&quot; blend mode. This method calculates the resulting color by applying the screen blending formula to each channel (red, green, and blue) while taking the maximum alpha value from either of the input colors.
&lt;/summary&gt;
&lt;param name=&quot;a&quot;&gt;The first ARGBColor object representing a color with its alpha, red, green, and blue components.&lt;/param&gt;
&lt;param name=&quot;b&quot;&gt;The second ARGBColor object representing a color with its alpha, red, green, and blue components.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor object where the result of the screen blend is applied to the color channels. The alpha channel contains the maximum alpha value from both input colors.&lt;/returns&gt;</pre></function>
* <function><a id="overlaycolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">OverlayColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Applies an overlay blending mode to two ARGBColor objects and returns the resulting color.
The overlay effect is a combination of multiply and screen blend modes, which enhances contrast by darkening or lightening colors depending on their luminance.
&lt;/summary&gt;
&lt;param name=&quot;a&quot;&gt;The first ARGBColor object representing the background color.&lt;/param&gt;
&lt;param name=&quot;b&quot;&gt;The second ARGBColor object representing the overlay color.&lt;/param&gt;
&lt;returns&gt;An ARGBColor object resulting from applying the overlay blending mode to the input colors.&lt;/returns&gt;</pre></function>
* <function><a id="lightencolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">LightenColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Lightens two ARGBColor objects by comparing their respective channels and selecting the maximum value for each channel.
&lt;/summary&gt;
&lt;param name=&quot;a&quot;&gt;The first ARGBColor object.&lt;/param&gt;
&lt;param name=&quot;b&quot;&gt;The second ARGBColor object.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor object where each channel is the maximum of the corresponding channels from the input colors.&lt;/returns&gt;</pre></function>
* <function><a id="darkencolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DarkenColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Darkens the specified ARGBColor by combining it with another ARGBColor.
The alpha channel is set to the maximum of both colors,
while the red, green, and blue channels are set to the minimum of each respective pair from the two colors.
&lt;/summary&gt;
&lt;param name=&quot;a&quot;&gt;The first ARGBColor.&lt;/param&gt;
&lt;param name=&quot;b&quot;&gt;The second ARGBColor used for darkening the first color.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor where:
\- The alpha channel is the maximum of both input colors&apos; alpha channels.
\- The red, green, and blue channels are the minimum of each respective pair from the two input colors.
&lt;/returns&gt;</pre></function>
## Colors
* <function><a id="parsehexcolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseHexColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> hexColorString) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a hexadecimal color string to an ARGBColor object. The input string can be in the format of 6 characters (RRGGBB) or 8 characters (AARRGGBB), 
optionally prefixed with &apos;\#&apos;. The function parses the hex string into its corresponding alpha, red, green, and blue components.
&lt;/summary&gt;
&lt;param name=&quot;hexColorString&quot;&gt;The hexadecimal color string to be converted. This should be in the format of &apos;\#RRGGBB&apos; or &apos;\#AARRGGBB&apos;, 
where RR is the red component, GG is the green component, BB is the blue component, and AA is the alpha component.&lt;/param&gt;
&lt;returns&gt;An ARGBColor object representing the parsed color components from the hexadecimal string. The Alpha (A) component defaults to 255 if not specified.&lt;/returns&gt;
&lt;exception cref=&quot;Exception&quot;&gt;Thrown when the input string is null or empty, when it does not conform to valid length 
requirements of 6 or 8 characters, contains non\-hexadecimal characters, or other parsing errors occur.&lt;/exception&gt;</pre></function>
* <function><a id="rgbtohsv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RGBToHSV</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c) -> <span style="color:#87AF00">HSVColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts an RGB color (with alpha transparency) to its HSV equivalent.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The ARGBColor object containing the red, green, blue, and alpha values.&lt;/param&gt;
&lt;returns&gt;A new HSVColor object representing the hue, saturation, value, and alpha of the original color.&lt;/returns&gt;</pre></function>
* <function><a id="hsvtorgb"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HSVToRGB</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">HSVColor</span> c) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a color from HSV (Hue, Saturation, Value) space to ARGB (Alpha, Red, Green, Blue) color format.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The HSVColor object containing the hue, saturation, value, and alpha components to be converted.&lt;/param&gt;
&lt;returns&gt;Returns an ARGBColor object representing the equivalent color in ARGB format.&lt;/returns&gt;</pre></function>
* <function><a id="adjustcolorbrightness"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AdjustColorBrightness</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> factor) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Adjusts the brightness of an ARGB color by a specified factor. The factor should be between \-1 and 1, where negative values darken the color, positive values brighten it, and zero leaves it unchanged.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The original ARGBColor to adjust.&lt;/param&gt;
&lt;param name=&quot;factor&quot;&gt;A double value representing the brightness adjustment factor. It must be within the range \[\-1, 1\].&lt;/param&gt;
&lt;returns&gt;A new ARGBColor instance with adjusted brightness based on the specified factor.&lt;/returns&gt;</pre></function>
* <function><a id="invertcolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">InvertColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Inverts the color of an ARGBColor object by subtracting each RGB component from 255, while retaining the alpha value.
This function utilizes a custom attribute PluginFunction to denote its behavior as part of a plugin system.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The original ARGBColor object whose color is to be inverted.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor object with the inverted RGB values and unchanged alpha value.&lt;/returns&gt;</pre></function>
* <function><a id="grayscalecolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GrayscaleColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a given color to its grayscale equivalent.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The original color to be converted.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor instance representing the grayscale version of the input color, preserving the alpha channel.&lt;/returns&gt;</pre></function>
* <function><a id="blendcolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">BlendColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> t) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Blends two ARGB colors based on the specified blend factor.
&lt;/summary&gt;
&lt;param name=&quot;a&quot;&gt;The first color to blend.&lt;/param&gt;
&lt;param name=&quot;b&quot;&gt;The second color to blend.&lt;/param&gt;
&lt;param name=&quot;t&quot;&gt;The blend factor ranging from 0.0 to 1.0, where 0.0 returns &apos;a&apos;, and 1.0 returns &apos;b&apos;.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor representing the blended result of &apos;a&apos; and &apos;b&apos; based on the blend factor &apos;t&apos;.&lt;/returns&gt;</pre></function>
* <function><a id="adjustcolorsaturation"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AdjustColorSaturation</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> factor) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Adjusts the saturation of a given ARGBColor by a specified factor.
The method converts the color to HSV (Hue, Saturation, Value), modifies 
its saturation component based on the input factor, and then converts it back 
to RGB. Saturation is clamped between 0 and 1 to ensure valid values.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The ARGBColor object representing the color whose saturation will be adjusted.&lt;/param&gt;
&lt;param name=&quot;factor&quot;&gt;A double value by which the saturation of the color will be multiplied. 
A factor greater than 1 increases saturation, while a factor between 0 and 1 decreases it.&lt;/param&gt;
&lt;returns&gt;An ARGBColor object with the adjusted saturation.&lt;/returns&gt;</pre></function>
* <function><a id="adjustcolorhue"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AdjustColorHue</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> degrees) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Adjusts the hue of a given ARGBColor by a specified number of degrees.
This function converts the color from RGB to HSV, modifies the hue,
and then converts it back to RGB.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The original ARGBColor that will have its hue adjusted.&lt;/param&gt;
&lt;param name=&quot;degrees&quot;&gt;The degree by which to adjust the hue. Positive values
increase the hue (clockwise), while negative values decrease it (counterclockwise).&lt;/param&gt;
&lt;returns&gt;An ARGBColor with the adjusted hue based on the input degrees.&lt;/returns&gt;</pre></function>
* <function><a id="adjustcoloralpha"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AdjustColorAlpha</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> c, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">byte</span> alpha) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Adjusts the alpha component of an ARGB color while preserving its red, green, and blue components.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The original ARGBColor object whose alpha is to be adjusted.&lt;/param&gt;
&lt;param name=&quot;alpha&quot;&gt;The new alpha value to set for the ARGBColor. Must be a byte between 0 and 255.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor object with the specified alpha component and the same red, green, and blue components as the original color.&lt;/returns&gt;</pre></function>
* <function><a id="multiplycolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">MultiplyColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Multiplies two ARGBColor values component\-wise and returns the result.
Each channel (A, R, G, B) of the resulting color is calculated by multiplying the corresponding channels
of the input colors and dividing by 255 to normalize the value back into a byte range.
&lt;/summary&gt;
&lt;param name=&quot;a&quot;&gt;The first ARGBColor instance.&lt;/param&gt;
&lt;param name=&quot;b&quot;&gt;The second ARGBColor instance.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor where each channel is the product of the corresponding channels in &apos;a&apos; and &apos;b&apos;,
divided by 255 to fit within the byte range. This represents a blend between the two colors based on their
alpha, red, green, and blue values respectively.&lt;/returns&gt;</pre></function>
* <function><a id="screencolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ScreenColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Combines two ARGBColor values using the &quot;screen&quot; blend mode. This method calculates the resulting color by applying the screen blending formula to each channel (red, green, and blue) while taking the maximum alpha value from either of the input colors.
&lt;/summary&gt;
&lt;param name=&quot;a&quot;&gt;The first ARGBColor object representing a color with its alpha, red, green, and blue components.&lt;/param&gt;
&lt;param name=&quot;b&quot;&gt;The second ARGBColor object representing a color with its alpha, red, green, and blue components.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor object where the result of the screen blend is applied to the color channels. The alpha channel contains the maximum alpha value from both input colors.&lt;/returns&gt;</pre></function>
* <function><a id="overlaycolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">OverlayColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Applies an overlay blending mode to two ARGBColor objects and returns the resulting color.
The overlay effect is a combination of multiply and screen blend modes, which enhances contrast by darkening or lightening colors depending on their luminance.
&lt;/summary&gt;
&lt;param name=&quot;a&quot;&gt;The first ARGBColor object representing the background color.&lt;/param&gt;
&lt;param name=&quot;b&quot;&gt;The second ARGBColor object representing the overlay color.&lt;/param&gt;
&lt;returns&gt;An ARGBColor object resulting from applying the overlay blending mode to the input colors.&lt;/returns&gt;</pre></function>
* <function><a id="lightencolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">LightenColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Lightens two ARGBColor objects by comparing their respective channels and selecting the maximum value for each channel.
&lt;/summary&gt;
&lt;param name=&quot;a&quot;&gt;The first ARGBColor object.&lt;/param&gt;
&lt;param name=&quot;b&quot;&gt;The second ARGBColor object.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor object where each channel is the maximum of the corresponding channels from the input colors.&lt;/returns&gt;</pre></function>
* <function><a id="darkencolor"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DarkenColor</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> a, <span style="color:#87AF00; margin-left:1px; margin-right:1px">ARGBColor</span> b) -> <span style="color:#87AF00">ARGBColor</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Darkens the specified ARGBColor by combining it with another ARGBColor.
The alpha channel is set to the maximum of both colors,
while the red, green, and blue channels are set to the minimum of each respective pair from the two colors.
&lt;/summary&gt;
&lt;param name=&quot;a&quot;&gt;The first ARGBColor.&lt;/param&gt;
&lt;param name=&quot;b&quot;&gt;The second ARGBColor used for darkening the first color.&lt;/param&gt;
&lt;returns&gt;A new ARGBColor where:
\- The alpha channel is the maximum of both input colors&apos; alpha channels.
\- The red, green, and blue channels are the minimum of each respective pair from the two input colors.
&lt;/returns&gt;</pre></function>
## <a id="compression" href="#index_compression">Compression</a>
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
## <a id="containers" href="#index_containers">Containers</a>
* <function><a id="container"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Container</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> containerName, <span style="color:#87AF00; margin-left:1px; margin-right:1px">param string[]</span> command) -> <span style="color:#87AF00">Task\<object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Executes a command within the specified container asynchronously.
&lt;/summary&gt;
&lt;param name=&quot;containerName&quot;&gt;The name of the container to execute the command in.&lt;/param&gt;
&lt;param name=&quot;command&quot;&gt;An array of strings representing the command and its arguments to be executed.&lt;/param&gt;
&lt;returns&gt;A task that represents the asynchronous operation. The task result contains an anonymous object with properties: StandardOutput, StandardError, ExitCode if successful; otherwise, a string message indicating the container does not exist.&lt;/returns&gt;</pre></function>
## Containers
* <function><a id="container"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Container</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> containerName, <span style="color:#87AF00; margin-left:1px; margin-right:1px">param string[]</span> command) -> <span style="color:#87AF00">Task\<object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Executes a command within the specified container asynchronously.
&lt;/summary&gt;
&lt;param name=&quot;containerName&quot;&gt;The name of the container to execute the command in.&lt;/param&gt;
&lt;param name=&quot;command&quot;&gt;An array of strings representing the command and its arguments to be executed.&lt;/param&gt;
&lt;returns&gt;A task that represents the asynchronous operation. The task result contains an anonymous object with properties: StandardOutput, StandardError, ExitCode if successful; otherwise, a string message indicating the container does not exist.&lt;/returns&gt;</pre></function>
## <a id="conversions" href="#index_conversions">Conversions</a>
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
## <a id="cookies" href="#index_cookies">Cookies</a>
* <function><a id="parsecookie"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseCookie</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cookie) -> <span style="color:#87AF00">Dictionary\<string, object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a cookie string into a dictionary of key\-value pairs, where values are dynamically typed objects.
&lt;/summary&gt;
&lt;param name=&quot;cookie&quot;&gt;The cookie string to parse.&lt;/param&gt;
&lt;returns&gt;A dictionary containing the parsed key\-value pairs from the cookie string. The keys are strings and
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;the values can be of type null, bool, int, long, double, DateTime, Guid, or string, depending on their format in the input.
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;If the input is empty or null, an empty dictionary with case\-insensitive string comparison for keys is returned.&lt;/returns&gt;</pre></function>
* <function><a id="createcookie"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CreateCookie</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> data) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Creates a cookie string from the provided key\-value pairs in the data dictionary.
Each key and value pair is concatenated with an &apos;=&apos; character, and multiple
pairs are separated by &apos;; &apos;. If the input dictionary contains no elements, an empty string is returned.
&lt;/summary&gt;
&lt;param name=&quot;data&quot;&gt;A dictionary containing cookie name and values as key\-value pairs.&lt;/param&gt;
&lt;returns&gt;A string representing a formatted cookie with all provided data.&lt;/returns&gt;</pre></function>
## Cookies
* <function><a id="parsecookie"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseCookie</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cookie) -> <span style="color:#87AF00">Dictionary\<string, object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a cookie string into a dictionary of key\-value pairs, where values are dynamically typed objects.
&lt;/summary&gt;
&lt;param name=&quot;cookie&quot;&gt;The cookie string to parse.&lt;/param&gt;
&lt;returns&gt;A dictionary containing the parsed key\-value pairs from the cookie string. The keys are strings and
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;the values can be of type null, bool, int, long, double, DateTime, Guid, or string, depending on their format in the input.
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;If the input is empty or null, an empty dictionary with case\-insensitive string comparison for keys is returned.&lt;/returns&gt;</pre></function>
* <function><a id="createcookie"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CreateCookie</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> data) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Creates a cookie string from the provided key\-value pairs in the data dictionary.
Each key and value pair is concatenated with an &apos;=&apos; character, and multiple
pairs are separated by &apos;; &apos;. If the input dictionary contains no elements, an empty string is returned.
&lt;/summary&gt;
&lt;param name=&quot;data&quot;&gt;A dictionary containing cookie name and values as key\-value pairs.&lt;/param&gt;
&lt;returns&gt;A string representing a formatted cookie with all provided data.&lt;/returns&gt;</pre></function>
## <a id="date" href="#index_date">Date</a>
* <function><a id="tounixtimeseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToUnixTimeSeconds</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset</span> dt) -> <span style="color:#5FAFAF">long</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a given DateTimeOffset to its Unix timestamp in seconds.
The Unix timestamp represents the number of seconds that have elapsed since 
00:00:00 UTC on 1 January 1970, not counting leap seconds.
&lt;/summary&gt;
&lt;param name=&quot;dt&quot;&gt;The DateTimeOffset value to convert.&lt;/param&gt;
&lt;returns&gt;A long integer representing the Unix timestamp in seconds.&lt;/returns&gt;</pre></function>
* <function><a id="tounixtimemilliseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToUnixTimeMilliseconds</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset</span> dt) -> <span style="color:#5FAFAF">long</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the given DateTimeOffset to Unix time expressed in milliseconds.
Unix time is defined as the number of milliseconds that have elapsed since 00:00:00 UTC on January 1, 1970 (excluding leap seconds).
&lt;/summary&gt;
&lt;param name=&quot;dt&quot;&gt;The DateTimeOffset value to convert.&lt;/param&gt;
&lt;returns&gt;A long integer representing the number of milliseconds since the Unix epoch.&lt;/returns&gt;</pre></function>
* <function><a id="fromunixtimeseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromUnixTimeSeconds</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">long</span> seconds) -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a Unix timestamp (seconds since January 1, 1970) to a 
DateTimeOffset value in the local time zone.
&lt;/summary&gt;
&lt;param name=&quot;seconds&quot;&gt;The number of seconds that have elapsed since January 1, 1970.&lt;/param&gt;
&lt;returns&gt;A DateTimeOffset object representing the equivalent date and time in the local time zone.&lt;/returns&gt;</pre></function>
* <function><a id="fromunixtimemilliseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromUnixTimeMilliseconds</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">long</span> milliseconds) -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the specified Unix time in milliseconds to a &lt;see cref=&quot;DateTimeOffset&quot;/&gt; value.
&lt;/summary&gt;
&lt;param name=&quot;milliseconds&quot;&gt;The number of 100\-nanosecond intervals since January 1, 1970 (midnight UTC).&lt;/param&gt;
&lt;returns&gt;A &lt;see cref=&quot;DateTimeOffset&quot;/&gt; value that is equivalent to the specified Unix time in milliseconds.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentOutOfRangeException&quot;&gt;Thrown when the input value represents a date earlier than January 1, 0001. \-OR\- Thrown when the input value represents a date later than December 31, 9999.&lt;/exception&gt;</pre></function>
* <function><a id="nowprecise"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NowPrecise</span>() -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Provides the current date and time in UTC with high precision.
&lt;/summary&gt;
&lt;returns&gt;A &lt;see cref=&quot;DateTimeOffset&quot;/&gt; object representing the current date and time in Coordinated Universal Time (UTC).&lt;/returns&gt;</pre></function>
* <function><a id="now"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Now</span>() -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the current date and time based on the loading options provided in the context.
This function returns a DateTimeOffset value representing &quot;now&quot; as defined within the context&apos;s 
LoadingOptions. It is used to ensure consistency in timing across different parts of an application 
or plugin system that share the same context configuration.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The LoaderContextData containing information about loading options, including the shared current time.&lt;/param&gt;
&lt;returns&gt;A DateTimeOffset value representing the current date and time as specified by the context&apos;s LoadingOptions.NowShared property.&lt;/returns&gt;</pre></function>
* <function><a id="nowntp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NowNtp</span>() -> <span style="color:#87AF00">Task\<DateTimeOffset\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the current network time from an NTP server asynchronously.
&lt;/summary&gt;
&lt;returns&gt;A task that represents the asynchronous operation, and contains a &lt;see cref=&quot;DateTimeOffset&quot;/&gt; object representing the current date and time as reported by the NTP server.&lt;/returns&gt;</pre></function>
## Date
* <function><a id="tounixtimeseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToUnixTimeSeconds</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset</span> dt) -> <span style="color:#5FAFAF">long</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a given DateTimeOffset to its Unix timestamp in seconds.
The Unix timestamp represents the number of seconds that have elapsed since 
00:00:00 UTC on 1 January 1970, not counting leap seconds.
&lt;/summary&gt;
&lt;param name=&quot;dt&quot;&gt;The DateTimeOffset value to convert.&lt;/param&gt;
&lt;returns&gt;A long integer representing the Unix timestamp in seconds.&lt;/returns&gt;</pre></function>
* <function><a id="tounixtimemilliseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToUnixTimeMilliseconds</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset</span> dt) -> <span style="color:#5FAFAF">long</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the given DateTimeOffset to Unix time expressed in milliseconds.
Unix time is defined as the number of milliseconds that have elapsed since 00:00:00 UTC on January 1, 1970 (excluding leap seconds).
&lt;/summary&gt;
&lt;param name=&quot;dt&quot;&gt;The DateTimeOffset value to convert.&lt;/param&gt;
&lt;returns&gt;A long integer representing the number of milliseconds since the Unix epoch.&lt;/returns&gt;</pre></function>
* <function><a id="fromunixtimeseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromUnixTimeSeconds</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">long</span> seconds) -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a Unix timestamp (seconds since January 1, 1970) to a 
DateTimeOffset value in the local time zone.
&lt;/summary&gt;
&lt;param name=&quot;seconds&quot;&gt;The number of seconds that have elapsed since January 1, 1970.&lt;/param&gt;
&lt;returns&gt;A DateTimeOffset object representing the equivalent date and time in the local time zone.&lt;/returns&gt;</pre></function>
* <function><a id="fromunixtimemilliseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromUnixTimeMilliseconds</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">long</span> milliseconds) -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the specified Unix time in milliseconds to a &lt;see cref=&quot;DateTimeOffset&quot;/&gt; value.
&lt;/summary&gt;
&lt;param name=&quot;milliseconds&quot;&gt;The number of 100\-nanosecond intervals since January 1, 1970 (midnight UTC).&lt;/param&gt;
&lt;returns&gt;A &lt;see cref=&quot;DateTimeOffset&quot;/&gt; value that is equivalent to the specified Unix time in milliseconds.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentOutOfRangeException&quot;&gt;Thrown when the input value represents a date earlier than January 1, 0001. \-OR\- Thrown when the input value represents a date later than December 31, 9999.&lt;/exception&gt;</pre></function>
* <function><a id="nowprecise"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NowPrecise</span>() -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Provides the current date and time in UTC with high precision.
&lt;/summary&gt;
&lt;returns&gt;A &lt;see cref=&quot;DateTimeOffset&quot;/&gt; object representing the current date and time in Coordinated Universal Time (UTC).&lt;/returns&gt;</pre></function>
* <function><a id="now"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Now</span>() -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the current date and time based on the loading options provided in the context.
This function returns a DateTimeOffset value representing &quot;now&quot; as defined within the context&apos;s 
LoadingOptions. It is used to ensure consistency in timing across different parts of an application 
or plugin system that share the same context configuration.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The LoaderContextData containing information about loading options, including the shared current time.&lt;/param&gt;
&lt;returns&gt;A DateTimeOffset value representing the current date and time as specified by the context&apos;s LoadingOptions.NowShared property.&lt;/returns&gt;</pre></function>
* <function><a id="nowntp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NowNtp</span>() -> <span style="color:#87AF00">Task\<DateTimeOffset\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the current network time from an NTP server asynchronously.
&lt;/summary&gt;
&lt;returns&gt;A task that represents the asynchronous operation, and contains a &lt;see cref=&quot;DateTimeOffset&quot;/&gt; object representing the current date and time as reported by the NTP server.&lt;/returns&gt;</pre></function>
## <a id="documentation" href="#index_documentation">Documentation</a>
* <function><a id="documentationtyped"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DocumentationTyped</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> function) -> <span style="color:#87AF00">XmlDocumentation</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the typed XML documentation for a specified function.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The loader context data containing information required to locate the documentation.&lt;/param&gt;
&lt;param name=&quot;function&quot;&gt;The name of the function whose documentation is being retrieved.&lt;/param&gt;
&lt;returns&gt;The parsed XML documentation object corresponding to the given function, or null if not found.&lt;/returns&gt;</pre></function>
* <function><a id="documentation"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Documentation</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> function) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the XML documentation for a specified function within the given loader context data.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The context containing information about the loaded plugin or library.&lt;/param&gt;
&lt;param name=&quot;function&quot;&gt;The name of the function whose documentation is to be retrieved.&lt;/param&gt;
&lt;returns&gt;A string representing the raw XML documentation for the specified function, 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;or null if no documentation is found.&lt;/returns&gt;</pre></function>
## Documentation
* <function><a id="documentationtyped"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DocumentationTyped</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> function) -> <span style="color:#87AF00">XmlDocumentation</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the typed XML documentation for a specified function.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The loader context data containing information required to locate the documentation.&lt;/param&gt;
&lt;param name=&quot;function&quot;&gt;The name of the function whose documentation is being retrieved.&lt;/param&gt;
&lt;returns&gt;The parsed XML documentation object corresponding to the given function, or null if not found.&lt;/returns&gt;</pre></function>
* <function><a id="documentation"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Documentation</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> function) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the XML documentation for a specified function within the given loader context data.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The context containing information about the loaded plugin or library.&lt;/param&gt;
&lt;param name=&quot;function&quot;&gt;The name of the function whose documentation is to be retrieved.&lt;/param&gt;
&lt;returns&gt;A string representing the raw XML documentation for the specified function, 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;or null if no documentation is found.&lt;/returns&gt;</pre></function>
## <a id="encoding" href="#index_encoding">Encoding</a>
* <function><a id="base64encode"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Base64Encode</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> plainText) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Encodes a given plain text string into its Base64 representation.
&lt;/summary&gt;
&lt;param name=&quot;plainText&quot;&gt;The input string to be encoded in UTF\-8 and then converted to Base64.&lt;/param&gt;
&lt;returns&gt;A Base64\-encoded string derived from the provided plain text.&lt;/returns&gt;</pre></function>
* <function><a id="base64decode"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Base64Decode</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64EncodedData) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Decodes a Base64 encoded string into its original UTF\-8 representation.
&lt;/summary&gt;
&lt;param name=&quot;base64EncodedData&quot;&gt;The Base64 encoded data to be decoded.&lt;/param&gt;
&lt;returns&gt;A string representing the decoded UTF\-8 text from the provided Base64 input.&lt;/returns&gt;</pre></function>
## Encoding
* <function><a id="base64encode"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Base64Encode</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> plainText) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Encodes a given plain text string into its Base64 representation.
&lt;/summary&gt;
&lt;param name=&quot;plainText&quot;&gt;The input string to be encoded in UTF\-8 and then converted to Base64.&lt;/param&gt;
&lt;returns&gt;A Base64\-encoded string derived from the provided plain text.&lt;/returns&gt;</pre></function>
* <function><a id="base64decode"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Base64Decode</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64EncodedData) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Decodes a Base64 encoded string into its original UTF\-8 representation.
&lt;/summary&gt;
&lt;param name=&quot;base64EncodedData&quot;&gt;The Base64 encoded data to be decoded.&lt;/param&gt;
&lt;returns&gt;A string representing the decoded UTF\-8 text from the provided Base64 input.&lt;/returns&gt;</pre></function>
## <a id="environment" href="#index_environment">Environment</a>
* <function><a id="getenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> defaultValue = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the value of an environment variable specified by the given key.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The name of the environment variable to retrieve.&lt;/param&gt;
&lt;param name=&quot;defaultValue&quot;&gt;
The default value to return if the environment variable is not found or its value is null.
This parameter is optional and defaults to null.
&lt;/param&gt;
&lt;returns&gt;The value of the environment variable as a string, or the specified default value
if the environment variable does not exist or has a null value.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;Thrown when the key argument is null or empty.&lt;/exception&gt;</pre></function>
* <function><a id="getenvorthrow"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetEnvOrThrow</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the value of a specified environment variable or throws an exception if it is not set.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The key of the environment variable to retrieve.&lt;/param&gt;
&lt;returns&gt;The value of the specified environment variable.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;
Thrown when the provided key is null or empty.
&lt;/exception&gt;
&lt;exception cref=&quot;InvalidOperationException&quot;&gt;
Thrown when the environment variable with the specified key is not set.
&lt;/exception&gt;</pre></function>
* <function><a id="hasenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HasEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Checks if a specified environment variable exists.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The key of the environment variable to check.&lt;/param&gt;
&lt;returns&gt;True if the environment variable with the given key exists and is not null; otherwise, false.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;Thrown when the provided key is null or empty.&lt;/exception&gt;</pre></function>
* <function><a id="getallenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetAllEnv</span>() -> <span style="color:#87AF00">Dictionary\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves all environment variables as a dictionary with the variable names as keys and their corresponding values as strings.
&lt;/summary&gt;
&lt;returns&gt;A dictionary where each key is an environment variable name (string) and each value is its associated value (string), or null if not set.&lt;/returns&gt;</pre></function>
* <function><a id="expandenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExpandEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Expands any environment variables contained within the specified string.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string that may contain environment variable references.&lt;/param&gt;
&lt;returns&gt;A new string with all environment variables in &quot;value&quot; replaced by their corresponding values.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;Thrown when the provided value is null.&lt;/exception&gt;</pre></function>
* <function><a id="setenv"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">SetEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Sets an environment variable for the current process.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The name of the environment variable to set. Cannot be null or empty.&lt;/param&gt;
&lt;param name=&quot;value&quot;&gt;The value of the environment variable. Can be null, which removes any existing value for the key.&lt;/param&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;
Thrown when the &lt;paramref name=&quot;key&quot;/&gt; is null or an empty string.
&lt;/exception&gt;</pre></function>
* <function><a id="clearenv"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">ClearEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Clears the environment variable specified by the given key. If the key exists in the environment variables, 
it is removed by setting its value to null.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The name of the environment variable to clear.&lt;/param&gt;</pre></function>
## Environment
* <function><a id="getenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> defaultValue = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the value of an environment variable specified by the given key.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The name of the environment variable to retrieve.&lt;/param&gt;
&lt;param name=&quot;defaultValue&quot;&gt;
The default value to return if the environment variable is not found or its value is null.
This parameter is optional and defaults to null.
&lt;/param&gt;
&lt;returns&gt;The value of the environment variable as a string, or the specified default value
if the environment variable does not exist or has a null value.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;Thrown when the key argument is null or empty.&lt;/exception&gt;</pre></function>
* <function><a id="getenvorthrow"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetEnvOrThrow</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the value of a specified environment variable or throws an exception if it is not set.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The key of the environment variable to retrieve.&lt;/param&gt;
&lt;returns&gt;The value of the specified environment variable.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;
Thrown when the provided key is null or empty.
&lt;/exception&gt;
&lt;exception cref=&quot;InvalidOperationException&quot;&gt;
Thrown when the environment variable with the specified key is not set.
&lt;/exception&gt;</pre></function>
* <function><a id="hasenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HasEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Checks if a specified environment variable exists.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The key of the environment variable to check.&lt;/param&gt;
&lt;returns&gt;True if the environment variable with the given key exists and is not null; otherwise, false.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;Thrown when the provided key is null or empty.&lt;/exception&gt;</pre></function>
* <function><a id="getallenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetAllEnv</span>() -> <span style="color:#87AF00">Dictionary\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves all environment variables as a dictionary with the variable names as keys and their corresponding values as strings.
&lt;/summary&gt;
&lt;returns&gt;A dictionary where each key is an environment variable name (string) and each value is its associated value (string), or null if not set.&lt;/returns&gt;</pre></function>
* <function><a id="expandenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExpandEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Expands any environment variables contained within the specified string.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string that may contain environment variable references.&lt;/param&gt;
&lt;returns&gt;A new string with all environment variables in &quot;value&quot; replaced by their corresponding values.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;Thrown when the provided value is null.&lt;/exception&gt;</pre></function>
* <function><a id="setenv"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">SetEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Sets an environment variable for the current process.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The name of the environment variable to set. Cannot be null or empty.&lt;/param&gt;
&lt;param name=&quot;value&quot;&gt;The value of the environment variable. Can be null, which removes any existing value for the key.&lt;/param&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;
Thrown when the &lt;paramref name=&quot;key&quot;/&gt; is null or an empty string.
&lt;/exception&gt;</pre></function>
* <function><a id="clearenv"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">ClearEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Clears the environment variable specified by the given key. If the key exists in the environment variables, 
it is removed by setting its value to null.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The name of the environment variable to clear.&lt;/param&gt;</pre></function>
## <a id="exchange-rate" href="#index_exchange-rate">Exchange rate</a>
* <function><a id="exchangerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExchangeRate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> from, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> to) -> <span style="color:#87AF00">Task\<decimal\></span></function>
## Exchange rate
* <function><a id="exchangerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExchangeRate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> from, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> to) -> <span style="color:#87AF00">Task\<decimal\></span></function>
## <a id="extraction" href="#index_extraction">Extraction</a>
* <function><a id="extractemails"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExtractEmails</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">List\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Extracts and returns a list of email addresses found within the specified input string using regular expressions.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The text from which to extract emails.&lt;/param&gt;
&lt;returns&gt;A list containing all email addresses identified in the input string.&lt;/returns&gt;</pre></function>
* <function><a id="extracturls"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExtractUrls</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">List\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Represents a plugin function that extracts URLs from the given input string.
This method uses regular expressions to identify and return a list of URL strings found in the input.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string from which URLs are extracted.&lt;/param&gt;
&lt;returns&gt;A list containing all URLs found within the input string. Returns an empty list if no URLs are found.&lt;/returns&gt;</pre></function>
* <function><a id="extractemailuser"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExtractEmailUser</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> email) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Extracts and returns the user portion of an email address.
&lt;/summary&gt;
&lt;param name=&quot;email&quot;&gt;The full email address from which to extract the user.&lt;/param&gt;
&lt;returns&gt;A string representing the user part before the &apos;@&apos; symbol, or an empty string if invalid or null.&lt;/returns&gt;</pre></function>
## Extraction
* <function><a id="extractemails"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExtractEmails</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">List\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Extracts and returns a list of email addresses found within the specified input string using regular expressions.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The text from which to extract emails.&lt;/param&gt;
&lt;returns&gt;A list containing all email addresses identified in the input string.&lt;/returns&gt;</pre></function>
* <function><a id="extracturls"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExtractUrls</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">List\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Represents a plugin function that extracts URLs from the given input string.
This method uses regular expressions to identify and return a list of URL strings found in the input.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string from which URLs are extracted.&lt;/param&gt;
&lt;returns&gt;A list containing all URLs found within the input string. Returns an empty list if no URLs are found.&lt;/returns&gt;</pre></function>
* <function><a id="extractemailuser"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExtractEmailUser</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> email) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Extracts and returns the user portion of an email address.
&lt;/summary&gt;
&lt;param name=&quot;email&quot;&gt;The full email address from which to extract the user.&lt;/param&gt;
&lt;returns&gt;A string representing the user part before the &apos;@&apos; symbol, or an empty string if invalid or null.&lt;/returns&gt;</pre></function>
## <a id="geolocation" href="#index_geolocation">Geolocation</a>
* <function><a id="haversine"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Haversine</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat2, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon2) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">GeoDistance</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the Haversine distance between two points on the Earth specified by their latitude and longitude.
&lt;/summary&gt;
&lt;param name=&quot;lat1&quot;&gt;Latitude of the first point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon1&quot;&gt;Longitude of the first point in degrees.&lt;/param&gt;
&lt;param name=&quot;lat2&quot;&gt;Latitude of the second point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon2&quot;&gt;Longitude of the second point in degrees.&lt;/param&gt;
&lt;returns&gt;The distance between the two points in kilometers.&lt;/returns&gt;</pre></function>
* <function><a id="vincenty"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Vincenty</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat2, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon2) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the distance between two points on Earth using the Vincenty formula for an ellipsoidal model.
This method accounts for the Earth&apos;s flattening and is highly accurate over long distances.
&lt;/summary&gt;
&lt;param name=&quot;lat1&quot;&gt;Latitude of the first point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon1&quot;&gt;Longitude of the first point in degrees.&lt;/param&gt;
&lt;param name=&quot;lat2&quot;&gt;Latitude of the second point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon2&quot;&gt;Longitude of the second point in degrees.&lt;/param&gt;
&lt;returns&gt;The distance between the two points in kilometers.&lt;/returns&gt;</pre></function>
* <function><a id="initialbearing"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">InitialBearing</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat2, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon2) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the initial bearing or forward azimuth needed to get from one geographic point 
to another. The result is expressed in degrees as a compass direction.
&lt;/summary&gt;
&lt;param name=&quot;lat1&quot;&gt;Latitude of the start point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon1&quot;&gt;Longitude of the start point in degrees.&lt;/param&gt;
&lt;param name=&quot;lat2&quot;&gt;Latitude of the end point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon2&quot;&gt;Longitude of the end point in degrees.&lt;/param&gt;
&lt;returns&gt;The initial bearing from the start point to the end point in degrees, ranging from 0 to 360.&lt;/returns&gt;</pre></function>
* <function><a id="pointalongroute"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PointAlongRoute</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat2, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon2, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> fraction) -> <span style="color:#87AF00">ValueTuple\<double, double\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes a point along the great\-circle route between two geographic coordinates.
&lt;/summary&gt;
&lt;param name=&quot;lat1&quot;&gt;Latitude of the starting point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon1&quot;&gt;Longitude of the starting point in degrees.&lt;/param&gt;
&lt;param name=&quot;lat2&quot;&gt;Latitude of the ending point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon2&quot;&gt;Longitude of the ending point in degrees.&lt;/param&gt;
&lt;param name=&quot;fraction&quot;&gt;
A fraction (0..1) representing how far along the route to calculate the point.
A value of 0.5 represents the midpoint, for example.
&lt;/param&gt;
&lt;returns&gt;A tuple containing the latitude and longitude of the computed point along the route.&lt;/returns&gt;</pre></function>
* <function><a id="degreestometerslat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DegreesToMetersLat</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> degreesLat) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts latitude in degrees to meters. 
The conversion assumes a spherical Earth model.
&lt;/summary&gt;
&lt;param name=&quot;degreesLat&quot;&gt;The latitude angle in degrees.&lt;/param&gt;
&lt;returns&gt;The equivalent distance in meters along the surface of the Earth at that latitude.&lt;/returns&gt;</pre></function>
* <function><a id="meterstodegreeslon"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">MetersToDegreesLon</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> meters, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> atLat) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a distance in meters to an equivalent angular distance in degrees of longitude at a given latitude.
&lt;/summary&gt;
&lt;param name=&quot;meters&quot;&gt;The distance in meters to be converted.&lt;/param&gt;
&lt;param name=&quot;atLat&quot;&gt;The latitude (in degrees) at which the conversion is performed. This affects the result due to Earth&apos;s curvature.&lt;/param&gt;
&lt;returns&gt;The equivalent angular distance in degrees of longitude corresponding to the given distance at the specified latitude.&lt;/returns&gt;</pre></function>
* <function><a id="compassdirection"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CompassDirection</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> bearingDegrees) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a given bearing in degrees to one of the 16 compass directions.
The function rounds the input bearing to the nearest compass direction using the specified formula.
&lt;/summary&gt;
&lt;param name=&quot;bearingDegrees&quot;&gt;The bearing angle in degrees, which should be between 0 and 360.&lt;/param&gt;
&lt;returns&gt;A string representing one of the 16 compass directions (e.g., &quot;N&quot;, &quot;NE&quot;, &quot;E&quot;).&lt;/returns&gt;
&lt;remarks&gt;
This function assumes a predefined array \`directions\` containing the 16 compass points
in clockwise order starting from &quot;N&quot; (North), such as {&quot;N&quot;, &quot;NNE&quot;, &quot;NE&quot;, ...}.
&lt;/remarks&gt;</pre></function>
* <function><a id="isvalidlat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsValidLat</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Checks if the provided latitude value is valid.
A valid latitude must be in the range from \-90 to 90 degrees, inclusive.
&lt;/summary&gt;
&lt;param name=&quot;lat&quot;&gt;The latitude value to check.&lt;/param&gt;
&lt;returns&gt;True if the latitude is within the valid range; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="isvalidlon"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsValidLon</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified longitude value is valid.
A valid longitude must be within the range of \-180 to 180 degrees, inclusive.
&lt;/summary&gt;
&lt;param name=&quot;lon&quot;&gt;The longitude value to validate.&lt;/param&gt;
&lt;returns&gt;true if the longitude is valid; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="normalizelat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NormalizeLat</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Normalizes a given latitude to fall within the range of \-90 to 90 degrees.
&lt;/summary&gt;
&lt;param name=&quot;lat&quot;&gt;The latitude value in degrees to be normalized.&lt;/param&gt;
&lt;returns&gt;A normalized latitude value within the range of \-90 to 90 degrees.&lt;/returns&gt;</pre></function>
* <function><a id="normalizelon"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NormalizeLon</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Normalizes a given longitude value to the range of \[\-180, 180\].
&lt;/summary&gt;
&lt;param name=&quot;lon&quot;&gt;The longitude in degrees that needs normalization.&lt;/param&gt;
&lt;returns&gt;The normalized longitude within the range of \[\-180, 180\] degrees.&lt;/returns&gt;</pre></function>
* <function><a id="parselatlon"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseLatLon</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">ValueTuple\<double, double\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a given string containing latitude and longitude information 
in various formats and returns them as double values representing 
the latitude and longitude.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;A string containing latitude and longitude 
details. The input can be in different notations including degrees,
minutes, seconds (DMS) format and decimal degrees.&lt;/param&gt;
&lt;returns&gt;A tuple containing two doubles where the first value is 
the latitude and the second is the longitude parsed from the given input.&lt;/returns&gt;</pre></function>
* <function><a id="parselatlonwithmetadata"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseLatLonWithMetadata</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">CoordinateResult</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the input string to extract latitude and longitude information along with metadata about the coordinate format.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string containing latitude and longitude data.&lt;/param&gt;
&lt;returns&gt;A CoordinateResult object that includes parsed latitude, longitude, the detected format,
whether the coordinates are in DMS (Degrees, Minutes, Seconds) or Decimal format, and the original input string.&lt;/returns&gt;</pre></function>
* <function><a id="geocodelocation"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GeocodeLocation</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> location, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> openweathermapApiKey) -> <span style="color:#87AF00">Task\<Dictionary\<string, double\>\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Geocodes the specified location using OpenWeatherMap&apos;s Geo API.
&lt;/summary&gt;
&lt;param name=&quot;location&quot;&gt;The location string to geocode.&lt;/param&gt;
&lt;param name=&quot;openweathermapApiKey&quot;&gt;Your OpenWeatherMap API key for authentication.&lt;/param&gt;
&lt;returns&gt;A dictionary containing latitude and longitude as keys with their respective double values,
or an empty dictionary if the location cannot be geocoded.&lt;/returns&gt;</pre></function>
## Geolocation
* <function><a id="haversine"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Haversine</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat2, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon2) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">GeoDistance</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the Haversine distance between two points on the Earth specified by their latitude and longitude.
&lt;/summary&gt;
&lt;param name=&quot;lat1&quot;&gt;Latitude of the first point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon1&quot;&gt;Longitude of the first point in degrees.&lt;/param&gt;
&lt;param name=&quot;lat2&quot;&gt;Latitude of the second point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon2&quot;&gt;Longitude of the second point in degrees.&lt;/param&gt;
&lt;returns&gt;The distance between the two points in kilometers.&lt;/returns&gt;</pre></function>
* <function><a id="vincenty"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Vincenty</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat2, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon2) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the distance between two points on Earth using the Vincenty formula for an ellipsoidal model.
This method accounts for the Earth&apos;s flattening and is highly accurate over long distances.
&lt;/summary&gt;
&lt;param name=&quot;lat1&quot;&gt;Latitude of the first point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon1&quot;&gt;Longitude of the first point in degrees.&lt;/param&gt;
&lt;param name=&quot;lat2&quot;&gt;Latitude of the second point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon2&quot;&gt;Longitude of the second point in degrees.&lt;/param&gt;
&lt;returns&gt;The distance between the two points in kilometers.&lt;/returns&gt;</pre></function>
* <function><a id="initialbearing"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">InitialBearing</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat2, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon2) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the initial bearing or forward azimuth needed to get from one geographic point 
to another. The result is expressed in degrees as a compass direction.
&lt;/summary&gt;
&lt;param name=&quot;lat1&quot;&gt;Latitude of the start point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon1&quot;&gt;Longitude of the start point in degrees.&lt;/param&gt;
&lt;param name=&quot;lat2&quot;&gt;Latitude of the end point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon2&quot;&gt;Longitude of the end point in degrees.&lt;/param&gt;
&lt;returns&gt;The initial bearing from the start point to the end point in degrees, ranging from 0 to 360.&lt;/returns&gt;</pre></function>
* <function><a id="pointalongroute"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PointAlongRoute</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon1, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat2, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon2, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> fraction) -> <span style="color:#87AF00">ValueTuple\<double, double\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes a point along the great\-circle route between two geographic coordinates.
&lt;/summary&gt;
&lt;param name=&quot;lat1&quot;&gt;Latitude of the starting point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon1&quot;&gt;Longitude of the starting point in degrees.&lt;/param&gt;
&lt;param name=&quot;lat2&quot;&gt;Latitude of the ending point in degrees.&lt;/param&gt;
&lt;param name=&quot;lon2&quot;&gt;Longitude of the ending point in degrees.&lt;/param&gt;
&lt;param name=&quot;fraction&quot;&gt;
A fraction (0..1) representing how far along the route to calculate the point.
A value of 0.5 represents the midpoint, for example.
&lt;/param&gt;
&lt;returns&gt;A tuple containing the latitude and longitude of the computed point along the route.&lt;/returns&gt;</pre></function>
* <function><a id="degreestometerslat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DegreesToMetersLat</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> degreesLat) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts latitude in degrees to meters. 
The conversion assumes a spherical Earth model.
&lt;/summary&gt;
&lt;param name=&quot;degreesLat&quot;&gt;The latitude angle in degrees.&lt;/param&gt;
&lt;returns&gt;The equivalent distance in meters along the surface of the Earth at that latitude.&lt;/returns&gt;</pre></function>
* <function><a id="meterstodegreeslon"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">MetersToDegreesLon</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> meters, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> atLat) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a distance in meters to an equivalent angular distance in degrees of longitude at a given latitude.
&lt;/summary&gt;
&lt;param name=&quot;meters&quot;&gt;The distance in meters to be converted.&lt;/param&gt;
&lt;param name=&quot;atLat&quot;&gt;The latitude (in degrees) at which the conversion is performed. This affects the result due to Earth&apos;s curvature.&lt;/param&gt;
&lt;returns&gt;The equivalent angular distance in degrees of longitude corresponding to the given distance at the specified latitude.&lt;/returns&gt;</pre></function>
* <function><a id="compassdirection"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CompassDirection</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> bearingDegrees) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a given bearing in degrees to one of the 16 compass directions.
The function rounds the input bearing to the nearest compass direction using the specified formula.
&lt;/summary&gt;
&lt;param name=&quot;bearingDegrees&quot;&gt;The bearing angle in degrees, which should be between 0 and 360.&lt;/param&gt;
&lt;returns&gt;A string representing one of the 16 compass directions (e.g., &quot;N&quot;, &quot;NE&quot;, &quot;E&quot;).&lt;/returns&gt;
&lt;remarks&gt;
This function assumes a predefined array \`directions\` containing the 16 compass points
in clockwise order starting from &quot;N&quot; (North), such as {&quot;N&quot;, &quot;NNE&quot;, &quot;NE&quot;, ...}.
&lt;/remarks&gt;</pre></function>
* <function><a id="isvalidlat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsValidLat</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Checks if the provided latitude value is valid.
A valid latitude must be in the range from \-90 to 90 degrees, inclusive.
&lt;/summary&gt;
&lt;param name=&quot;lat&quot;&gt;The latitude value to check.&lt;/param&gt;
&lt;returns&gt;True if the latitude is within the valid range; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="isvalidlon"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsValidLon</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified longitude value is valid.
A valid longitude must be within the range of \-180 to 180 degrees, inclusive.
&lt;/summary&gt;
&lt;param name=&quot;lon&quot;&gt;The longitude value to validate.&lt;/param&gt;
&lt;returns&gt;true if the longitude is valid; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="normalizelat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NormalizeLat</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Normalizes a given latitude to fall within the range of \-90 to 90 degrees.
&lt;/summary&gt;
&lt;param name=&quot;lat&quot;&gt;The latitude value in degrees to be normalized.&lt;/param&gt;
&lt;returns&gt;A normalized latitude value within the range of \-90 to 90 degrees.&lt;/returns&gt;</pre></function>
* <function><a id="normalizelon"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NormalizeLon</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Normalizes a given longitude value to the range of \[\-180, 180\].
&lt;/summary&gt;
&lt;param name=&quot;lon&quot;&gt;The longitude in degrees that needs normalization.&lt;/param&gt;
&lt;returns&gt;The normalized longitude within the range of \[\-180, 180\] degrees.&lt;/returns&gt;</pre></function>
* <function><a id="parselatlon"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseLatLon</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">ValueTuple\<double, double\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a given string containing latitude and longitude information 
in various formats and returns them as double values representing 
the latitude and longitude.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;A string containing latitude and longitude 
details. The input can be in different notations including degrees,
minutes, seconds (DMS) format and decimal degrees.&lt;/param&gt;
&lt;returns&gt;A tuple containing two doubles where the first value is 
the latitude and the second is the longitude parsed from the given input.&lt;/returns&gt;</pre></function>
* <function><a id="parselatlonwithmetadata"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseLatLonWithMetadata</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">CoordinateResult</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the input string to extract latitude and longitude information along with metadata about the coordinate format.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string containing latitude and longitude data.&lt;/param&gt;
&lt;returns&gt;A CoordinateResult object that includes parsed latitude, longitude, the detected format,
whether the coordinates are in DMS (Degrees, Minutes, Seconds) or Decimal format, and the original input string.&lt;/returns&gt;</pre></function>
* <function><a id="geocodelocation"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GeocodeLocation</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> location, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> openweathermapApiKey) -> <span style="color:#87AF00">Task\<Dictionary\<string, double\>\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Geocodes the specified location using OpenWeatherMap&apos;s Geo API.
&lt;/summary&gt;
&lt;param name=&quot;location&quot;&gt;The location string to geocode.&lt;/param&gt;
&lt;param name=&quot;openweathermapApiKey&quot;&gt;Your OpenWeatherMap API key for authentication.&lt;/param&gt;
&lt;returns&gt;A dictionary containing latitude and longitude as keys with their respective double values,
or an empty dictionary if the location cannot be geocoded.&lt;/returns&gt;</pre></function>
## <a id="git" href="#index_git">Git</a>
* <function><a id="gitcommits"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">GitCommits</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> path) -> <span style="color:#87AF00">Dictionary\<string, object\></span></function>
## Git
* <function><a id="gitcommits"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">GitCommits</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> path) -> <span style="color:#87AF00">Dictionary\<string, object\></span></function>
## <a id="globally-unique-identifier-guid" href="#index_globally-unique-identifier-guid">Globally Unique Identifier (Guid)</a>
* <function><a id="generateuuid1"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid1</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a UUID version 1 which is based on the current date and time, ensuring uniqueness through node and clock sequence identifiers.
This function creates a new GUID by manually setting its components to align with the UUID v1 specification.
&lt;/summary&gt;
&lt;returns&gt;A Guid representing a UUID version 1.&lt;/returns&gt;</pre></function>
* <function><a id="generateuuid3"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid3</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">Guid</span> namespaceId, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> name) -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a UUID version 3 using MD5 hashing algorithm based on the provided namespace identifier and name.
&lt;/summary&gt;
&lt;param name=&quot;namespaceId&quot;&gt;The GUID representing the UUID namespace.&lt;/param&gt;
&lt;param name=&quot;name&quot;&gt;The name used to generate the UUID.&lt;/param&gt;
&lt;returns&gt;A new Guid instance that represents a UUID version 3.&lt;/returns&gt;</pre></function>
* <function><a id="generateuuid4"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid4</span>() -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">GenerateUuid</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a Version 4 Universally Unique Identifier (UUID) as a string.
&lt;/summary&gt;
&lt;returns&gt;A string representing the generated UUID in its canonical form.&lt;/returns&gt;</pre></function>
* <function><a id="generateuuid5"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid5</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> namespaceId, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> name) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a UUID version 5 based on the given namespace ID and name.
This method utilizes SHA1 hashing to ensure uniqueness according to RFC 4122 specifications.
&lt;/summary&gt;
&lt;param name=&quot;namespaceId&quot;&gt;A valid GUID string representing the namespace.&lt;/param&gt;
&lt;param name=&quot;name&quot;&gt;The name or identifier for which the UUID is generated.&lt;/param&gt;
&lt;returns&gt;A string representation of the generated UUID version 5.&lt;/returns&gt;</pre></function>
* <function><a id="generateuuid6"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid6</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a version 1.6 UUID using the current system time as its basis.
The function creates a GUID by combining a timestamp and random bytes,
conforming to the variant 1.6 specification of the UUID standard.
&lt;/summary&gt;
&lt;returns&gt;A unique identifier (GUID) formatted according to Version 1.6.&lt;/returns&gt;</pre></function>
* <function><a id="generatecombguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateCombGuid</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a COMB (combined) GUID which is sorted lexicographically. 
The method creates a new GUID using the current time in UTC and combines it with 
a date\-based prefix to ensure that the GUIDs are ordered by creation time.
&lt;/summary&gt;
&lt;returns&gt;A new Guid object containing a timestamp component for sorting purposes.&lt;/returns&gt;</pre></function>
* <function><a id="generatetimeorderedguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateTimeOrderedGuid</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a time\-ordered GUID using the current system ticks to ensure temporal order.
This function is marked as unsafe and serves as a plugin function with the specified identifier.
&lt;/summary&gt;
&lt;returns&gt;A unique identifier (GUID) that incorporates the current UTC timestamp for ordering.&lt;/returns&gt;</pre></function>
## Globally Unique Identifier (Guid)
* <function><a id="generateuuid1"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid1</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a UUID version 1 which is based on the current date and time, ensuring uniqueness through node and clock sequence identifiers.
This function creates a new GUID by manually setting its components to align with the UUID v1 specification.
&lt;/summary&gt;
&lt;returns&gt;A Guid representing a UUID version 1.&lt;/returns&gt;</pre></function>
* <function><a id="generateuuid3"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid3</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">Guid</span> namespaceId, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> name) -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a UUID version 3 using MD5 hashing algorithm based on the provided namespace identifier and name.
&lt;/summary&gt;
&lt;param name=&quot;namespaceId&quot;&gt;The GUID representing the UUID namespace.&lt;/param&gt;
&lt;param name=&quot;name&quot;&gt;The name used to generate the UUID.&lt;/param&gt;
&lt;returns&gt;A new Guid instance that represents a UUID version 3.&lt;/returns&gt;</pre></function>
* <function><a id="generateuuid4"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid4</span>() -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">GenerateUuid</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a Version 4 Universally Unique Identifier (UUID) as a string.
&lt;/summary&gt;
&lt;returns&gt;A string representing the generated UUID in its canonical form.&lt;/returns&gt;</pre></function>
* <function><a id="generateuuid5"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid5</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> namespaceId, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> name) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a UUID version 5 based on the given namespace ID and name.
This method utilizes SHA1 hashing to ensure uniqueness according to RFC 4122 specifications.
&lt;/summary&gt;
&lt;param name=&quot;namespaceId&quot;&gt;A valid GUID string representing the namespace.&lt;/param&gt;
&lt;param name=&quot;name&quot;&gt;The name or identifier for which the UUID is generated.&lt;/param&gt;
&lt;returns&gt;A string representation of the generated UUID version 5.&lt;/returns&gt;</pre></function>
* <function><a id="generateuuid6"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid6</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a version 1.6 UUID using the current system time as its basis.
The function creates a GUID by combining a timestamp and random bytes,
conforming to the variant 1.6 specification of the UUID standard.
&lt;/summary&gt;
&lt;returns&gt;A unique identifier (GUID) formatted according to Version 1.6.&lt;/returns&gt;</pre></function>
* <function><a id="generatecombguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateCombGuid</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a COMB (combined) GUID which is sorted lexicographically. 
The method creates a new GUID using the current time in UTC and combines it with 
a date\-based prefix to ensure that the GUIDs are ordered by creation time.
&lt;/summary&gt;
&lt;returns&gt;A new Guid object containing a timestamp component for sorting purposes.&lt;/returns&gt;</pre></function>
* <function><a id="generatetimeorderedguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateTimeOrderedGuid</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a time\-ordered GUID using the current system ticks to ensure temporal order.
This function is marked as unsafe and serves as a plugin function with the specified identifier.
&lt;/summary&gt;
&lt;returns&gt;A unique identifier (GUID) that incorporates the current UTC timestamp for ordering.&lt;/returns&gt;</pre></function>
## <a id="hashing" href="#index_hashing">Hashing</a>
* <function><a id="crc32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CRC32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">uint</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the CRC\-32 hash of a given string using UTF\-8 encoding.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string for which to compute the CRC\-32 hash.&lt;/param&gt;
&lt;returns&gt;A uint representing the computed CRC\-32 hash value.&lt;/returns&gt;</pre></function>
* <function><a id="crc64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CRC64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the CRC\-64 checksum for a given input string.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string to calculate the checksum for.&lt;/param&gt;
&lt;returns&gt;An unsigned long representing the 64\-bit CRC checksum of the input string.&lt;/returns&gt;
&lt;remarks&gt;
This function uses UTF\-8 encoding to convert the input string into bytes and then computes the CRC\-64 hash.
&lt;/remarks&gt;</pre></function>
* <function><a id="xxhash32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">XXHash32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> seed = <span style="color:#5FAFAF; margin-right:1px">0</span>) -> <span style="color:#5FAFAF">uint</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes a 32\-bit hash value for the specified input string using the XXHash algorithm.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;param name=&quot;seed&quot;&gt;An optional seed value to initialize the hashing process. Default is 0.&lt;/param&gt;
&lt;returns&gt;A uint representing the computed hash value of the input string.&lt;/returns&gt;</pre></function>
* <function><a id="xxhash64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">XXHash64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">long</span> seed = <span style="color:#5FAFAF; margin-right:1px">0</span>) -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the XXH64 hash of a given input string using the specified seed value.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;param name=&quot;seed&quot;&gt;An optional seed value for the hash function. Defaults to 0 if not provided.&lt;/param&gt;
&lt;returns&gt;Returns the computed XXH64 hash as an unsigned long (ulong).&lt;/returns&gt;</pre></function>
* <function><a id="shake128"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Shake128</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> outputLength) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHAKE\-128 hash of a given input string using a specified output length.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;param name=&quot;outputLength&quot;&gt;The desired length of the output hash in bytes.&lt;/param&gt;
&lt;returns&gt;The SHAKE\-128 hash as a hexadecimal string representation.&lt;/returns&gt;</pre></function>
* <function><a id="shake256"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Shake256</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> outputLength) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHAKE\-256 hash of a given input string with specified output length.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;param name=&quot;outputLength&quot;&gt;The desired length of the hash output in bytes.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representing the SHAKE\-256 hash of the input with the specified length.&lt;/returns&gt;</pre></function>
* <function><a id="sha1"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA1</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the SHA\-1 hash for a given input string and returns it as a hexadecimal string.
This method utilizes the provided hashing function from the SHA1 class to ensure 
secure hashing of the specified value. The result is returned in a standard format 
suitable for verification or storage purposes. Usage involves passing the target 
string which will be hashed using the SHA\-1 algorithm, leveraging an external plugin 
mechanism.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to hash.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representation of the SHA\-1 hash of the input value.&lt;/returns&gt;</pre></function>
* <function><a id="sha256"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA256</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHA\-256 hash of the specified input string.
Utilizes a plugin function mechanism to apply the SHA\-256 hashing algorithm.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representing the SHA\-256 hash of the input.&lt;/returns&gt;</pre></function>
* <function><a id="sha512"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA512</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHA\-512 hash of a given input string.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representation of the SHA\-512 hash.&lt;/returns&gt;
&lt;remarks&gt;This method is marked as a plugin function for dynamic loading.&lt;/remarks&gt;</pre></function>
* <function><a id="sha3256"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA3_256</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHA\-3 256\-bit hash of a given input string.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;returns&gt;A hexadecimal representation of the SHA\-3 256\-bit hash.&lt;/returns&gt;</pre></function>
* <function><a id="sha3384"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA3_384</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHA3\-384 hash of a given input string.
This method utilizes a helper function to perform hashing with the specified algorithm.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;returns&gt;The resulting SHA3\-384 hash as a hexadecimal string.&lt;/returns&gt;</pre></function>
* <function><a id="sha3512"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA3_512</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHA3\-512 hash of a given input string.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;returns&gt;The SHA3\-512 hash represented as a hexadecimal string.&lt;/returns&gt;
&lt;remarks&gt;This method utilizes the HashData property of the SHA3\_512 class to perform hashing.&lt;/remarks&gt;</pre></function>
* <function><a id="md5"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">MD5</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the MD5 hash of a given input string.
This method utilizes a custom plugin function mechanism to process the string.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representing the MD5 hash of the input.&lt;/returns&gt;</pre></function>
* <function><a id="hmacsha256"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMAC_SHA256</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the HMAC\-SHA256 hash for a given key and value.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The secret key used in the hashing process.&lt;/param&gt;
&lt;param name=&quot;value&quot;&gt;The data to be hashed using the provided key.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representing the HMAC\-SHA256 hash of the input value.&lt;/returns&gt;</pre></function>
* <function><a id="hmacsha512"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMAC_SHA512</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the HMAC\-SHA512 hash for the given key and value.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The secret key used for hashing.&lt;/param&gt;
&lt;param name=&quot;value&quot;&gt;The input data to be hashed.&lt;/param&gt;
&lt;returns&gt;A string representation of the resulting HMAC\-SHA512 hash.&lt;/returns&gt;</pre></function>
## Hashing
* <function><a id="crc32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CRC32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">uint</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the CRC\-32 hash of a given string using UTF\-8 encoding.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string for which to compute the CRC\-32 hash.&lt;/param&gt;
&lt;returns&gt;A uint representing the computed CRC\-32 hash value.&lt;/returns&gt;</pre></function>
* <function><a id="crc64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CRC64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the CRC\-64 checksum for a given input string.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string to calculate the checksum for.&lt;/param&gt;
&lt;returns&gt;An unsigned long representing the 64\-bit CRC checksum of the input string.&lt;/returns&gt;
&lt;remarks&gt;
This function uses UTF\-8 encoding to convert the input string into bytes and then computes the CRC\-64 hash.
&lt;/remarks&gt;</pre></function>
* <function><a id="xxhash32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">XXHash32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> seed = <span style="color:#5FAFAF; margin-right:1px">0</span>) -> <span style="color:#5FAFAF">uint</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes a 32\-bit hash value for the specified input string using the XXHash algorithm.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;param name=&quot;seed&quot;&gt;An optional seed value to initialize the hashing process. Default is 0.&lt;/param&gt;
&lt;returns&gt;A uint representing the computed hash value of the input string.&lt;/returns&gt;</pre></function>
* <function><a id="xxhash64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">XXHash64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">long</span> seed = <span style="color:#5FAFAF; margin-right:1px">0</span>) -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the XXH64 hash of a given input string using the specified seed value.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;param name=&quot;seed&quot;&gt;An optional seed value for the hash function. Defaults to 0 if not provided.&lt;/param&gt;
&lt;returns&gt;Returns the computed XXH64 hash as an unsigned long (ulong).&lt;/returns&gt;</pre></function>
* <function><a id="shake128"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Shake128</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> outputLength) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHAKE\-128 hash of a given input string using a specified output length.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;param name=&quot;outputLength&quot;&gt;The desired length of the output hash in bytes.&lt;/param&gt;
&lt;returns&gt;The SHAKE\-128 hash as a hexadecimal string representation.&lt;/returns&gt;</pre></function>
* <function><a id="shake256"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Shake256</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> outputLength) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHAKE\-256 hash of a given input string with specified output length.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;param name=&quot;outputLength&quot;&gt;The desired length of the hash output in bytes.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representing the SHAKE\-256 hash of the input with the specified length.&lt;/returns&gt;</pre></function>
* <function><a id="sha1"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA1</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the SHA\-1 hash for a given input string and returns it as a hexadecimal string.
This method utilizes the provided hashing function from the SHA1 class to ensure 
secure hashing of the specified value. The result is returned in a standard format 
suitable for verification or storage purposes. Usage involves passing the target 
string which will be hashed using the SHA\-1 algorithm, leveraging an external plugin 
mechanism.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to hash.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representation of the SHA\-1 hash of the input value.&lt;/returns&gt;</pre></function>
* <function><a id="sha256"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA256</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHA\-256 hash of the specified input string.
Utilizes a plugin function mechanism to apply the SHA\-256 hashing algorithm.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representing the SHA\-256 hash of the input.&lt;/returns&gt;</pre></function>
* <function><a id="sha512"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA512</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHA\-512 hash of a given input string.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representation of the SHA\-512 hash.&lt;/returns&gt;
&lt;remarks&gt;This method is marked as a plugin function for dynamic loading.&lt;/remarks&gt;</pre></function>
* <function><a id="sha3256"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA3_256</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHA\-3 256\-bit hash of a given input string.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;returns&gt;A hexadecimal representation of the SHA\-3 256\-bit hash.&lt;/returns&gt;</pre></function>
* <function><a id="sha3384"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA3_384</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHA3\-384 hash of a given input string.
This method utilizes a helper function to perform hashing with the specified algorithm.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;returns&gt;The resulting SHA3\-384 hash as a hexadecimal string.&lt;/returns&gt;</pre></function>
* <function><a id="sha3512"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA3_512</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the SHA3\-512 hash of a given input string.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;returns&gt;The SHA3\-512 hash represented as a hexadecimal string.&lt;/returns&gt;
&lt;remarks&gt;This method utilizes the HashData property of the SHA3\_512 class to perform hashing.&lt;/remarks&gt;</pre></function>
* <function><a id="md5"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">MD5</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the MD5 hash of a given input string.
This method utilizes a custom plugin function mechanism to process the string.
&lt;/summary&gt;
&lt;param name=&quot;value&quot;&gt;The input string to be hashed.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representing the MD5 hash of the input.&lt;/returns&gt;</pre></function>
* <function><a id="hmacsha256"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMAC_SHA256</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the HMAC\-SHA256 hash for a given key and value.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The secret key used in the hashing process.&lt;/param&gt;
&lt;param name=&quot;value&quot;&gt;The data to be hashed using the provided key.&lt;/param&gt;
&lt;returns&gt;A hexadecimal string representing the HMAC\-SHA256 hash of the input value.&lt;/returns&gt;</pre></function>
* <function><a id="hmacsha512"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMAC_SHA512</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Computes the HMAC\-SHA512 hash for the given key and value.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The secret key used for hashing.&lt;/param&gt;
&lt;param name=&quot;value&quot;&gt;The input data to be hashed.&lt;/param&gt;
&lt;returns&gt;A string representation of the resulting HMAC\-SHA512 hash.&lt;/returns&gt;</pre></function>
## <a id="hypertext-transfer-protocol-http" href="#index_hypertext-transfer-protocol-http">Hypertext Transfer Protocol (HTTP)</a>
* <function><a id="http"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HTTP</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> url, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> method, <span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> headers, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> body, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> mode) -> <span style="color:#87AF00">Task\<object\></span></function>
## Hypertext Transfer Protocol (HTTP)
* <function><a id="http"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HTTP</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> url, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> method, <span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> headers, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> body, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> mode) -> <span style="color:#87AF00">Task\<object\></span></function>
## <a id="json" href="#index_json">JSON</a>
* <function><a id="tojson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToJSON</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> obj, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> indented) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Serializes an object to a JSON string with optional indentation.
&lt;/summary&gt;
&lt;param name=&quot;obj&quot;&gt;The object to serialize. Can be null.&lt;/param&gt;
&lt;param name=&quot;indented&quot;&gt;
A boolean indicating whether the output JSON should be indented for readability.
If true, the resulting JSON will include whitespace and line breaks.
If false, the resulting JSON will be compact without unnecessary spaces or newlines.
&lt;/param&gt;
&lt;returns&gt;A string representation of the serialized object in JSON format. Returns null if the input object is null.&lt;/returns&gt;</pre></function>
* <function><a id="formatjson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FormatJSON</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> json, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> indented = <span style="color:#5FAFAF; margin-right:1px">true</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Formats a JSON string with optional indentation.
&lt;/summary&gt;
&lt;param name=&quot;json&quot;&gt;The JSON string to format. Can be null.&lt;/param&gt;
&lt;param name=&quot;indented&quot;&gt;A boolean indicating whether the output should be indented for readability. Default is true.&lt;/param&gt;
&lt;returns&gt;A formatted JSON string if input is valid; otherwise, null.&lt;/returns&gt;</pre></function>
* <function><a id="parsejson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseJSON</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> json) -> <span style="color:#87AF00">object</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a JSON string and deserializes it into an object.
&lt;/summary&gt;
&lt;param name=&quot;json&quot;&gt;The JSON string to parse.&lt;/param&gt;
&lt;returns&gt;An object representing the deserialized data from the input JSON, or null if the input is null.&lt;/returns&gt;</pre></function>
## JSON
* <function><a id="tojson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToJSON</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> obj, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> indented) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Serializes an object to a JSON string with optional indentation.
&lt;/summary&gt;
&lt;param name=&quot;obj&quot;&gt;The object to serialize. Can be null.&lt;/param&gt;
&lt;param name=&quot;indented&quot;&gt;
A boolean indicating whether the output JSON should be indented for readability.
If true, the resulting JSON will include whitespace and line breaks.
If false, the resulting JSON will be compact without unnecessary spaces or newlines.
&lt;/param&gt;
&lt;returns&gt;A string representation of the serialized object in JSON format. Returns null if the input object is null.&lt;/returns&gt;</pre></function>
* <function><a id="formatjson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FormatJSON</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> json, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> indented = <span style="color:#5FAFAF; margin-right:1px">true</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Formats a JSON string with optional indentation.
&lt;/summary&gt;
&lt;param name=&quot;json&quot;&gt;The JSON string to format. Can be null.&lt;/param&gt;
&lt;param name=&quot;indented&quot;&gt;A boolean indicating whether the output should be indented for readability. Default is true.&lt;/param&gt;
&lt;returns&gt;A formatted JSON string if input is valid; otherwise, null.&lt;/returns&gt;</pre></function>
* <function><a id="parsejson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseJSON</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> json) -> <span style="color:#87AF00">object</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a JSON string and deserializes it into an object.
&lt;/summary&gt;
&lt;param name=&quot;json&quot;&gt;The JSON string to parse.&lt;/param&gt;
&lt;returns&gt;An object representing the deserialized data from the input JSON, or null if the input is null.&lt;/returns&gt;</pre></function>
## <a id="json-web-token-jwt" href="#index_json-web-token-jwt">JSON Web Token (JWT)</a>
* <function><a id="encodejwt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EncodeJwt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> claims, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> secret) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Encodes a JSON Web Token (JWT) using the specified claims and secret key.
The token is composed of three parts: header, payload, and signature. 
The header specifies the algorithm (&quot;HS256&quot;) used for signing the JWT, 
while the payload contains the claims to be encoded in the JWT. 
Finally, the signature is generated using HMAC SHA\-256 with the secret key.
&lt;/summary&gt;
&lt;param name=&quot;claims&quot;&gt;A dictionary of claims to include in the JWT.&lt;/param&gt;
&lt;param name=&quot;secret&quot;&gt;The secret key used for signing the JWT.&lt;/param&gt;
&lt;returns&gt;A string representing the encoded JWT.&lt;/returns&gt;</pre></function>
* <function><a id="decodejwt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DecodeJwt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> token, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> secret = <span style="color:#D70000; margin-right:1px">null</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> includeMetadata = <span style="color:#5FAFAF; margin-right:1px">false</span>) -> <span style="color:#87AF00">IDictionary\<string, object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Decodes a JWT (JSON Web Token) and validates its HMAC\-SHA256 signature using an optional secret.
Throws exceptions for invalid tokens or signatures. Optionally includes token metadata in the output.
&lt;/summary&gt;
&lt;param name=&quot;token&quot;&gt;The JWT to decode.&lt;/param&gt;
&lt;param name=&quot;secret&quot;&gt;Optional secret key used to validate the signature (for HMAC\-SHA256).&lt;/param&gt;
&lt;param name=&quot;includeMetadata&quot;&gt;
Whether to include the JWT header and signature as metadata in the returned dictionary.
&lt;/param&gt;
&lt;returns&gt;A dictionary containing the decoded JWT payload, optionally including header and signature metadata.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when the token is empty or null.&lt;/exception&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown when the token does not have exactly three parts separated by dots.&lt;/exception&gt;
&lt;exception cref=&quot;NotSupportedException&quot;&gt;
Thrown when the algorithm specified in the JWT header is not HS256.
&lt;/exception&gt;
&lt;exception cref=&quot;CryptographicException&quot;&gt;Thrown when the signature of the token cannot be validated with the given secret.&lt;/exception&gt;</pre></function>
* <function><a id="isjwt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsJwt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> token) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines if the provided string is a valid JWT (JSON Web Token).
&lt;/summary&gt;
&lt;param name=&quot;token&quot;&gt;The token to be validated as a JWT.&lt;/param&gt;
&lt;returns&gt;True if the token is a valid JWT; otherwise, false.&lt;/returns&gt;</pre></function>
## JSON Web Token (JWT)
* <function><a id="encodejwt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EncodeJwt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> claims, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> secret) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Encodes a JSON Web Token (JWT) using the specified claims and secret key.
The token is composed of three parts: header, payload, and signature. 
The header specifies the algorithm (&quot;HS256&quot;) used for signing the JWT, 
while the payload contains the claims to be encoded in the JWT. 
Finally, the signature is generated using HMAC SHA\-256 with the secret key.
&lt;/summary&gt;
&lt;param name=&quot;claims&quot;&gt;A dictionary of claims to include in the JWT.&lt;/param&gt;
&lt;param name=&quot;secret&quot;&gt;The secret key used for signing the JWT.&lt;/param&gt;
&lt;returns&gt;A string representing the encoded JWT.&lt;/returns&gt;</pre></function>
* <function><a id="decodejwt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DecodeJwt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> token, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> secret = <span style="color:#D70000; margin-right:1px">null</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> includeMetadata = <span style="color:#5FAFAF; margin-right:1px">false</span>) -> <span style="color:#87AF00">IDictionary\<string, object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Decodes a JWT (JSON Web Token) and validates its HMAC\-SHA256 signature using an optional secret.
Throws exceptions for invalid tokens or signatures. Optionally includes token metadata in the output.
&lt;/summary&gt;
&lt;param name=&quot;token&quot;&gt;The JWT to decode.&lt;/param&gt;
&lt;param name=&quot;secret&quot;&gt;Optional secret key used to validate the signature (for HMAC\-SHA256).&lt;/param&gt;
&lt;param name=&quot;includeMetadata&quot;&gt;
Whether to include the JWT header and signature as metadata in the returned dictionary.
&lt;/param&gt;
&lt;returns&gt;A dictionary containing the decoded JWT payload, optionally including header and signature metadata.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when the token is empty or null.&lt;/exception&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown when the token does not have exactly three parts separated by dots.&lt;/exception&gt;
&lt;exception cref=&quot;NotSupportedException&quot;&gt;
Thrown when the algorithm specified in the JWT header is not HS256.
&lt;/exception&gt;
&lt;exception cref=&quot;CryptographicException&quot;&gt;Thrown when the signature of the token cannot be validated with the given secret.&lt;/exception&gt;</pre></function>
* <function><a id="isjwt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsJwt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> token) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines if the provided string is a valid JWT (JSON Web Token).
&lt;/summary&gt;
&lt;param name=&quot;token&quot;&gt;The token to be validated as a JWT.&lt;/param&gt;
&lt;returns&gt;True if the token is a valid JWT; otherwise, false.&lt;/returns&gt;</pre></function>
## <a id="large-language-model-llm" href="#index_large-language-model-llm">Large Language Model (LLM)</a>
* <function><a id="ailmstudio"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AI_LMStudio</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> prompt, <span style="color:#87AF00; margin-left:1px; margin-right:1px">LMStudioConfig</span> config) -> <span style="color:#87AF00">Task\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Asynchronously communicates with the LMStudio AI model to generate a chat completion response.
The function creates and sends a request using specified configurations, then returns the generated content as a string.
&lt;/summary&gt;
&lt;param name=&quot;prompt&quot;&gt;The user input prompt for the AI model.&lt;/param&gt;
&lt;param name=&quot;config&quot;&gt;
Configuration settings for the LMStudioClient, including endpoint URL, model type, maximum tokens,
and temperature. The configuration cannot be null.
&lt;/param&gt;
&lt;returns&gt;A task representing the asynchronous operation, which upon completion provides a string
containing the AI\-generated response based on the given prompt.&lt;/returns&gt;</pre></function>
* <function><a id="aiopenai"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AI_OpenAI</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> prompt, <span style="color:#87AF00; margin-left:1px; margin-right:1px">OpenAIConfig</span> config) -> <span style="color:#87AF00">Task\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Asynchronously interacts with OpenAI&apos;s API to generate a response based on the provided prompt.
Utilizes configuration settings for API key or endpoint, model specification,
and various other parameters such as maximum tokens and temperature for generation.
&lt;/summary&gt;
&lt;param name=&quot;prompt&quot;&gt;The user input string prompting the AI for a specific task.&lt;/param&gt;
&lt;param name=&quot;config&quot;&gt;Configuration object containing OpenAI API details like API key, model type,
endpoint URI, max tokens limit, and temperature settings.&lt;/param&gt;
&lt;returns&gt;A Task that represents the asynchronous operation, which upon completion yields
the generated response string from the AI based on the user prompt.&lt;/returns&gt;</pre></function>
## Large Language Model (LLM)
* <function><a id="ailmstudio"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AI_LMStudio</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> prompt, <span style="color:#87AF00; margin-left:1px; margin-right:1px">LMStudioConfig</span> config) -> <span style="color:#87AF00">Task\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Asynchronously communicates with the LMStudio AI model to generate a chat completion response.
The function creates and sends a request using specified configurations, then returns the generated content as a string.
&lt;/summary&gt;
&lt;param name=&quot;prompt&quot;&gt;The user input prompt for the AI model.&lt;/param&gt;
&lt;param name=&quot;config&quot;&gt;
Configuration settings for the LMStudioClient, including endpoint URL, model type, maximum tokens,
and temperature. The configuration cannot be null.
&lt;/param&gt;
&lt;returns&gt;A task representing the asynchronous operation, which upon completion provides a string
containing the AI\-generated response based on the given prompt.&lt;/returns&gt;</pre></function>
* <function><a id="aiopenai"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AI_OpenAI</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> prompt, <span style="color:#87AF00; margin-left:1px; margin-right:1px">OpenAIConfig</span> config) -> <span style="color:#87AF00">Task\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Asynchronously interacts with OpenAI&apos;s API to generate a response based on the provided prompt.
Utilizes configuration settings for API key or endpoint, model specification,
and various other parameters such as maximum tokens and temperature for generation.
&lt;/summary&gt;
&lt;param name=&quot;prompt&quot;&gt;The user input string prompting the AI for a specific task.&lt;/param&gt;
&lt;param name=&quot;config&quot;&gt;Configuration object containing OpenAI API details like API key, model type,
endpoint URI, max tokens limit, and temperature settings.&lt;/param&gt;
&lt;returns&gt;A Task that represents the asynchronous operation, which upon completion yields
the generated response string from the AI based on the user prompt.&lt;/returns&gt;</pre></function>
## <a id="lookup" href="#index_lookup">Lookup</a>
* <function><a id="lookup"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Lookup</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fullkey = <span style="color:#D70000; margin-right:1px">""</span>) -> <span style="color:#87AF00">object</span> -- (alias <span style="color:#D75F00">$</span>)</function>
* <function><a id="parent"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Parent</span>() -> <span style="color:#87AF00">string</span></function>
* <function><a id="self"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Self</span>() -> <span style="color:#87AF00">string</span></function>
## Lookup
* <function><a id="lookup"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Lookup</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fullkey = <span style="color:#D70000; margin-right:1px">""</span>) -> <span style="color:#87AF00">object</span> -- (alias <span style="color:#D75F00">$</span>)</function>
* <function><a id="parent"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Parent</span>() -> <span style="color:#87AF00">string</span></function>
* <function><a id="self"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Self</span>() -> <span style="color:#87AF00">string</span></function>
## <a id="math" href="#index_math">Math</a>
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
## <a id="multipurpose-internet-mail-extensions-mime" href="#index_multipurpose-internet-mail-extensions-mime">Multipurpose Internet Mail Extensions (MIME)</a>
* <function><a id="getmimefromextension"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetMimeFromExtension</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> ext) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the MIME type associated with a given file extension.
&lt;/summary&gt;
&lt;param name=&quot;ext&quot;&gt;The file extension for which to retrieve the MIME type. Must not be null or whitespace.&lt;/param&gt;
&lt;returns&gt;A string representing the MIME type, or an empty string if the extension is null, whitespace, or has no associated MIME type.&lt;/returns&gt;</pre></function>
* <function><a id="getextensionfrommime"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetExtensionFromMime</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> mime) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the file extension associated with a given MIME type. If the MIME type is null, empty, or whitespace,
an empty string is returned. Otherwise, the method trims any leading or trailing whitespace from the input and 
attempts to find the first corresponding extension using the MimeTypes.GetMimeTypeExtensions method.
If no suitable extension is found, it defaults to &quot;.bin&quot;.
&lt;/summary&gt;
&lt;param name=&quot;mime&quot;&gt;The MIME type for which to retrieve the file extension.&lt;/param&gt;
&lt;returns&gt;A string representing the associated file extension or &quot;.bin&quot; if none are found; an empty string
if the input MIME type is null, empty, or only whitespace.&lt;/returns&gt;</pre></function>
## Multipurpose Internet Mail Extensions (MIME)
* <function><a id="getmimefromextension"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetMimeFromExtension</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> ext) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the MIME type associated with a given file extension.
&lt;/summary&gt;
&lt;param name=&quot;ext&quot;&gt;The file extension for which to retrieve the MIME type. Must not be null or whitespace.&lt;/param&gt;
&lt;returns&gt;A string representing the MIME type, or an empty string if the extension is null, whitespace, or has no associated MIME type.&lt;/returns&gt;</pre></function>
* <function><a id="getextensionfrommime"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetExtensionFromMime</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> mime) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the file extension associated with a given MIME type. If the MIME type is null, empty, or whitespace,
an empty string is returned. Otherwise, the method trims any leading or trailing whitespace from the input and 
attempts to find the first corresponding extension using the MimeTypes.GetMimeTypeExtensions method.
If no suitable extension is found, it defaults to &quot;.bin&quot;.
&lt;/summary&gt;
&lt;param name=&quot;mime&quot;&gt;The MIME type for which to retrieve the file extension.&lt;/param&gt;
&lt;returns&gt;A string representing the associated file extension or &quot;.bin&quot; if none are found; an empty string
if the input MIME type is null, empty, or only whitespace.&lt;/returns&gt;</pre></function>
## <a id="networking" href="#index_networking">Networking</a>
* <function><a id="istcpportopen"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsTcpPortOpen</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> hostName, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> port, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> timeoutMs = <span style="color:#5FAFAF; margin-right:1px">5000</span>) -> <span style="color:#87AF00">Task\<bool\></span></function>
* <function><a id="whois"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Whois</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> ip) -> <span style="color:#87AF00">Task\<WhoisResponseScoped\></span></function>
* <function><a id="isvpn"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsVPN</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> ip) -> <span style="color:#87AF00">Task\<bool\></span></function>
## Networking
* <function><a id="istcpportopen"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsTcpPortOpen</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> hostName, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> port, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> timeoutMs = <span style="color:#5FAFAF; margin-right:1px">5000</span>) -> <span style="color:#87AF00">Task\<bool\></span></function>
* <function><a id="whois"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Whois</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> ip) -> <span style="color:#87AF00">Task\<WhoisResponseScoped\></span></function>
* <function><a id="isvpn"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsVPN</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> ip) -> <span style="color:#87AF00">Task\<bool\></span></function>
## <a id="one-time-password-otp" href="#index_one-time-password-otp">One-Time Password (OTP)</a>
* <function><a id="generatetotp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateTOTP</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset?</span> at = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a Time\-based One\-Time Password (TOTP) based on the provided secret key.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The base32 encoded secret key used to generate the TOTP.&lt;/param&gt;
&lt;param name=&quot;at&quot;&gt;
An optional DateTimeOffset representing the time for which the TOTP is calculated. 
If not specified, the current UTC time is used.
&lt;/param&gt;
&lt;returns&gt;A string representation of the 6\-digit TOTP code generated from the provided key and time.&lt;/returns&gt;</pre></function>
* <function><a id="verifytotp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">VerifyTOTP</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> window = <span style="color:#5FAFAF; margin-right:1px">0</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Verifies a Time\-based One\-Time Password (TOTP) against the provided key and time window.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The base32\-encoded secret key used to generate TOTP.&lt;/param&gt;
&lt;param name=&quot;code&quot;&gt;The TOTP code to be verified.&lt;/param&gt;
&lt;param name=&quot;window&quot;&gt;The number of past and future intervals (default is 0) to check for validity, where each interval is 30 seconds.&lt;/param&gt;
&lt;returns&gt;True if the provided code matches a valid TOTP generated within the specified time window; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="remainingtotpseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RemainingTOTPSeconds</span>() -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the remaining time in seconds until the next Time\-based One\-Time Password (TOTP) changes.
TOTPs are typically refreshed every 30 seconds, and this function computes how many seconds 
remain before the next refresh. This can be useful for applications requiring synchronization
or timing\-related operations based on TOTP intervals.
&lt;/summary&gt;
&lt;returns&gt;
An integer representing the number of seconds remaining until the next TOTP change.
The return value will be an integer between 0 and 29, inclusive.
&lt;/returns&gt;</pre></function>
## One-Time Password (OTP)
* <function><a id="generatetotp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateTOTP</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset?</span> at = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a Time\-based One\-Time Password (TOTP) based on the provided secret key.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The base32 encoded secret key used to generate the TOTP.&lt;/param&gt;
&lt;param name=&quot;at&quot;&gt;
An optional DateTimeOffset representing the time for which the TOTP is calculated. 
If not specified, the current UTC time is used.
&lt;/param&gt;
&lt;returns&gt;A string representation of the 6\-digit TOTP code generated from the provided key and time.&lt;/returns&gt;</pre></function>
* <function><a id="verifytotp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">VerifyTOTP</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> window = <span style="color:#5FAFAF; margin-right:1px">0</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Verifies a Time\-based One\-Time Password (TOTP) against the provided key and time window.
&lt;/summary&gt;
&lt;param name=&quot;key&quot;&gt;The base32\-encoded secret key used to generate TOTP.&lt;/param&gt;
&lt;param name=&quot;code&quot;&gt;The TOTP code to be verified.&lt;/param&gt;
&lt;param name=&quot;window&quot;&gt;The number of past and future intervals (default is 0) to check for validity, where each interval is 30 seconds.&lt;/param&gt;
&lt;returns&gt;True if the provided code matches a valid TOTP generated within the specified time window; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="remainingtotpseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RemainingTOTPSeconds</span>() -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the remaining time in seconds until the next Time\-based One\-Time Password (TOTP) changes.
TOTPs are typically refreshed every 30 seconds, and this function computes how many seconds 
remain before the next refresh. This can be useful for applications requiring synchronization
or timing\-related operations based on TOTP intervals.
&lt;/summary&gt;
&lt;returns&gt;
An integer representing the number of seconds remaining until the next TOTP change.
The return value will be an integer between 0 and 29, inclusive.
&lt;/returns&gt;</pre></function>
## <a id="parsing" href="#index_parsing">Parsing</a>
* <function><a id="parsebool"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseBool</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Attempts to parse the provided string as a boolean value.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a boolean value.&lt;/param&gt;
&lt;returns&gt;A boolean value that represents the parsed result from the input text.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string cannot be parsed into a boolean value.
The exception message includes the invalid input string for clarity.
&lt;/exception&gt;</pre></function>
* <function><a id="parsesbyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseSByte</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">sbyte</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the given string into an sbyte value. Throws a FormatException if parsing fails.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a number to parse.&lt;/param&gt;
&lt;returns&gt;The parsed sbyte value.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input cannot be converted to an sbyte, indicating that
the format is invalid for parsing into the specified range.
&lt;/exception&gt;</pre></function>
* <function><a id="parsebyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseByte</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">byte</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the specified string into a byte using invariant culture and integer number styles.
If parsing fails, a &lt;see cref=&quot;FormatException&quot;/&gt; is thrown.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The input string to parse.&lt;/param&gt;
&lt;returns&gt;The parsed byte value.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the format of the string is invalid or if it does not represent a valid byte value.
&lt;/exception&gt;</pre></function>
* <function><a id="parseint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseInt16</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">short</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the specified text into a 16\-bit signed integer (Int16).
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of the number to parse.&lt;/param&gt;
&lt;returns&gt;A short value parsed from the input text.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input cannot be parsed as Int16, indicating that
the format is not valid for an Int16 within the range of 
{short.MinValue}..{short.MaxValue}.
&lt;/exception&gt;</pre></function>
* <function><a id="parseuint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUInt16</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">ushort</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the given string representation of a number into an unsigned 16\-bit integer (UInt16).
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string that contains the number to be parsed.&lt;/param&gt;
&lt;returns&gt;The UInt16 value that results from parsing the specified string.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the format of the string is invalid or if it falls outside
the range of a UInt16 (0..65535).
&lt;/exception&gt;</pre></function>
* <function><a id="parseint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseInt32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a string into an integer (Int32) using invariant culture formatting. 
Throws a FormatException if the parsing is unsuccessful.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The text to parse as an Int32.&lt;/param&gt;
&lt;returns&gt;The parsed integer value.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string cannot be parsed into a valid Int32.
&lt;/exception&gt;</pre></function>
* <function><a id="parseuint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUInt32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">uint</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a string into an unsigned 32\-bit integer.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of the number to be parsed.&lt;/param&gt;
&lt;returns&gt;The parsed unsigned 32\-bit integer value.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string cannot be converted to a valid UInt32 value within the range of uint.MinValue and uint.MaxValue.
&lt;/exception&gt;</pre></function>
* <function><a id="parseint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseInt64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">long</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Attempts to parse the provided string into a 64\-bit integer (Int64). If parsing fails, it throws a FormatException.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a number to be parsed.&lt;/param&gt;
&lt;returns&gt;The successfully parsed long value if the conversion succeeds.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown when the input string cannot be parsed as an Int64.&lt;/exception&gt;</pre></function>
* <function><a id="parseuint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUInt64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the specified string representation of a number into its equivalent unsigned 64\-bit integer (ulong).
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;A string containing the number to convert.&lt;/param&gt;
&lt;returns&gt;The parsed unsigned 64\-bit integer value.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string does not represent a valid unsigned 64\-bit integer.
The exception message includes the text that could not be parsed and the range of valid values for an unsigned 64\-bit integer.
&lt;/exception&gt;</pre></function>
* <function><a id="parsefloat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseFloat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">float</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Attempts to parse the specified string into a single\-precision floating\-point number.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a number to parse.&lt;/param&gt;
&lt;returns&gt;A float value parsed from the given text if successful.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the parsing operation fails, indicating that the input string does not represent a valid single\-precision floating\-point number.
&lt;/exception&gt;</pre></function>
* <function><a id="parsedouble"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseDouble</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a string representation of a number into a double value.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string to be parsed.&lt;/param&gt;
&lt;returns&gt;The parsed double value if successful.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown when the input string cannot be parsed as a valid double.&lt;/exception&gt;</pre></function>
* <function><a id="parsedecimal"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseDecimal</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">decimal</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Attempts to parse a string into a decimal number using invariant culture and specific number styles.
If parsing is unsuccessful, it throws a FormatException with a message indicating the failure.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a decimal number to be parsed.&lt;/param&gt;
&lt;returns&gt;The parsed decimal value if successful.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string cannot be converted to a decimal using the specified parsing settings.
The exception message includes the input text that failed to parse.
&lt;/exception&gt;</pre></function>
* <function><a id="parsetimespan"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseTimeSpan</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">TimeSpan</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the specified string and converts it into a &lt;see cref=&quot;TimeSpan&quot;/&gt; object using invariant culture settings.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of time duration to parse.&lt;/param&gt;
&lt;returns&gt;A &lt;see cref=&quot;TimeSpan&quot;/&gt; representing the parsed time duration.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the format of the specified string is invalid or it does not represent a valid &lt;see cref=&quot;TimeSpan&quot;/&gt;.
&lt;/exception&gt;</pre></function>
* <function><a id="parsedatetimeoffset"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseDateTimeOffset</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a string into a DateTimeOffset object using the specified culture (InvariantCulture).
Throws a FormatException if parsing fails.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of the date and time offset.&lt;/param&gt;
&lt;returns&gt;A DateTimeOffset object parsed from the input string.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown when the input string cannot be parsed as a DateTimeOffset.&lt;/exception&gt;</pre></function>
* <function><a id="parseipaddress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseIPAddress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">IPAddress</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a string representation of an IP address into an IPAddress object.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string containing the IP address.&lt;/param&gt;
&lt;returns&gt;An IPAddress object representing the parsed IP address.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input text cannot be parsed as a valid IP address.
The exception message will specify the input string that failed to parse.
&lt;/exception&gt;</pre></function>
* <function><a id="parseguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseGuid</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Attempts to parse the specified string into a GUID (Globally Unique Identifier).
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a GUID to be parsed.&lt;/param&gt;
&lt;returns&gt;A GUID that matches the text if parsing succeeds.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string does not represent a valid GUID.
&lt;/exception&gt;</pre></function>
* <function><a id="parsesemver"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseSemVer</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> version) -> <span style="color:#87AF00">SemVer</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a given string into a Semantic Version (SemVer) object.
This method uses a regular expression to validate and extract version components: major, minor, and patch.
&lt;/summary&gt;
&lt;param name=&quot;version&quot;&gt;The semantic version string to be parsed.&lt;/param&gt;
&lt;returns&gt;A SemVer object containing the major, minor, and patch numbers extracted from the input string.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the provided version string does not match the semantic version format,
or if any of the numeric components (major, minor, patch) cannot be parsed as integers.
&lt;/exception&gt;</pre></function>
## Parsing
* <function><a id="parsebool"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseBool</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Attempts to parse the provided string as a boolean value.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a boolean value.&lt;/param&gt;
&lt;returns&gt;A boolean value that represents the parsed result from the input text.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string cannot be parsed into a boolean value.
The exception message includes the invalid input string for clarity.
&lt;/exception&gt;</pre></function>
* <function><a id="parsesbyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseSByte</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">sbyte</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the given string into an sbyte value. Throws a FormatException if parsing fails.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a number to parse.&lt;/param&gt;
&lt;returns&gt;The parsed sbyte value.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input cannot be converted to an sbyte, indicating that
the format is invalid for parsing into the specified range.
&lt;/exception&gt;</pre></function>
* <function><a id="parsebyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseByte</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">byte</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the specified string into a byte using invariant culture and integer number styles.
If parsing fails, a &lt;see cref=&quot;FormatException&quot;/&gt; is thrown.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The input string to parse.&lt;/param&gt;
&lt;returns&gt;The parsed byte value.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the format of the string is invalid or if it does not represent a valid byte value.
&lt;/exception&gt;</pre></function>
* <function><a id="parseint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseInt16</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">short</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the specified text into a 16\-bit signed integer (Int16).
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of the number to parse.&lt;/param&gt;
&lt;returns&gt;A short value parsed from the input text.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input cannot be parsed as Int16, indicating that
the format is not valid for an Int16 within the range of 
{short.MinValue}..{short.MaxValue}.
&lt;/exception&gt;</pre></function>
* <function><a id="parseuint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUInt16</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">ushort</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the given string representation of a number into an unsigned 16\-bit integer (UInt16).
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string that contains the number to be parsed.&lt;/param&gt;
&lt;returns&gt;The UInt16 value that results from parsing the specified string.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the format of the string is invalid or if it falls outside
the range of a UInt16 (0..65535).
&lt;/exception&gt;</pre></function>
* <function><a id="parseint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseInt32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a string into an integer (Int32) using invariant culture formatting. 
Throws a FormatException if the parsing is unsuccessful.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The text to parse as an Int32.&lt;/param&gt;
&lt;returns&gt;The parsed integer value.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string cannot be parsed into a valid Int32.
&lt;/exception&gt;</pre></function>
* <function><a id="parseuint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUInt32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">uint</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a string into an unsigned 32\-bit integer.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of the number to be parsed.&lt;/param&gt;
&lt;returns&gt;The parsed unsigned 32\-bit integer value.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string cannot be converted to a valid UInt32 value within the range of uint.MinValue and uint.MaxValue.
&lt;/exception&gt;</pre></function>
* <function><a id="parseint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseInt64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">long</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Attempts to parse the provided string into a 64\-bit integer (Int64). If parsing fails, it throws a FormatException.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a number to be parsed.&lt;/param&gt;
&lt;returns&gt;The successfully parsed long value if the conversion succeeds.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown when the input string cannot be parsed as an Int64.&lt;/exception&gt;</pre></function>
* <function><a id="parseuint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUInt64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the specified string representation of a number into its equivalent unsigned 64\-bit integer (ulong).
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;A string containing the number to convert.&lt;/param&gt;
&lt;returns&gt;The parsed unsigned 64\-bit integer value.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string does not represent a valid unsigned 64\-bit integer.
The exception message includes the text that could not be parsed and the range of valid values for an unsigned 64\-bit integer.
&lt;/exception&gt;</pre></function>
* <function><a id="parsefloat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseFloat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">float</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Attempts to parse the specified string into a single\-precision floating\-point number.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a number to parse.&lt;/param&gt;
&lt;returns&gt;A float value parsed from the given text if successful.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the parsing operation fails, indicating that the input string does not represent a valid single\-precision floating\-point number.
&lt;/exception&gt;</pre></function>
* <function><a id="parsedouble"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseDouble</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a string representation of a number into a double value.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string to be parsed.&lt;/param&gt;
&lt;returns&gt;The parsed double value if successful.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown when the input string cannot be parsed as a valid double.&lt;/exception&gt;</pre></function>
* <function><a id="parsedecimal"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseDecimal</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">decimal</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Attempts to parse a string into a decimal number using invariant culture and specific number styles.
If parsing is unsuccessful, it throws a FormatException with a message indicating the failure.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a decimal number to be parsed.&lt;/param&gt;
&lt;returns&gt;The parsed decimal value if successful.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string cannot be converted to a decimal using the specified parsing settings.
The exception message includes the input text that failed to parse.
&lt;/exception&gt;</pre></function>
* <function><a id="parsetimespan"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseTimeSpan</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">TimeSpan</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the specified string and converts it into a &lt;see cref=&quot;TimeSpan&quot;/&gt; object using invariant culture settings.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of time duration to parse.&lt;/param&gt;
&lt;returns&gt;A &lt;see cref=&quot;TimeSpan&quot;/&gt; representing the parsed time duration.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the format of the specified string is invalid or it does not represent a valid &lt;see cref=&quot;TimeSpan&quot;/&gt;.
&lt;/exception&gt;</pre></function>
* <function><a id="parsedatetimeoffset"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseDateTimeOffset</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a string into a DateTimeOffset object using the specified culture (InvariantCulture).
Throws a FormatException if parsing fails.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of the date and time offset.&lt;/param&gt;
&lt;returns&gt;A DateTimeOffset object parsed from the input string.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown when the input string cannot be parsed as a DateTimeOffset.&lt;/exception&gt;</pre></function>
* <function><a id="parseipaddress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseIPAddress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">IPAddress</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a string representation of an IP address into an IPAddress object.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string containing the IP address.&lt;/param&gt;
&lt;returns&gt;An IPAddress object representing the parsed IP address.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input text cannot be parsed as a valid IP address.
The exception message will specify the input string that failed to parse.
&lt;/exception&gt;</pre></function>
* <function><a id="parseguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseGuid</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Attempts to parse the specified string into a GUID (Globally Unique Identifier).
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string representation of a GUID to be parsed.&lt;/param&gt;
&lt;returns&gt;A GUID that matches the text if parsing succeeds.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the input string does not represent a valid GUID.
&lt;/exception&gt;</pre></function>
* <function><a id="parsesemver"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseSemVer</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> version) -> <span style="color:#87AF00">SemVer</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a given string into a Semantic Version (SemVer) object.
This method uses a regular expression to validate and extract version components: major, minor, and patch.
&lt;/summary&gt;
&lt;param name=&quot;version&quot;&gt;The semantic version string to be parsed.&lt;/param&gt;
&lt;returns&gt;A SemVer object containing the major, minor, and patch numbers extracted from the input string.&lt;/returns&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;
Thrown when the provided version string does not match the semantic version format,
or if any of the numeric components (major, minor, patch) cannot be parsed as integers.
&lt;/exception&gt;</pre></function>
## <a id="password" href="#index_password">Password</a>
* <function><a id="hashpassword"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HashPassword</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> iterations = <span style="color:#5FAFAF; margin-right:1px">150000</span>, <span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset?</span> expiresAt = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Hashes the provided password using PBKDF2 with a random salt and specified number of iterations.
Optionally sets an expiration time for the hash.
&lt;/summary&gt;
&lt;param name=&quot;password&quot;&gt;The password to be hashed.&lt;/param&gt;
&lt;param name=&quot;iterations&quot;&gt;The number of iterations for the key derivation function. Defaults to Iterations constant if not provided.&lt;/param&gt;
&lt;param name=&quot;expiresAt&quot;&gt;An optional DateTimeOffset representing when the hash expires. If null, sets it to NoExpiration.&lt;/param&gt;
&lt;returns&gt;A formatted string containing the iteration count, expiration time (or default), salt, and hashed key.&lt;/returns&gt;</pre></function>
* <function><a id="verifypassword"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">VerifyPassword</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> hash, <span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset?</span> now = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Verifies whether a given password matches the provided hash and optionally checks for expiration.
&lt;/summary&gt;
&lt;param name=&quot;password&quot;&gt;The plain text password to verify.&lt;/param&gt;
&lt;param name=&quot;hash&quot;&gt;The hashed string containing iterations, expiration time, salt, and expected hash.&lt;/param&gt;
&lt;param name=&quot;now&quot;&gt;Optional parameter representing the current date and time. Defaults to current UTC time if not provided.&lt;/param&gt;
&lt;returns&gt;True if the password matches the hash and is within the valid expiration period; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="passwordentropybits"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PasswordEntropyBits</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the entropy in bits of a given password based on its character set diversity and length.
&lt;/summary&gt;
&lt;param name=&quot;password&quot;&gt;The input password whose entropy is to be calculated.&lt;/param&gt;
&lt;returns&gt;The entropy value in bits, representing the unpredictability or randomness of the password.&lt;/returns&gt;</pre></function>
* <function><a id="isstrongpassword"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsStrongPassword</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> minEntropyBits = <span style="color:#5FAFAF; margin-right:1px">80</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified password meets the minimum entropy requirement.
&lt;/summary&gt;
&lt;param name=&quot;password&quot;&gt;The password to evaluate.&lt;/param&gt;
&lt;param name=&quot;minEntropyBits&quot;&gt;
The minimum number of bits of entropy required for a strong password. 
Default is 80 bits.
&lt;/param&gt;
&lt;returns&gt;True if the password&apos;s entropy meets or exceeds the specified threshold; otherwise, false.&lt;/returns&gt;</pre></function>
## Password
* <function><a id="hashpassword"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HashPassword</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> iterations = <span style="color:#5FAFAF; margin-right:1px">150000</span>, <span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset?</span> expiresAt = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Hashes the provided password using PBKDF2 with a random salt and specified number of iterations.
Optionally sets an expiration time for the hash.
&lt;/summary&gt;
&lt;param name=&quot;password&quot;&gt;The password to be hashed.&lt;/param&gt;
&lt;param name=&quot;iterations&quot;&gt;The number of iterations for the key derivation function. Defaults to Iterations constant if not provided.&lt;/param&gt;
&lt;param name=&quot;expiresAt&quot;&gt;An optional DateTimeOffset representing when the hash expires. If null, sets it to NoExpiration.&lt;/param&gt;
&lt;returns&gt;A formatted string containing the iteration count, expiration time (or default), salt, and hashed key.&lt;/returns&gt;</pre></function>
* <function><a id="verifypassword"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">VerifyPassword</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> hash, <span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset?</span> now = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Verifies whether a given password matches the provided hash and optionally checks for expiration.
&lt;/summary&gt;
&lt;param name=&quot;password&quot;&gt;The plain text password to verify.&lt;/param&gt;
&lt;param name=&quot;hash&quot;&gt;The hashed string containing iterations, expiration time, salt, and expected hash.&lt;/param&gt;
&lt;param name=&quot;now&quot;&gt;Optional parameter representing the current date and time. Defaults to current UTC time if not provided.&lt;/param&gt;
&lt;returns&gt;True if the password matches the hash and is within the valid expiration period; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="passwordentropybits"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PasswordEntropyBits</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Calculates the entropy in bits of a given password based on its character set diversity and length.
&lt;/summary&gt;
&lt;param name=&quot;password&quot;&gt;The input password whose entropy is to be calculated.&lt;/param&gt;
&lt;returns&gt;The entropy value in bits, representing the unpredictability or randomness of the password.&lt;/returns&gt;</pre></function>
* <function><a id="isstrongpassword"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsStrongPassword</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> minEntropyBits = <span style="color:#5FAFAF; margin-right:1px">80</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified password meets the minimum entropy requirement.
&lt;/summary&gt;
&lt;param name=&quot;password&quot;&gt;The password to evaluate.&lt;/param&gt;
&lt;param name=&quot;minEntropyBits&quot;&gt;
The minimum number of bits of entropy required for a strong password. 
Default is 80 bits.
&lt;/param&gt;
&lt;returns&gt;True if the password&apos;s entropy meets or exceeds the specified threshold; otherwise, false.&lt;/returns&gt;</pre></function>
## <a id="path" href="#index_path">Path</a>
* <function><a id="pathcombine"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathCombine</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">param string[]</span> parts) -> <span style="color:#87AF00">string</span></function>
* <function><a id="pathchild"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathChild</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> path) -> <span style="color:#87AF00">string</span></function>
* <function><a id="pathparent"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathParent</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> path) -> <span style="color:#87AF00">string</span></function>
* <function><a id="pathparts"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathParts</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> path) -> <span style="color:#87AF00">string[]</span></function>
* <function><a id="pathid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathId</span>() -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">Id</span>)</function>
* <function><a id="pathdepth"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathDepth</span>() -> <span style="color:#5FAFAF">int</span></function>
## Path
* <function><a id="pathcombine"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathCombine</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">param string[]</span> parts) -> <span style="color:#87AF00">string</span></function>
* <function><a id="pathchild"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathChild</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> path) -> <span style="color:#87AF00">string</span></function>
* <function><a id="pathparent"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathParent</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> path) -> <span style="color:#87AF00">string</span></function>
* <function><a id="pathparts"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathParts</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> path) -> <span style="color:#87AF00">string[]</span></function>
* <function><a id="pathid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathId</span>() -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">Id</span>)</function>
* <function><a id="pathdepth"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathDepth</span>() -> <span style="color:#5FAFAF">int</span></function>
## <a id="print" href="#index_print">Print</a>
* <function><a id="print"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Print</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message) -> <span style="color:#87AF00">void</span> -- (alias <span style="color:#D75F00">Echo</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Prints the specified message to both the console and debug output.
&lt;/summary&gt;
&lt;param name=&quot;message&quot;&gt;The message to print.&lt;/param&gt;</pre></function>
## Print
* <function><a id="print"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Print</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message) -> <span style="color:#87AF00">void</span> -- (alias <span style="color:#D75F00">Echo</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Prints the specified message to both the console and debug output.
&lt;/summary&gt;
&lt;param name=&quot;message&quot;&gt;The message to print.&lt;/param&gt;</pre></function>
## <a id="random" href="#index_random">Random</a>
* <function><a id="randombool"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomBool</span>() -> <span style="color:#5FAFAF">bool</span></function>
* <function><a id="randomint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomInt64</span>() -> <span style="color:#5FAFAF">long</span></function>
* <function><a id="randomuint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomUInt64</span>() -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a random unsigned 64\-bit integer using the underlying random number generator.
This function is marked as a plugin function and can be used to obtain random values for various purposes.
&lt;/summary&gt;
&lt;returns&gt;A randomly generated 64\-bit unsigned integer.&lt;/returns&gt;</pre></function>
* <function><a id="randomint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomInt32</span>() -> <span style="color:#5FAFAF">int</span></function>
* <function><a id="randomuint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomUInt32</span>() -> <span style="color:#5FAFAF">uint</span></function>
* <function><a id="randomint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomInt16</span>() -> <span style="color:#5FAFAF">short</span></function>
* <function><a id="randomuint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomUInt16</span>() -> <span style="color:#5FAFAF">ushort</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates and returns a random 16\-bit unsigned integer.
&lt;/summary&gt;
&lt;returns&gt;A random ushort value.&lt;/returns&gt;</pre></function>
* <function><a id="randomsbyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomSByte</span>() -> <span style="color:#5FAFAF">sbyte</span></function>
* <function><a id="randombyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomByte</span>() -> <span style="color:#5FAFAF">byte</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a random byte using the underlying random number generator.
&lt;/summary&gt;</pre></function>
* <function><a id="randomfloat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomFloat</span>() -> <span style="color:#5FAFAF">float</span></function>
* <function><a id="randomdouble"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomDouble</span>() -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates and returns a random double value using the underlying random number generator.
&lt;/summary&gt;
&lt;returns&gt;A randomly generated double value.&lt;/returns&gt;</pre></function>
* <function><a id="randomdecimal"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomDecimal</span>() -> <span style="color:#87AF00">decimal</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a random decimal number using a predefined random number generator.
&lt;/summary&gt;
&lt;returns&gt;A randomly generated decimal value. The characteristics of the randomness depend on the implementation within rng.Decimal().&lt;/returns&gt;</pre></function>
* <function><a id="randomstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomString</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a random string of the specified length using a predefined random number generator.
&lt;/summary&gt;
&lt;param name=&quot;length&quot;&gt;The desired length of the generated random string.&lt;/param&gt;
&lt;returns&gt;A randomly generated string with the given length. The content and characteristics of the randomness depend on the implementation within rng.String(length).&lt;/returns&gt;</pre></function>
* <function><a id="randombytes"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomBytes</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> count) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates an array of random bytes with the specified length.
&lt;/summary&gt;
&lt;param name=&quot;count&quot;&gt;The number of random bytes to generate.&lt;/param&gt;
&lt;returns&gt;An array containing &apos;count&apos; randomly generated bytes.&lt;/returns&gt;</pre></function>
* <function><a id="randomdatetime"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomDateTime</span>() -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates and returns a random &lt;see cref=&quot;DateTimeOffset&quot;/&gt; with the current date and 
time offset set to zero. The function utilizes a pseudo\-random number generator 
to produce a random long value representing seconds since Unix epoch (1970\-01\-01T00:00:00Z).
This ensures that the returned DateTimeOffset is within plausible historical bounds.
&lt;/summary&gt;
&lt;returns&gt;A random &lt;see cref=&quot;DateTimeOffset&quot;/&gt; with an offset of zero.&lt;/returns&gt;</pre></function>
## Random
* <function><a id="randombool"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomBool</span>() -> <span style="color:#5FAFAF">bool</span></function>
* <function><a id="randomint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomInt64</span>() -> <span style="color:#5FAFAF">long</span></function>
* <function><a id="randomuint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomUInt64</span>() -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a random unsigned 64\-bit integer using the underlying random number generator.
This function is marked as a plugin function and can be used to obtain random values for various purposes.
&lt;/summary&gt;
&lt;returns&gt;A randomly generated 64\-bit unsigned integer.&lt;/returns&gt;</pre></function>
* <function><a id="randomint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomInt32</span>() -> <span style="color:#5FAFAF">int</span></function>
* <function><a id="randomuint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomUInt32</span>() -> <span style="color:#5FAFAF">uint</span></function>
* <function><a id="randomint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomInt16</span>() -> <span style="color:#5FAFAF">short</span></function>
* <function><a id="randomuint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomUInt16</span>() -> <span style="color:#5FAFAF">ushort</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates and returns a random 16\-bit unsigned integer.
&lt;/summary&gt;
&lt;returns&gt;A random ushort value.&lt;/returns&gt;</pre></function>
* <function><a id="randomsbyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomSByte</span>() -> <span style="color:#5FAFAF">sbyte</span></function>
* <function><a id="randombyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomByte</span>() -> <span style="color:#5FAFAF">byte</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a random byte using the underlying random number generator.
&lt;/summary&gt;</pre></function>
* <function><a id="randomfloat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomFloat</span>() -> <span style="color:#5FAFAF">float</span></function>
* <function><a id="randomdouble"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomDouble</span>() -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates and returns a random double value using the underlying random number generator.
&lt;/summary&gt;
&lt;returns&gt;A randomly generated double value.&lt;/returns&gt;</pre></function>
* <function><a id="randomdecimal"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomDecimal</span>() -> <span style="color:#87AF00">decimal</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a random decimal number using a predefined random number generator.
&lt;/summary&gt;
&lt;returns&gt;A randomly generated decimal value. The characteristics of the randomness depend on the implementation within rng.Decimal().&lt;/returns&gt;</pre></function>
* <function><a id="randomstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomString</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a random string of the specified length using a predefined random number generator.
&lt;/summary&gt;
&lt;param name=&quot;length&quot;&gt;The desired length of the generated random string.&lt;/param&gt;
&lt;returns&gt;A randomly generated string with the given length. The content and characteristics of the randomness depend on the implementation within rng.String(length).&lt;/returns&gt;</pre></function>
* <function><a id="randombytes"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomBytes</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> count) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates an array of random bytes with the specified length.
&lt;/summary&gt;
&lt;param name=&quot;count&quot;&gt;The number of random bytes to generate.&lt;/param&gt;
&lt;returns&gt;An array containing &apos;count&apos; randomly generated bytes.&lt;/returns&gt;</pre></function>
* <function><a id="randomdatetime"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomDateTime</span>() -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates and returns a random &lt;see cref=&quot;DateTimeOffset&quot;/&gt; with the current date and 
time offset set to zero. The function utilizes a pseudo\-random number generator 
to produce a random long value representing seconds since Unix epoch (1970\-01\-01T00:00:00Z).
This ensures that the returned DateTimeOffset is within plausible historical bounds.
&lt;/summary&gt;
&lt;returns&gt;A random &lt;see cref=&quot;DateTimeOffset&quot;/&gt; with an offset of zero.&lt;/returns&gt;</pre></function>
## <a id="really-simple-syndication-rss" href="#index_really-simple-syndication-rss">Really Simple Syndication (RSS)</a>
* <function><a id="fetchrss"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FetchRSS</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> url) -> <span style="color:#87AF00">Task\<Feed\></span></function>
## Really Simple Syndication (RSS)
* <function><a id="fetchrss"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FetchRSS</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> url) -> <span style="color:#87AF00">Task\<Feed\></span></function>
## <a id="regex" href="#index_regex">Regex</a>
* <function><a id="regexismatch"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RegexIsMatch</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> pattern, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines if the specified input string matches a given regular expression pattern.
&lt;/summary&gt;
&lt;param name=&quot;pattern&quot;&gt;The regular expression pattern to match against.&lt;/param&gt;
&lt;param name=&quot;input&quot;&gt;The input string to test for a match.&lt;/param&gt;
&lt;returns&gt;True if the input string matches the pattern; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="regexmatch"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RegexMatch</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> pattern, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">Match</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Finds the first match for a regular expression within a given input string.
&lt;/summary&gt;
&lt;param name=&quot;pattern&quot;&gt;The regex pattern to be matched against the input string.&lt;/param&gt;
&lt;param name=&quot;input&quot;&gt;The input string in which to search for matches.&lt;/param&gt;
&lt;returns&gt;A Match object representing the first successful match of the pattern in the input, or an empty match if no patterns were found.&lt;/returns&gt;</pre></function>
* <function><a id="regexmatches"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RegexMatches</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> pattern, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">Match[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves an array of matches based on a regular expression pattern applied to the input string.
&lt;/summary&gt;
&lt;param name=&quot;pattern&quot;&gt;The regex pattern used for matching.&lt;/param&gt;
&lt;param name=&quot;input&quot;&gt;The input string where the search is performed.&lt;/param&gt;
&lt;returns&gt;An array containing all matches found in the input string according to the specified pattern.&lt;/returns&gt;</pre></function>
## Regex
* <function><a id="regexismatch"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RegexIsMatch</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> pattern, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines if the specified input string matches a given regular expression pattern.
&lt;/summary&gt;
&lt;param name=&quot;pattern&quot;&gt;The regular expression pattern to match against.&lt;/param&gt;
&lt;param name=&quot;input&quot;&gt;The input string to test for a match.&lt;/param&gt;
&lt;returns&gt;True if the input string matches the pattern; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="regexmatch"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RegexMatch</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> pattern, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">Match</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Finds the first match for a regular expression within a given input string.
&lt;/summary&gt;
&lt;param name=&quot;pattern&quot;&gt;The regex pattern to be matched against the input string.&lt;/param&gt;
&lt;param name=&quot;input&quot;&gt;The input string in which to search for matches.&lt;/param&gt;
&lt;returns&gt;A Match object representing the first successful match of the pattern in the input, or an empty match if no patterns were found.&lt;/returns&gt;</pre></function>
* <function><a id="regexmatches"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RegexMatches</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> pattern, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">Match[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves an array of matches based on a regular expression pattern applied to the input string.
&lt;/summary&gt;
&lt;param name=&quot;pattern&quot;&gt;The regex pattern used for matching.&lt;/param&gt;
&lt;param name=&quot;input&quot;&gt;The input string where the search is performed.&lt;/param&gt;
&lt;returns&gt;An array containing all matches found in the input string according to the specified pattern.&lt;/returns&gt;</pre></function>
## <a id="roman-numerals" href="#index_roman-numerals">Roman Numerals</a>
* <function><a id="toromannumeral"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToRomanNumeral</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> number) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts an integer to its corresponding Roman numeral representation.
This function does not support negative numbers and returns &quot;N&quot; for zero.
&lt;/summary&gt;
&lt;param name=&quot;number&quot;&gt;The integer value to convert.&lt;/param&gt;
&lt;returns&gt;A string representing the Roman numeral equivalent of the input number.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentOutOfRangeException&quot;&gt;
Thrown when a negative number is provided, as Roman numerals do not support negatives.
&lt;/exception&gt;</pre></function>
* <function><a id="fromromannumeral"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromRomanNumeral</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> roman) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a Roman numeral string to its corresponding integer value.
&lt;/summary&gt;
&lt;param name=&quot;roman&quot;&gt;The Roman numeral string to convert. The input should be in uppercase and 
can optionally contain whitespace which will be ignored.&lt;/param&gt;
&lt;returns&gt;The integer representation of the given Roman numeral.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when the input Roman numeral string is empty or contains only whitespace.&lt;/exception&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown when the input contains invalid characters that do not 
correspond to any Roman numeral symbols in SymbolMap.&lt;/exception&gt;</pre></function>
## Roman Numerals
* <function><a id="toromannumeral"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToRomanNumeral</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> number) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts an integer to its corresponding Roman numeral representation.
This function does not support negative numbers and returns &quot;N&quot; for zero.
&lt;/summary&gt;
&lt;param name=&quot;number&quot;&gt;The integer value to convert.&lt;/param&gt;
&lt;returns&gt;A string representing the Roman numeral equivalent of the input number.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentOutOfRangeException&quot;&gt;
Thrown when a negative number is provided, as Roman numerals do not support negatives.
&lt;/exception&gt;</pre></function>
* <function><a id="fromromannumeral"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromRomanNumeral</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> roman) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a Roman numeral string to its corresponding integer value.
&lt;/summary&gt;
&lt;param name=&quot;roman&quot;&gt;The Roman numeral string to convert. The input should be in uppercase and 
can optionally contain whitespace which will be ignored.&lt;/param&gt;
&lt;returns&gt;The integer representation of the given Roman numeral.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown when the input Roman numeral string is empty or contains only whitespace.&lt;/exception&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown when the input contains invalid characters that do not 
correspond to any Roman numeral symbols in SymbolMap.&lt;/exception&gt;</pre></function>
## <a id="secure-string" href="#index_secure-string">Secure String</a>
* <function><a id="tosecurestring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToSecureString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Encrypts the specified input string using AES encryption and returns a secure string.
The method throws an exception if the input is null. It performs AES encryption with 
a 256\-bit key size, CBC mode, and PKCS7 padding. An HMAC\-SHA256 is computed over the IV 
concatenated with the cipher text to ensure integrity, and the final payload includes the
IV, cipher text, and MAC. Sensitive data buffers are cleared after use.
&lt;/summary&gt;
&lt;remarks&gt;
Set custom secret via ENV &apos;SECURE\_SECRET&apos;
&lt;/remarks&gt;
&lt;param name=&quot;input&quot;&gt;The input string to be encrypted.&lt;/param&gt;
&lt;returns&gt;A Base64 encoded string representing the encrypted data including the IV, 
cipher text, and HMAC\-SHA256 MAC.&lt;/returns&gt;</pre></function>
* <function><a id="fromsecurestring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromSecureString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> encrypted) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a Base64 encoded string that represents an encrypted and HMAC\-protected payload into its plaintext form.
This method performs decryption using AES with CBC mode and verifies the integrity of the data using HMAC\-SHA256.
&lt;/summary&gt;
&lt;param name=&quot;encrypted&quot;&gt;The Base64 encoded string containing the encrypted data, initialization vector (IV), 
and message authentication code (MAC). The input must not be null.&lt;/param&gt;
&lt;returns&gt;A string representing the decrypted plaintext content.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;Thrown when the input parameter &apos;encrypted&apos; is null.&lt;/exception&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown if the payload format is invalid or does not meet expected length requirements.&lt;/exception&gt;
&lt;exception cref=&quot;CryptographicException&quot;&gt;Thrown when the MAC verification fails, indicating potential data tampering.&lt;/exception&gt;</pre></function>
## Secure String
* <function><a id="tosecurestring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToSecureString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Encrypts the specified input string using AES encryption and returns a secure string.
The method throws an exception if the input is null. It performs AES encryption with 
a 256\-bit key size, CBC mode, and PKCS7 padding. An HMAC\-SHA256 is computed over the IV 
concatenated with the cipher text to ensure integrity, and the final payload includes the
IV, cipher text, and MAC. Sensitive data buffers are cleared after use.
&lt;/summary&gt;
&lt;remarks&gt;
Set custom secret via ENV &apos;SECURE\_SECRET&apos;
&lt;/remarks&gt;
&lt;param name=&quot;input&quot;&gt;The input string to be encrypted.&lt;/param&gt;
&lt;returns&gt;A Base64 encoded string representing the encrypted data including the IV, 
cipher text, and HMAC\-SHA256 MAC.&lt;/returns&gt;</pre></function>
* <function><a id="fromsecurestring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromSecureString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> encrypted) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a Base64 encoded string that represents an encrypted and HMAC\-protected payload into its plaintext form.
This method performs decryption using AES with CBC mode and verifies the integrity of the data using HMAC\-SHA256.
&lt;/summary&gt;
&lt;param name=&quot;encrypted&quot;&gt;The Base64 encoded string containing the encrypted data, initialization vector (IV), 
and message authentication code (MAC). The input must not be null.&lt;/param&gt;
&lt;returns&gt;A string representing the decrypted plaintext content.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentNullException&quot;&gt;Thrown when the input parameter &apos;encrypted&apos; is null.&lt;/exception&gt;
&lt;exception cref=&quot;FormatException&quot;&gt;Thrown if the payload format is invalid or does not meet expected length requirements.&lt;/exception&gt;
&lt;exception cref=&quot;CryptographicException&quot;&gt;Thrown when the MAC verification fails, indicating potential data tampering.&lt;/exception&gt;</pre></function>
## <a id="string" href="#index_string">String</a>
* <function><a id="reverse"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Reverse</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Reverses the order of characters in a given input string using an efficient method.
This function leverages the Span&lt;T&gt; and String.Create to perform the reversal operation 
in place, minimizing allocations and enhancing performance.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string whose characters are to be reversed.&lt;/param&gt;
&lt;returns&gt;A new string with its characters in reverse order compared to the input.&lt;/returns&gt;</pre></function>
* <function><a id="repeatstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RepeatString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> times) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Repeats the given input string a specified number of times.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be repeated.&lt;/param&gt;
&lt;param name=&quot;times&quot;&gt;The number of times to repeat the string. Must be non\-negative.&lt;/param&gt;
&lt;returns&gt;A new string consisting of the input string repeated &apos;times&apos; times concatenated together. If &apos;times&apos; is zero, an empty string is returned.&lt;/returns&gt;</pre></function>
* <function><a id="truncate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Truncate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> suffix = <span style="color:#D70000; margin-right:1px">"…"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Truncates the given input string to a specified length and appends a suffix if truncation occurs.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The original string to be truncated.&lt;/param&gt;
&lt;param name=&quot;length&quot;&gt;The maximum allowed length for the output string. If the input is shorter, it&apos;s returned unchanged.&lt;/param&gt;
&lt;param name=&quot;suffix&quot;&gt;The string to append at the end if truncation occurs, defaulting to an ellipsis character (…).&lt;/param&gt;
&lt;returns&gt;The truncated string with suffix appended if necessary; otherwise, returns the original string.&lt;/returns&gt;</pre></function>
* <function><a id="countwords"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CountWords</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Counts the number of words in the provided input string using a regular expression pattern.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string from which to count the words.&lt;/param&gt;
&lt;returns&gt;The total number of words found in the input string.&lt;/returns&gt;</pre></function>
* <function><a id="randomstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomString</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> allowedChars = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a random string of the specified length using either provided allowed characters or a default character set.
&lt;/summary&gt;
&lt;param name=&quot;length&quot;&gt;The length of the random string to generate. Must be non\-negative.&lt;/param&gt;
&lt;param name=&quot;allowedChars&quot;&gt;An optional parameter specifying which characters can be used in the generated string. 
If null, a default set of alphanumeric characters is used.&lt;/param&gt;
&lt;returns&gt;A randomly generated string of specified length using allowed or default characters.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentOutOfRangeException&quot;&gt;
Thrown when the specified length is negative.
&lt;/exception&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;
Thrown when the character set (either provided or default) is empty.
&lt;/exception&gt;</pre></function>
* <function><a id="slugify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Slugify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> separator = <span style="color:#D70000; margin-right:1px">"-"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Transforms the input string into a URL\-friendly slug format.
Converts all characters to lowercase, replaces non\-alphanumeric 
characters with hyphens, and trims leading/trailing hyphens.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string to be converted into a slug.&lt;/param&gt;
&lt;returns&gt;A URL\-friendly version of the input string as a lowercase string with hyphens.&lt;/returns&gt;</pre></function>
* <function><a id="joinstrings"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">JoinStrings</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IEnumerable\<string\></span> items, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> delimiter = <span style="color:#D70000; margin-right:1px">","</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Joins a collection of strings into a single string using the specified delimiter.
&lt;/summary&gt;
&lt;param name=&quot;items&quot;&gt;The collection of strings to join.&lt;/param&gt;
&lt;param name=&quot;delimiter&quot;&gt;A string used to separate each element in the joined string. Defaults to &quot;,&quot; if not provided.&lt;/param&gt;
&lt;returns&gt;A single string that is the concatenation of the elements in &lt;paramref name=&quot;items&quot;/&gt;, separated by occurrences of &lt;paramref name=&quot;delimiter&quot;/&gt;.&lt;/returns&gt;</pre></function>
* <function><a id="splitstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SplitString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> delimiter = <span style="color:#D70000; margin-right:1px">","</span>) -> <span style="color:#87AF00">List\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Splits the input string into a list of substrings based on the specified delimiter.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be split.&lt;/param&gt;
&lt;param name=&quot;delimiter&quot;&gt;The delimiter used to separate the substrings. Defaults to a comma (&quot;,&quot;) if not provided.&lt;/param&gt;
&lt;returns&gt;A list containing each substring resulting from the split operation.&lt;/returns&gt;</pre></function>
* <function><a id="removewhitespace"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RemoveWhitespace</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Removes all whitespace characters from the specified input string.
This function utilizes a regular expression to identify and eliminate all forms of 
whitespace, including spaces, tabs, and newlines. The result is returned as a single,
contiguous string without any whitespace characters.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string from which whitespace will be removed.&lt;/param&gt;
&lt;returns&gt;A new string with all whitespace characters removed.&lt;/returns&gt;</pre></function>
* <function><a id="countoccurrences"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CountOccurrences</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> source, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> substring) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Counts the occurrences of a specified substring within the provided source string.
Utilizes regular expressions to ensure accurate matching. If either input is null or empty, they are treated as empty strings by default.
&lt;/summary&gt;
&lt;param name=&quot;source&quot;&gt;The string in which to search for occurrences.&lt;/param&gt;
&lt;param name=&quot;substring&quot;&gt;The substring to count within the source string.&lt;/param&gt;
&lt;returns&gt;The number of times the specified substring occurs in the source string.&lt;/returns&gt;</pre></function>
* <function><a id="startswithignorecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">StartsWithIgnoreCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> prefix) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified input string begins with a given prefix,
ignoring case differences.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to test.&lt;/param&gt;
&lt;param name=&quot;prefix&quot;&gt;The prefix to look for at the start of the input string.&lt;/param&gt;
&lt;returns&gt;&lt;c&gt;true&lt;/c&gt; if input starts with prefix, ignoring case; otherwise, &lt;c&gt;false&lt;/c&gt;.&lt;/returns&gt;</pre></function>
* <function><a id="endswithignorecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EndsWithIgnoreCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> suffix) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether a specified string ends with the given suffix,
ignoring case. If either the input or the suffix is null, appropriate
handling ensures no exceptions are thrown.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be evaluated.&lt;/param&gt;
&lt;param name=&quot;suffix&quot;&gt;The suffix to compare against.&lt;/param&gt;
&lt;returns&gt;True if the input ends with the specified suffix ignoring case; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="containsignorecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ContainsIgnoreCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> source, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toCheck) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified substring is present in the given string, 
ignoring case sensitivity.
&lt;/summary&gt;
&lt;param name=&quot;source&quot;&gt;The source string to search within.&lt;/param&gt;
&lt;param name=&quot;toCheck&quot;&gt;The substring to locate in the source string.&lt;/param&gt;
&lt;returns&gt;True if the substring is found; otherwise, false. Returns false if either input is null.&lt;/returns&gt;</pre></function>
* <function><a id="isalpha"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsAlpha</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified string contains only alphabetic characters.
Utilizes a regular expression to match the entire input against alphabet\-only patterns. 
If the input is null, it defaults to an empty string before performing the check.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to evaluate.&lt;/param&gt;
&lt;returns&gt;true if the input contains only alphabetic characters; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="isalphanumeric"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsAlphaNumeric</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified string contains only alphanumeric characters.
Uses a predefined regular expression pattern to check if each character in the input 
is either a letter (uppercase or lowercase) or a digit. Returns true if all characters 
match this criteria, otherwise returns false. If the input is null or empty, it defaults 
to an empty string and evaluates accordingly.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be evaluated for alphanumeric content.&lt;/param&gt;
&lt;returns&gt;True if the string is composed solely of letters and digits; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="islowercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsLowerCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines if a given string is in lowercase.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to check.&lt;/param&gt;
&lt;returns&gt;True if the input string is entirely in lowercase, or null/empty; otherwise, false.&lt;/returns&gt;
&lt;remarks&gt;
Uses &lt;see cref=&quot;string.ToLowerInvariant&quot;/&gt; to perform case\-insensitive comparison,
ensuring that culture\-specific casing rules do not affect the result.
&lt;/remarks&gt;</pre></function>
* <function><a id="isuppercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsUpperCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified string is entirely in uppercase.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to evaluate.&lt;/param&gt;
&lt;returns&gt;true if the input is null or an empty string, or if all characters in the input are uppercase; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="tostring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">Str</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the specified object to its string representation. Returns a special 
string for null objects, uses invariant culture formatting for convertible 
objects, and handles tracked dictionaries uniquely by including their Id.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input object to convert to string.&lt;/param&gt;
&lt;returns&gt;A string representing the input object, or special representations
for null, tracked dictionaries, and convertible types. Returns &lt;c&gt;null&lt;/c&gt; 
if conversion fails for non\-conformant objects.&lt;/returns&gt;</pre></function>
* <function><a id="format"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Format</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> format, <span style="color:#87AF00; margin-left:1px; margin-right:1px">param object[]</span> args) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Formats the specified string using the provided arguments.
&lt;/summary&gt;
&lt;param name=&quot;format&quot;&gt;The composite format string.&lt;/param&gt;
&lt;param name=&quot;args&quot;&gt;An array of objects to write using format.&lt;/param&gt;
&lt;returns&gt;A formatted string according to the format and args specified.&lt;/returns&gt;</pre></function>
## String
* <function><a id="reverse"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Reverse</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Reverses the order of characters in a given input string using an efficient method.
This function leverages the Span&lt;T&gt; and String.Create to perform the reversal operation 
in place, minimizing allocations and enhancing performance.
&lt;/summary&gt;
&lt;param name=&quot;text&quot;&gt;The string whose characters are to be reversed.&lt;/param&gt;
&lt;returns&gt;A new string with its characters in reverse order compared to the input.&lt;/returns&gt;</pre></function>
* <function><a id="repeatstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RepeatString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> times) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Repeats the given input string a specified number of times.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be repeated.&lt;/param&gt;
&lt;param name=&quot;times&quot;&gt;The number of times to repeat the string. Must be non\-negative.&lt;/param&gt;
&lt;returns&gt;A new string consisting of the input string repeated &apos;times&apos; times concatenated together. If &apos;times&apos; is zero, an empty string is returned.&lt;/returns&gt;</pre></function>
* <function><a id="truncate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Truncate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> suffix = <span style="color:#D70000; margin-right:1px">"…"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Truncates the given input string to a specified length and appends a suffix if truncation occurs.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The original string to be truncated.&lt;/param&gt;
&lt;param name=&quot;length&quot;&gt;The maximum allowed length for the output string. If the input is shorter, it&apos;s returned unchanged.&lt;/param&gt;
&lt;param name=&quot;suffix&quot;&gt;The string to append at the end if truncation occurs, defaulting to an ellipsis character (…).&lt;/param&gt;
&lt;returns&gt;The truncated string with suffix appended if necessary; otherwise, returns the original string.&lt;/returns&gt;</pre></function>
* <function><a id="countwords"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CountWords</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Counts the number of words in the provided input string using a regular expression pattern.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string from which to count the words.&lt;/param&gt;
&lt;returns&gt;The total number of words found in the input string.&lt;/returns&gt;</pre></function>
* <function><a id="randomstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomString</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> allowedChars = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Generates a random string of the specified length using either provided allowed characters or a default character set.
&lt;/summary&gt;
&lt;param name=&quot;length&quot;&gt;The length of the random string to generate. Must be non\-negative.&lt;/param&gt;
&lt;param name=&quot;allowedChars&quot;&gt;An optional parameter specifying which characters can be used in the generated string. 
If null, a default set of alphanumeric characters is used.&lt;/param&gt;
&lt;returns&gt;A randomly generated string of specified length using allowed or default characters.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentOutOfRangeException&quot;&gt;
Thrown when the specified length is negative.
&lt;/exception&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;
Thrown when the character set (either provided or default) is empty.
&lt;/exception&gt;</pre></function>
* <function><a id="slugify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Slugify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> separator = <span style="color:#D70000; margin-right:1px">"-"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Transforms the input string into a URL\-friendly slug format.
Converts all characters to lowercase, replaces non\-alphanumeric 
characters with hyphens, and trims leading/trailing hyphens.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string to be converted into a slug.&lt;/param&gt;
&lt;returns&gt;A URL\-friendly version of the input string as a lowercase string with hyphens.&lt;/returns&gt;</pre></function>
* <function><a id="joinstrings"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">JoinStrings</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IEnumerable\<string\></span> items, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> delimiter = <span style="color:#D70000; margin-right:1px">","</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Joins a collection of strings into a single string using the specified delimiter.
&lt;/summary&gt;
&lt;param name=&quot;items&quot;&gt;The collection of strings to join.&lt;/param&gt;
&lt;param name=&quot;delimiter&quot;&gt;A string used to separate each element in the joined string. Defaults to &quot;,&quot; if not provided.&lt;/param&gt;
&lt;returns&gt;A single string that is the concatenation of the elements in &lt;paramref name=&quot;items&quot;/&gt;, separated by occurrences of &lt;paramref name=&quot;delimiter&quot;/&gt;.&lt;/returns&gt;</pre></function>
* <function><a id="splitstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SplitString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> delimiter = <span style="color:#D70000; margin-right:1px">","</span>) -> <span style="color:#87AF00">List\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Splits the input string into a list of substrings based on the specified delimiter.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be split.&lt;/param&gt;
&lt;param name=&quot;delimiter&quot;&gt;The delimiter used to separate the substrings. Defaults to a comma (&quot;,&quot;) if not provided.&lt;/param&gt;
&lt;returns&gt;A list containing each substring resulting from the split operation.&lt;/returns&gt;</pre></function>
* <function><a id="removewhitespace"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RemoveWhitespace</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Removes all whitespace characters from the specified input string.
This function utilizes a regular expression to identify and eliminate all forms of 
whitespace, including spaces, tabs, and newlines. The result is returned as a single,
contiguous string without any whitespace characters.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string from which whitespace will be removed.&lt;/param&gt;
&lt;returns&gt;A new string with all whitespace characters removed.&lt;/returns&gt;</pre></function>
* <function><a id="countoccurrences"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CountOccurrences</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> source, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> substring) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Counts the occurrences of a specified substring within the provided source string.
Utilizes regular expressions to ensure accurate matching. If either input is null or empty, they are treated as empty strings by default.
&lt;/summary&gt;
&lt;param name=&quot;source&quot;&gt;The string in which to search for occurrences.&lt;/param&gt;
&lt;param name=&quot;substring&quot;&gt;The substring to count within the source string.&lt;/param&gt;
&lt;returns&gt;The number of times the specified substring occurs in the source string.&lt;/returns&gt;</pre></function>
* <function><a id="startswithignorecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">StartsWithIgnoreCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> prefix) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified input string begins with a given prefix,
ignoring case differences.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to test.&lt;/param&gt;
&lt;param name=&quot;prefix&quot;&gt;The prefix to look for at the start of the input string.&lt;/param&gt;
&lt;returns&gt;&lt;c&gt;true&lt;/c&gt; if input starts with prefix, ignoring case; otherwise, &lt;c&gt;false&lt;/c&gt;.&lt;/returns&gt;</pre></function>
* <function><a id="endswithignorecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EndsWithIgnoreCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> suffix) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether a specified string ends with the given suffix,
ignoring case. If either the input or the suffix is null, appropriate
handling ensures no exceptions are thrown.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be evaluated.&lt;/param&gt;
&lt;param name=&quot;suffix&quot;&gt;The suffix to compare against.&lt;/param&gt;
&lt;returns&gt;True if the input ends with the specified suffix ignoring case; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="containsignorecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ContainsIgnoreCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> source, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toCheck) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified substring is present in the given string, 
ignoring case sensitivity.
&lt;/summary&gt;
&lt;param name=&quot;source&quot;&gt;The source string to search within.&lt;/param&gt;
&lt;param name=&quot;toCheck&quot;&gt;The substring to locate in the source string.&lt;/param&gt;
&lt;returns&gt;True if the substring is found; otherwise, false. Returns false if either input is null.&lt;/returns&gt;</pre></function>
* <function><a id="isalpha"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsAlpha</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified string contains only alphabetic characters.
Utilizes a regular expression to match the entire input against alphabet\-only patterns. 
If the input is null, it defaults to an empty string before performing the check.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to evaluate.&lt;/param&gt;
&lt;returns&gt;true if the input contains only alphabetic characters; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="isalphanumeric"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsAlphaNumeric</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified string contains only alphanumeric characters.
Uses a predefined regular expression pattern to check if each character in the input 
is either a letter (uppercase or lowercase) or a digit. Returns true if all characters 
match this criteria, otherwise returns false. If the input is null or empty, it defaults 
to an empty string and evaluates accordingly.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be evaluated for alphanumeric content.&lt;/param&gt;
&lt;returns&gt;True if the string is composed solely of letters and digits; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="islowercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsLowerCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines if a given string is in lowercase.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to check.&lt;/param&gt;
&lt;returns&gt;True if the input string is entirely in lowercase, or null/empty; otherwise, false.&lt;/returns&gt;
&lt;remarks&gt;
Uses &lt;see cref=&quot;string.ToLowerInvariant&quot;/&gt; to perform case\-insensitive comparison,
ensuring that culture\-specific casing rules do not affect the result.
&lt;/remarks&gt;</pre></function>
* <function><a id="isuppercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsUpperCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified string is entirely in uppercase.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to evaluate.&lt;/param&gt;
&lt;returns&gt;true if the input is null or an empty string, or if all characters in the input are uppercase; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="tostring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">Str</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the specified object to its string representation. Returns a special 
string for null objects, uses invariant culture formatting for convertible 
objects, and handles tracked dictionaries uniquely by including their Id.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input object to convert to string.&lt;/param&gt;
&lt;returns&gt;A string representing the input object, or special representations
for null, tracked dictionaries, and convertible types. Returns &lt;c&gt;null&lt;/c&gt; 
if conversion fails for non\-conformant objects.&lt;/returns&gt;</pre></function>
* <function><a id="format"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Format</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> format, <span style="color:#87AF00; margin-left:1px; margin-right:1px">param object[]</span> args) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Formats the specified string using the provided arguments.
&lt;/summary&gt;
&lt;param name=&quot;format&quot;&gt;The composite format string.&lt;/param&gt;
&lt;param name=&quot;args&quot;&gt;An array of objects to write using format.&lt;/param&gt;
&lt;returns&gt;A formatted string according to the format and args specified.&lt;/returns&gt;</pre></function>
## <a id="string-casing" href="#index_string-casing">String Casing</a>
* <function><a id="tolowercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToLowerCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">LowerCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the specified string to lowercase using culture\-invariant settings.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be converted to lowercase. Can be null or empty.&lt;/param&gt;
&lt;returns&gt;A new string with all characters converted to lowercase, or the original input if it is null or empty.&lt;/returns&gt;</pre></function>
* <function><a id="touppercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToUpperCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">UpperCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the specified string to uppercase using the current culture&apos;s TextInfo.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be converted to uppercase. If null or empty, returns as is.&lt;/param&gt;
&lt;returns&gt;The uppercase representation of the input string, or the original input if it is null or empty.&lt;/returns&gt;</pre></function>
* <function><a id="totitlecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToTitleCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">TitleCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the specified string to title case using invariant culture.
This method ensures that each word in the input string is capitalized,
while maintaining any existing casing for words that should remain unchanged.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to convert to title case.&lt;/param&gt;
&lt;returns&gt;A string with each word converted to title case. If the input is null or empty, returns the original input.&lt;/returns&gt;</pre></function>
* <function><a id="tokebabcase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToKebabCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">KebabCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a given string to Kebab Case format. This involves replacing spaces and underscores with hyphens, converting uppercase letters to lowercase, and ensuring no consecutive hyphens are present. It handles null or empty input gracefully by returning the input as is
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be converted to Kebab Case.&lt;/param&gt;
&lt;returns&gt;A new string formatted in Kebab Case or the original input if it was null or empty.&lt;/returns&gt;</pre></function>
* <function><a id="tocamelcase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToCamelCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">CamelCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a given string to CamelCase format. It transforms the input by 
capitalizing the first letter of each word while removing spaces and other 
whitespace characters, ensuring that only the initial character of the entire 
string is in lowercase unless it was originally uppercase.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to convert to CamelCase.&lt;/param&gt;
&lt;returns&gt;A new string in CamelCase format derived from the input. Returns 
the original string if it is null or empty.&lt;/returns&gt;</pre></function>
* <function><a id="tosnakecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToSnakeCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">SnakeCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the provided input string from PascalCase or CamelCase to snake\_case.
The conversion involves replacing uppercase letters with underscores followed by their lowercase equivalents. 
Consecutive underscores are reduced to a single underscore, and any leading/trailing underscores are removed.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string to convert.&lt;/param&gt;
&lt;returns&gt;A new string in snake\_case format or the original input if it is null or empty.&lt;/returns&gt;</pre></function>
* <function><a id="tosentencecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToSentenceCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">SentenceCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the first character of a given string to uppercase while converting all other characters in the string to lowercase.
If the input is null or empty, it returns the input unchanged.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be converted to sentence case.&lt;/param&gt;
&lt;returns&gt;A new string with the first character capitalized and remaining characters in lowercase, or the original input if it&apos;s null or empty.&lt;/returns&gt;</pre></function>
## String Casing
* <function><a id="tolowercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToLowerCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">LowerCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the specified string to lowercase using culture\-invariant settings.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be converted to lowercase. Can be null or empty.&lt;/param&gt;
&lt;returns&gt;A new string with all characters converted to lowercase, or the original input if it is null or empty.&lt;/returns&gt;</pre></function>
* <function><a id="touppercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToUpperCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">UpperCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the specified string to uppercase using the current culture&apos;s TextInfo.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be converted to uppercase. If null or empty, returns as is.&lt;/param&gt;
&lt;returns&gt;The uppercase representation of the input string, or the original input if it is null or empty.&lt;/returns&gt;</pre></function>
* <function><a id="totitlecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToTitleCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">TitleCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the specified string to title case using invariant culture.
This method ensures that each word in the input string is capitalized,
while maintaining any existing casing for words that should remain unchanged.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to convert to title case.&lt;/param&gt;
&lt;returns&gt;A string with each word converted to title case. If the input is null or empty, returns the original input.&lt;/returns&gt;</pre></function>
* <function><a id="tokebabcase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToKebabCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">KebabCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a given string to Kebab Case format. This involves replacing spaces and underscores with hyphens, converting uppercase letters to lowercase, and ensuring no consecutive hyphens are present. It handles null or empty input gracefully by returning the input as is
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be converted to Kebab Case.&lt;/param&gt;
&lt;returns&gt;A new string formatted in Kebab Case or the original input if it was null or empty.&lt;/returns&gt;</pre></function>
* <function><a id="tocamelcase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToCamelCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">CamelCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a given string to CamelCase format. It transforms the input by 
capitalizing the first letter of each word while removing spaces and other 
whitespace characters, ensuring that only the initial character of the entire 
string is in lowercase unless it was originally uppercase.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to convert to CamelCase.&lt;/param&gt;
&lt;returns&gt;A new string in CamelCase format derived from the input. Returns 
the original string if it is null or empty.&lt;/returns&gt;</pre></function>
* <function><a id="tosnakecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToSnakeCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">SnakeCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the provided input string from PascalCase or CamelCase to snake\_case.
The conversion involves replacing uppercase letters with underscores followed by their lowercase equivalents. 
Consecutive underscores are reduced to a single underscore, and any leading/trailing underscores are removed.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string to convert.&lt;/param&gt;
&lt;returns&gt;A new string in snake\_case format or the original input if it is null or empty.&lt;/returns&gt;</pre></function>
* <function><a id="tosentencecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToSentenceCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">SentenceCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts the first character of a given string to uppercase while converting all other characters in the string to lowercase.
If the input is null or empty, it returns the input unchanged.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be converted to sentence case.&lt;/param&gt;
&lt;returns&gt;A new string with the first character capitalized and remaining characters in lowercase, or the original input if it&apos;s null or empty.&lt;/returns&gt;</pre></function>
## <a id="system" href="#index_system">System</a>
* <function><a id="systemthrottlercallspersecond"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">System_ThrottlerCallsPerSecond</span>() -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the number of allowed calls per second for the current throttler.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The loading context data which includes access to the Store and its Throttler.&lt;/param&gt;
&lt;returns&gt;The calls per second limit set by the Throttler. Returns double.MaxValue if no Throttler is present.&lt;/returns&gt;</pre></function>
* <function><a id="systemisinmemory"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">System_IsInMemory</span>() -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the system is operating in memory mode.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The loader context data containing configuration details.&lt;/param&gt;
&lt;returns&gt;A boolean value indicating if the store configuration specifies an in\-memory mode.&lt;/returns&gt;</pre></function>
* <function><a id="systemcompact"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_Compact</span>() -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Initiates a compaction process on the data store associated with the given loader context.
This operation reduces storage space and improves efficiency by optimizing stored data.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The LoaderContextData providing access to the store that requires compaction.&lt;/param&gt;</pre></function>
* <function><a id="systemimportfromfile"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_ImportFromFile</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> filepath) -> <span style="color:#87AF00">DataChangeType</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Imports data from a specified JSON file and applies import options through the given context.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The LoaderContextData object providing necessary context for importing.&lt;/param&gt;
&lt;param name=&quot;filepath&quot;&gt;The path to the JSON file that should be imported.&lt;/param&gt;
&lt;returns&gt;A DataChangeType indicating the result of the import operation.&lt;/returns&gt;</pre></function>
* <function><a id="systemexporttofile"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_ExportToFile</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> filepath, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> indent = <span style="color:#5FAFAF; margin-right:1px">false</span>) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Exports the data from the provided LoaderContextData store to a specified file.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The context containing the store with the data to be exported.&lt;/param&gt;
&lt;param name=&quot;filepath&quot;&gt;The path of the file where the data should be exported.&lt;/param&gt;
&lt;param name=&quot;indent&quot;&gt;
A boolean value indicating whether the exported data should be formatted with indentation.
Default is false, which results in no indentation.
&lt;/param&gt;</pre></function>
* <function><a id="systemshutdowm"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_Shutdowm</span>() -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Initiates the shutdown process for the system by cancelling the 
ongoing operations linked to a specific shutdown token source. This 
function is protected and should be executed within contexts where
it&apos;s safe to invoke system\-level shutdown procedures.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The loader context data containing the store with a ShutdownTokenSource.&lt;/param&gt;</pre></function>
* <function><a id="systeminfo"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_Info</span>() -> <span style="color:#87AF00">SystemInfo</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves system information including runtime statistics, memory usage,
disk status, and environment details. The method calculates CPU usage percentage
based on the current process&apos;s processor time relative to uptime, checks for degraded 
performance conditions (e.g., high CPU or memory usage), and gathers comprehensive 
data about the system&apos;s runtime environment, memory utilization, and available disk space.
&lt;/summary&gt;
&lt;returns&gt;A &lt;see cref=&quot;SystemInfo&quot;/&gt; object containing detailed information
about the current state of the system including uptime, CPU load, memory allocation,
garbage collection metrics, disk drive details, and environmental settings such as OS 
architecture and processor count.&lt;/returns&gt;</pre></function>
## System
* <function><a id="systemthrottlercallspersecond"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">System_ThrottlerCallsPerSecond</span>() -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves the number of allowed calls per second for the current throttler.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The loading context data which includes access to the Store and its Throttler.&lt;/param&gt;
&lt;returns&gt;The calls per second limit set by the Throttler. Returns double.MaxValue if no Throttler is present.&lt;/returns&gt;</pre></function>
* <function><a id="systemisinmemory"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">System_IsInMemory</span>() -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the system is operating in memory mode.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The loader context data containing configuration details.&lt;/param&gt;
&lt;returns&gt;A boolean value indicating if the store configuration specifies an in\-memory mode.&lt;/returns&gt;</pre></function>
* <function><a id="systemcompact"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_Compact</span>() -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Initiates a compaction process on the data store associated with the given loader context.
This operation reduces storage space and improves efficiency by optimizing stored data.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The LoaderContextData providing access to the store that requires compaction.&lt;/param&gt;</pre></function>
* <function><a id="systemimportfromfile"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_ImportFromFile</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> filepath) -> <span style="color:#87AF00">DataChangeType</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Imports data from a specified JSON file and applies import options through the given context.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The LoaderContextData object providing necessary context for importing.&lt;/param&gt;
&lt;param name=&quot;filepath&quot;&gt;The path to the JSON file that should be imported.&lt;/param&gt;
&lt;returns&gt;A DataChangeType indicating the result of the import operation.&lt;/returns&gt;</pre></function>
* <function><a id="systemexporttofile"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_ExportToFile</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> filepath, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> indent = <span style="color:#5FAFAF; margin-right:1px">false</span>) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Exports the data from the provided LoaderContextData store to a specified file.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The context containing the store with the data to be exported.&lt;/param&gt;
&lt;param name=&quot;filepath&quot;&gt;The path of the file where the data should be exported.&lt;/param&gt;
&lt;param name=&quot;indent&quot;&gt;
A boolean value indicating whether the exported data should be formatted with indentation.
Default is false, which results in no indentation.
&lt;/param&gt;</pre></function>
* <function><a id="systemshutdowm"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_Shutdowm</span>() -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Initiates the shutdown process for the system by cancelling the 
ongoing operations linked to a specific shutdown token source. This 
function is protected and should be executed within contexts where
it&apos;s safe to invoke system\-level shutdown procedures.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The loader context data containing the store with a ShutdownTokenSource.&lt;/param&gt;</pre></function>
* <function><a id="systeminfo"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_Info</span>() -> <span style="color:#87AF00">SystemInfo</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Retrieves system information including runtime statistics, memory usage,
disk status, and environment details. The method calculates CPU usage percentage
based on the current process&apos;s processor time relative to uptime, checks for degraded 
performance conditions (e.g., high CPU or memory usage), and gathers comprehensive 
data about the system&apos;s runtime environment, memory utilization, and available disk space.
&lt;/summary&gt;
&lt;returns&gt;A &lt;see cref=&quot;SystemInfo&quot;/&gt; object containing detailed information
about the current state of the system including uptime, CPU load, memory allocation,
garbage collection metrics, disk drive details, and environmental settings such as OS 
architecture and processor count.&lt;/returns&gt;</pre></function>
## <a id="temperature" href="#index_temperature">Temperature</a>
* <function><a id="fahrenheittocelsius"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FahrenheitToCelsius</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> f) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">FtoC</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a temperature from Fahrenheit to Celsius.
&lt;/summary&gt;
&lt;param name=&quot;f&quot;&gt;The temperature in Fahrenheit.&lt;/param&gt;
&lt;returns&gt;The equivalent temperature in Celsius.&lt;/returns&gt;</pre></function>
* <function><a id="fahrenheittokelvin"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FahrenheitToKelvin</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> f) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">FtoK</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a temperature from Fahrenheit to Kelvin.
&lt;/summary&gt;
&lt;param name=&quot;f&quot;&gt;The temperature in degrees Fahrenheit.&lt;/param&gt;
&lt;returns&gt;The equivalent temperature in Kelvin.&lt;/returns&gt;</pre></function>
* <function><a id="celsiustokelvin"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CelsiusToKelvin</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> c) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">CtoK</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a temperature value from Celsius to Kelvin.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The temperature in degrees Celsius.&lt;/param&gt;
&lt;returns&gt;The equivalent temperature in Kelvin.&lt;/returns&gt;
&lt;/example&gt;</pre></function>
* <function><a id="celsiustofahrenheit"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CelsiusToFahrenheit</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> c) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">CtoF</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a temperature value from Celsius to Fahrenheit.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The temperature in degrees Celsius.&lt;/param&gt;
&lt;returns&gt;The equivalent temperature in degrees Fahrenheit.&lt;/returns&gt;</pre></function>
* <function><a id="kelvintocelsius"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">KelvinToCelsius</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> k) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">KtoC</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a temperature from Kelvin to Celsius.
&lt;/summary&gt;
&lt;param name=&quot;k&quot;&gt;The temperature in Kelvin.&lt;/param&gt;
&lt;returns&gt;The equivalent temperature in Celsius.&lt;/returns&gt;</pre></function>
* <function><a id="kelvintofahrenheit"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">KelvinToFahrenheit</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> k) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">KtoF</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a temperature from Kelvin to Fahrenheit.
&lt;/summary&gt;
&lt;param name=&quot;k&quot;&gt;The temperature in Kelvin.&lt;/param&gt;
&lt;returns&gt;The equivalent temperature in Fahrenheit.&lt;/returns&gt;</pre></function>
## Temperature
* <function><a id="fahrenheittocelsius"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FahrenheitToCelsius</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> f) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">FtoC</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a temperature from Fahrenheit to Celsius.
&lt;/summary&gt;
&lt;param name=&quot;f&quot;&gt;The temperature in Fahrenheit.&lt;/param&gt;
&lt;returns&gt;The equivalent temperature in Celsius.&lt;/returns&gt;</pre></function>
* <function><a id="fahrenheittokelvin"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FahrenheitToKelvin</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> f) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">FtoK</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a temperature from Fahrenheit to Kelvin.
&lt;/summary&gt;
&lt;param name=&quot;f&quot;&gt;The temperature in degrees Fahrenheit.&lt;/param&gt;
&lt;returns&gt;The equivalent temperature in Kelvin.&lt;/returns&gt;</pre></function>
* <function><a id="celsiustokelvin"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CelsiusToKelvin</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> c) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">CtoK</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a temperature value from Celsius to Kelvin.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The temperature in degrees Celsius.&lt;/param&gt;
&lt;returns&gt;The equivalent temperature in Kelvin.&lt;/returns&gt;
&lt;/example&gt;</pre></function>
* <function><a id="celsiustofahrenheit"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CelsiusToFahrenheit</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> c) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">CtoF</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a temperature value from Celsius to Fahrenheit.
&lt;/summary&gt;
&lt;param name=&quot;c&quot;&gt;The temperature in degrees Celsius.&lt;/param&gt;
&lt;returns&gt;The equivalent temperature in degrees Fahrenheit.&lt;/returns&gt;</pre></function>
* <function><a id="kelvintocelsius"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">KelvinToCelsius</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> k) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">KtoC</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a temperature from Kelvin to Celsius.
&lt;/summary&gt;
&lt;param name=&quot;k&quot;&gt;The temperature in Kelvin.&lt;/param&gt;
&lt;returns&gt;The equivalent temperature in Celsius.&lt;/returns&gt;</pre></function>
* <function><a id="kelvintofahrenheit"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">KelvinToFahrenheit</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> k) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">KtoF</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Converts a temperature from Kelvin to Fahrenheit.
&lt;/summary&gt;
&lt;param name=&quot;k&quot;&gt;The temperature in Kelvin.&lt;/param&gt;
&lt;returns&gt;The equivalent temperature in Fahrenheit.&lt;/returns&gt;</pre></function>
## <a id="templating" href="#index_templating">Templating</a>
* <function><a id="smartformat"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">SmartFormat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> format, <span style="color:#87AF00; margin-left:1px; margin-right:1px">param object[]</span> args) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Formats the input string using smart formatting with extended capabilities. This function leverages a custom formatter that can be influenced by context data passed as a parameter. The formatted output adheres to culture\-invariant rules.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The loading context providing additional information for custom formatting.&lt;/param&gt;
&lt;param name=&quot;format&quot;&gt;The format string specifying how the arguments should be formatted and combined.&lt;/param&gt;
&lt;param name=&quot;args&quot;&gt;An array of objects containing the data to format according to the specified format string.&lt;/param&gt;
&lt;returns&gt;A string resulting from applying smart formatting rules to the input data, using culture\-invariant formatting conventions.&lt;/returns&gt;</pre></function>
* <function><a id="scribanformat"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">ScribanFormat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> templateText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> model = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Formats a provided template text using the Scriban templating engine, optionally applying a model as context data.
Incorporates custom methods from the loader context into the rendering process if available.
Throws an InvalidOperationException if the parsed template contains errors.
&lt;/summary&gt;
&lt;param name=&quot;kContext&quot;&gt;The LoaderContextData object containing necessary loading and execution contexts including potential custom methods.&lt;/param&gt;
&lt;param name=&quot;templateText&quot;&gt;The template text to be formatted using Scriban.&lt;/param&gt;
&lt;param name=&quot;model&quot;&gt;An optional dictionary of string keys and object values representing the model data for rendering. Defaults to null if not provided.&lt;/param&gt;
&lt;returns&gt;A string result of the rendered template after applying the given model data or default contexts.&lt;/returns&gt;</pre></function>
* <function><a id="handlebarsformat"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">HandlebarsFormat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> templateText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> model = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Formats a given text using Handlebars syntax with an optional model for data binding.
The function creates a Handlebars instance and configures it to use custom compile\-time features,
then compiles the template and renders it with the provided model (or an empty dictionary if none is supplied).
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The context containing configuration and data needed for compiling the template.&lt;/param&gt;
&lt;param name=&quot;templateText&quot;&gt;The text of the Handlebars template to be compiled and rendered.&lt;/param&gt;
&lt;param name=&quot;model&quot;&gt;An optional dictionary representing the model that provides values for the placeholders in the template.&lt;/param&gt;
&lt;returns&gt;A formatted string resulting from rendering the Handlebars template with the provided model.&lt;/returns&gt;</pre></function>
## Templating
* <function><a id="smartformat"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">SmartFormat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> format, <span style="color:#87AF00; margin-left:1px; margin-right:1px">param object[]</span> args) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Formats the input string using smart formatting with extended capabilities. This function leverages a custom formatter that can be influenced by context data passed as a parameter. The formatted output adheres to culture\-invariant rules.
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The loading context providing additional information for custom formatting.&lt;/param&gt;
&lt;param name=&quot;format&quot;&gt;The format string specifying how the arguments should be formatted and combined.&lt;/param&gt;
&lt;param name=&quot;args&quot;&gt;An array of objects containing the data to format according to the specified format string.&lt;/param&gt;
&lt;returns&gt;A string resulting from applying smart formatting rules to the input data, using culture\-invariant formatting conventions.&lt;/returns&gt;</pre></function>
* <function><a id="scribanformat"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">ScribanFormat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> templateText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> model = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Formats a provided template text using the Scriban templating engine, optionally applying a model as context data.
Incorporates custom methods from the loader context into the rendering process if available.
Throws an InvalidOperationException if the parsed template contains errors.
&lt;/summary&gt;
&lt;param name=&quot;kContext&quot;&gt;The LoaderContextData object containing necessary loading and execution contexts including potential custom methods.&lt;/param&gt;
&lt;param name=&quot;templateText&quot;&gt;The template text to be formatted using Scriban.&lt;/param&gt;
&lt;param name=&quot;model&quot;&gt;An optional dictionary of string keys and object values representing the model data for rendering. Defaults to null if not provided.&lt;/param&gt;
&lt;returns&gt;A string result of the rendered template after applying the given model data or default contexts.&lt;/returns&gt;</pre></function>
* <function><a id="handlebarsformat"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">HandlebarsFormat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> templateText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> model = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Formats a given text using Handlebars syntax with an optional model for data binding.
The function creates a Handlebars instance and configures it to use custom compile\-time features,
then compiles the template and renders it with the provided model (or an empty dictionary if none is supplied).
&lt;/summary&gt;
&lt;param name=&quot;context&quot;&gt;The context containing configuration and data needed for compiling the template.&lt;/param&gt;
&lt;param name=&quot;templateText&quot;&gt;The text of the Handlebars template to be compiled and rendered.&lt;/param&gt;
&lt;param name=&quot;model&quot;&gt;An optional dictionary representing the model that provides values for the placeholders in the template.&lt;/param&gt;
&lt;returns&gt;A formatted string resulting from rendering the Handlebars template with the provided model.&lt;/returns&gt;</pre></function>
## <a id="uniform-resource-locator-url" href="#index_uniform-resource-locator-url">Uniform Resource Locator (URL)</a>
* <function><a id="parseuriquery"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUriQuery</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> uri) -> <span style="color:#87AF00">Dictionary\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the query parameters from a given URI and returns them as a dictionary.
&lt;/summary&gt;
&lt;param name=&quot;uri&quot;&gt;The absolute URI containing query parameters to parse.&lt;/param&gt;
&lt;returns&gt;A dictionary where each key is a parameter name and each value is the corresponding parameter value. 
If a parameter has no value, its entry in the dictionary will have an empty string as the value.&lt;/returns&gt;</pre></function>
* <function><a id="parseuriparts"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUriParts</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> uriString) -> <span style="color:#87AF00">Dictionary\<string, object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the given URI string into its components and returns them as a dictionary.
&lt;/summary&gt;
&lt;param name=&quot;uriString&quot;&gt;The URI string to be parsed.&lt;/param&gt;
&lt;returns&gt;A dictionary containing the components of the URI such as scheme, host, port, path,
query, fragment, user info, absolute URI, segments, and whether it is an absolute URI. 
If the input is a relative URI, only the original string is treated as the path.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown if the provided URI string format is invalid or
if an unexpected error occurs during parsing.&lt;/exception&gt;</pre></function>
## Uniform Resource Locator (URL)
* <function><a id="parseuriquery"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUriQuery</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> uri) -> <span style="color:#87AF00">Dictionary\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the query parameters from a given URI and returns them as a dictionary.
&lt;/summary&gt;
&lt;param name=&quot;uri&quot;&gt;The absolute URI containing query parameters to parse.&lt;/param&gt;
&lt;returns&gt;A dictionary where each key is a parameter name and each value is the corresponding parameter value. 
If a parameter has no value, its entry in the dictionary will have an empty string as the value.&lt;/returns&gt;</pre></function>
* <function><a id="parseuriparts"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUriParts</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> uriString) -> <span style="color:#87AF00">Dictionary\<string, object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses the given URI string into its components and returns them as a dictionary.
&lt;/summary&gt;
&lt;param name=&quot;uriString&quot;&gt;The URI string to be parsed.&lt;/param&gt;
&lt;returns&gt;A dictionary containing the components of the URI such as scheme, host, port, path,
query, fragment, user info, absolute URI, segments, and whether it is an absolute URI. 
If the input is a relative URI, only the original string is treated as the path.&lt;/returns&gt;
&lt;exception cref=&quot;ArgumentException&quot;&gt;Thrown if the provided URI string format is invalid or
if an unexpected error occurs during parsing.&lt;/exception&gt;</pre></function>
## <a id="user-agent-ua" href="#index_user-agent-ua">User agent (UA)</a>
* <function><a id="parseuseragent"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUserAgent</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> userAgent) -> <span style="color:#87AF00">UserAgent</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a user agent string to extract information about the browser or device.
&lt;/summary&gt;
&lt;param name=&quot;userAgent&quot;&gt;The user agent string to be parsed.&lt;/param&gt;
&lt;returns&gt;A UserAgent object containing the name, version, and optionally platform type and name.&lt;/returns&gt;
&lt;exception cref=&quot;InvalidDataException&quot;&gt;
Thrown when the provided user agent string cannot be parsed and results in an unknown type with no identifiable information.
&lt;/exception&gt;</pre></function>
## User agent (UA)
* <function><a id="parseuseragent"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUserAgent</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> userAgent) -> <span style="color:#87AF00">UserAgent</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses a user agent string to extract information about the browser or device.
&lt;/summary&gt;
&lt;param name=&quot;userAgent&quot;&gt;The user agent string to be parsed.&lt;/param&gt;
&lt;returns&gt;A UserAgent object containing the name, version, and optionally platform type and name.&lt;/returns&gt;
&lt;exception cref=&quot;InvalidDataException&quot;&gt;
Thrown when the provided user agent string cannot be parsed and results in an unknown type with no identifiable information.
&lt;/exception&gt;</pre></function>
## <a id="validation" href="#index_validation">Validation</a>
* <function><a id="isvalidemail"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsValidEmail</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> address) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Validates whether a given email address string is valid.
&lt;/summary&gt;
&lt;param name=&quot;address&quot;&gt;The email address to validate.&lt;/param&gt;
&lt;returns&gt;True if the email address is valid and not null; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="isvalidphonenumber"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsValidPhoneNumber</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> number, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> defaultRegion = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines if the provided phone number is valid based on regional formatting rules.
&lt;/summary&gt;
&lt;param name=&quot;number&quot;&gt;The phone number to be validated. If null, returns false.&lt;/param&gt;
&lt;param name=&quot;defaultRegion&quot;&gt;Optional region code used when no region is specified in the phone number; can also be null.&lt;/param&gt;
&lt;returns&gt;True if the phone number is valid according to regional rules, otherwise false.&lt;/returns&gt;</pre></function>
* <function><a id="iscreditcardinfovalid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsCreditCardInfoValid</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cardNo, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> expiryDate = <span style="color:#D70000; margin-right:1px">null</span>, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cvv = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines if the credit card information provided is valid.
Validates the credit card number, CVV, and expiry date according to specified patterns and conditions.
&lt;/summary&gt;
&lt;param name=&quot;cardNo&quot;&gt;The credit card number as a string.&lt;/param&gt;
&lt;param name=&quot;expiryDate&quot;&gt;Optional. The expiry date of the credit card in &quot;MM/yyyy&quot; format.&lt;/param&gt;
&lt;param name=&quot;cvv&quot;&gt;Optional. The CVV code of the credit card.&lt;/param&gt;
&lt;returns&gt;True if all provided credit card information is valid; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="validatejson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ValidateJson</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> json, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> schema) -> <span style="color:#87AF00">Task\<bool\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Validates a JSON string against the provided JSON Schema.
&lt;/summary&gt;
&lt;param name=&quot;json&quot;&gt;The JSON string to validate.&lt;/param&gt;
&lt;param name=&quot;schema&quot;&gt;The JSON schema in string format used for validation.&lt;/param&gt;
&lt;returns&gt;A task that represents the asynchronous operation. The task result contains a boolean indicating whether the JSON is valid against the schema (true if valid, false otherwise).&lt;/returns&gt;</pre></function>
* <function><a id="isurl"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsUrl</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Checks if the provided string is a valid absolute URL.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be checked as a potential URL.&lt;/param&gt;
&lt;returns&gt;True if the input is a valid absolute URL, otherwise false.&lt;/returns&gt;</pre></function>
* <function><a id="isnumeric"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsNumeric</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified string can be parsed as a numeric value.
Utilizes the &lt;see cref=&quot;double.TryParse&quot;/&gt; method to check if the conversion is successful.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string to evaluate for its numeric nature.&lt;/param&gt;
&lt;returns&gt;&lt;c&gt;true&lt;/c&gt; if the string represents a valid double; otherwise, &lt;c&gt;false&lt;/c&gt;.&lt;/returns&gt;</pre></function>
* <function><a id="isguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsGuid</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified string is a valid GUID.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to check for being a valid GUID.&lt;/param&gt;
&lt;returns&gt;True if the input string represents a valid GUID; otherwise, false.&lt;/returns&gt;</pre></function>
## Validation
* <function><a id="isvalidemail"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsValidEmail</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> address) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Validates whether a given email address string is valid.
&lt;/summary&gt;
&lt;param name=&quot;address&quot;&gt;The email address to validate.&lt;/param&gt;
&lt;returns&gt;True if the email address is valid and not null; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="isvalidphonenumber"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsValidPhoneNumber</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> number, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> defaultRegion = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines if the provided phone number is valid based on regional formatting rules.
&lt;/summary&gt;
&lt;param name=&quot;number&quot;&gt;The phone number to be validated. If null, returns false.&lt;/param&gt;
&lt;param name=&quot;defaultRegion&quot;&gt;Optional region code used when no region is specified in the phone number; can also be null.&lt;/param&gt;
&lt;returns&gt;True if the phone number is valid according to regional rules, otherwise false.&lt;/returns&gt;</pre></function>
* <function><a id="iscreditcardinfovalid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsCreditCardInfoValid</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cardNo, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> expiryDate = <span style="color:#D70000; margin-right:1px">null</span>, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cvv = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines if the credit card information provided is valid.
Validates the credit card number, CVV, and expiry date according to specified patterns and conditions.
&lt;/summary&gt;
&lt;param name=&quot;cardNo&quot;&gt;The credit card number as a string.&lt;/param&gt;
&lt;param name=&quot;expiryDate&quot;&gt;Optional. The expiry date of the credit card in &quot;MM/yyyy&quot; format.&lt;/param&gt;
&lt;param name=&quot;cvv&quot;&gt;Optional. The CVV code of the credit card.&lt;/param&gt;
&lt;returns&gt;True if all provided credit card information is valid; otherwise, false.&lt;/returns&gt;</pre></function>
* <function><a id="validatejson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ValidateJson</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> json, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> schema) -> <span style="color:#87AF00">Task\<bool\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Validates a JSON string against the provided JSON Schema.
&lt;/summary&gt;
&lt;param name=&quot;json&quot;&gt;The JSON string to validate.&lt;/param&gt;
&lt;param name=&quot;schema&quot;&gt;The JSON schema in string format used for validation.&lt;/param&gt;
&lt;returns&gt;A task that represents the asynchronous operation. The task result contains a boolean indicating whether the JSON is valid against the schema (true if valid, false otherwise).&lt;/returns&gt;</pre></function>
* <function><a id="isurl"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsUrl</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Checks if the provided string is a valid absolute URL.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to be checked as a potential URL.&lt;/param&gt;
&lt;returns&gt;True if the input is a valid absolute URL, otherwise false.&lt;/returns&gt;</pre></function>
* <function><a id="isnumeric"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsNumeric</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified string can be parsed as a numeric value.
Utilizes the &lt;see cref=&quot;double.TryParse&quot;/&gt; method to check if the conversion is successful.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The input string to evaluate for its numeric nature.&lt;/param&gt;
&lt;returns&gt;&lt;c&gt;true&lt;/c&gt; if the string represents a valid double; otherwise, &lt;c&gt;false&lt;/c&gt;.&lt;/returns&gt;</pre></function>
* <function><a id="isguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsGuid</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Determines whether the specified string is a valid GUID.
&lt;/summary&gt;
&lt;param name=&quot;input&quot;&gt;The string to check for being a valid GUID.&lt;/param&gt;
&lt;returns&gt;True if the input string represents a valid GUID; otherwise, false.&lt;/returns&gt;</pre></function>
## <a id="weather" href="#index_weather">Weather</a>
* <function><a id="fetchweather"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FetchWeather</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> openweathermapApiKey) -> <span style="color:#87AF00">Task\<Dictionary\<string, object\>\></span></function>
## Weather
* <function><a id="fetchweather"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FetchWeather</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> openweathermapApiKey) -> <span style="color:#87AF00">Task\<Dictionary\<string, object\>\></span></function>
## <a id="x509certificates" href="#index_x509certificates">X509Certificates</a>
* <function><a id="parsex509"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseX509</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> certPemString) -> <span style="color:#87AF00">Certificate</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses an X.509 certificate from a PEM\-formatted string and creates a Certificate object containing detailed information about the certificate.
&lt;/summary&gt;
&lt;param name=&quot;certPemString&quot;&gt;The PEM\-encoded certificate as a string.&lt;/param&gt;
&lt;returns&gt;A Certificate object with properties such as thumbprint, serial number, validity period, issuer, subject&lt;/returns&gt;</pre></function>
* <function><a id="createselfsignedcertificate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CreateSelfSignedCertificate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> subject, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySize = <span style="color:#5FAFAF; margin-right:1px">2048</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> validDays = <span style="color:#5FAFAF; margin-right:1px">365</span>, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> hashAlg = <span style="color:#D70000; margin-right:1px">"SHA256"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Creates a self\-signed X.509 certificate with the specified subject name, RSA key size,
validity period in days, and hash algorithm.
&lt;/summary&gt;
&lt;param name=&quot;subject&quot;&gt;The subject name of the certificate.&lt;/param&gt;
&lt;param name=&quot;keySize&quot;&gt;The size of the RSA key, default is 2048 bits.&lt;/param&gt;
&lt;param name=&quot;validDays&quot;&gt;The number of days for which the certificate is valid. Default is 365 days.&lt;/param&gt;
&lt;param name=&quot;hashAlg&quot;&gt;The hash algorithm to use, default is &quot;SHA256&quot;.&lt;/param&gt;
&lt;returns&gt;A PEM formatted string containing both the certificate and</pre></function>
* <function><a id="createcertificateauthority"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CreateCertificateAuthority</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> subject, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySize = <span style="color:#5FAFAF; margin-right:1px">4096</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> validDays = <span style="color:#5FAFAF; margin-right:1px">3650</span>) -> <span style="color:#87AF00">ValueTuple\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Creates a self\-signed Certificate Authority (CA) with specified subject name, RSA key size, and validity period.
&lt;/summary&gt;
&lt;param name=&quot;subject&quot;&gt;
The subject name for the X.500 distinguished name of the certificate authority in a string format.
&lt;/param&gt;
&lt;param name=&quot;keySize&quot;&gt;
Optional parameter specifying the size of the RSA key to be generated. Defaults to 4096 bits if not provided.
&lt;/param&gt;
&lt;param name=&quot;validDays&quot;&gt;
Optional parameter indicating the number of days for which the certificate is valid. Defaults to 3650 days if not provided.
&lt;/param&gt;
&lt;returns&gt;
A tuple containing two strings:
\- CertPem: The PEM\-encoded representation of the self\-signed certificate.
\- KeyPem: The PEM\-encoded representation of the self\-signed certificate.
&lt;/returns&gt;</pre></function>
* <function><a id="signcertificate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SignCertificate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> subject, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> issuerCertPem, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> issuerKeyPem, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySize = <span style="color:#5FAFAF; margin-right:1px">2048</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> validDays = <span style="color:#5FAFAF; margin-right:1px">365</span>) -> <span style="color:#87AF00">string</span></function>
* <function><a id="createcertificatechain"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CreateCertificateChain</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> leafSubject, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> caCertPem, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> caKeyPem, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> validDays = <span style="color:#5FAFAF; margin-right:1px">365</span>) -> <span style="color:#87AF00">string</span></function>
## X509Certificates
* <function><a id="parsex509"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseX509</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> certPemString) -> <span style="color:#87AF00">Certificate</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Parses an X.509 certificate from a PEM\-formatted string and creates a Certificate object containing detailed information about the certificate.
&lt;/summary&gt;
&lt;param name=&quot;certPemString&quot;&gt;The PEM\-encoded certificate as a string.&lt;/param&gt;
&lt;returns&gt;A Certificate object with properties such as thumbprint, serial number, validity period, issuer, subject&lt;/returns&gt;</pre></function>
* <function><a id="createselfsignedcertificate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CreateSelfSignedCertificate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> subject, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySize = <span style="color:#5FAFAF; margin-right:1px">2048</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> validDays = <span style="color:#5FAFAF; margin-right:1px">365</span>, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> hashAlg = <span style="color:#D70000; margin-right:1px">"SHA256"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Creates a self\-signed X.509 certificate with the specified subject name, RSA key size,
validity period in days, and hash algorithm.
&lt;/summary&gt;
&lt;param name=&quot;subject&quot;&gt;The subject name of the certificate.&lt;/param&gt;
&lt;param name=&quot;keySize&quot;&gt;The size of the RSA key, default is 2048 bits.&lt;/param&gt;
&lt;param name=&quot;validDays&quot;&gt;The number of days for which the certificate is valid. Default is 365 days.&lt;/param&gt;
&lt;param name=&quot;hashAlg&quot;&gt;The hash algorithm to use, default is &quot;SHA256&quot;.&lt;/param&gt;
&lt;returns&gt;A PEM formatted string containing both the certificate and</pre></function>
* <function><a id="createcertificateauthority"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CreateCertificateAuthority</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> subject, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySize = <span style="color:#5FAFAF; margin-right:1px">4096</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> validDays = <span style="color:#5FAFAF; margin-right:1px">3650</span>) -> <span style="color:#87AF00">ValueTuple\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">&lt;summary&gt;
Creates a self\-signed Certificate Authority (CA) with specified subject name, RSA key size, and validity period.
&lt;/summary&gt;
&lt;param name=&quot;subject&quot;&gt;
The subject name for the X.500 distinguished name of the certificate authority in a string format.
&lt;/param&gt;
&lt;param name=&quot;keySize&quot;&gt;
Optional parameter specifying the size of the RSA key to be generated. Defaults to 4096 bits if not provided.
&lt;/param&gt;
&lt;param name=&quot;validDays&quot;&gt;
Optional parameter indicating the number of days for which the certificate is valid. Defaults to 3650 days if not provided.
&lt;/param&gt;
&lt;returns&gt;
A tuple containing two strings:
\- CertPem: The PEM\-encoded representation of the self\-signed certificate.
\- KeyPem: The PEM\-encoded representation of the self\-signed certificate.
&lt;/returns&gt;</pre></function>
* <function><a id="signcertificate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SignCertificate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> subject, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> issuerCertPem, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> issuerKeyPem, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySize = <span style="color:#5FAFAF; margin-right:1px">2048</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> validDays = <span style="color:#5FAFAF; margin-right:1px">365</span>) -> <span style="color:#87AF00">string</span></function>
* <function><a id="createcertificatechain"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CreateCertificateChain</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> leafSubject, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> caCertPem, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> caKeyPem, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> validDays = <span style="color:#5FAFAF; margin-right:1px">365</span>) -> <span style="color:#87AF00">string</span></function>
