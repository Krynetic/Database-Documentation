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
  - <a id="index_Length"></a>[Length](#length)
  - <a id="index_Type"></a>[Type](#type)
  - <a id="index_ToBytes"></a>[ToBytes](#tobytes)
  - <a id="index_Array"></a>[Array](#array)
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
  - <a id="index_GetCookieValue"></a>[GetCookieValue](#getcookievalue)
  - <a id="index_SetCookieValue"></a>[SetCookieValue](#setcookievalue)
  - <a id="index_RemoveCookieKey"></a>[RemoveCookieKey](#removecookiekey)
  - <a id="index_HasCookieKey"></a>[HasCookieKey](#hascookiekey)
  - <a id="index_MergeCookies"></a>[MergeCookies](#mergecookies)
  - <a id="index_CookieCount"></a>[CookieCount](#cookiecount)
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
- <a id="index_emojis"></a>[Emojis](#emojis)
  - <a id="index_EmojiRaw"></a>[EmojiRaw](#emojiraw)
  - <a id="index_EmojiAlias"></a>[EmojiAlias](#emojialias)
  - <a id="index_Emojify"></a>[Emojify](#emojify)
  - <a id="index_Demojify"></a>[Demojify](#demojify)
  - <a id="index_EmojiFind"></a>[EmojiFind](#emojifind)
  - <a id="index_EmojiFindAliases"></a>[EmojiFindAliases](#emojifindaliases)
  - <a id="index_EmojiSkinToneVariants"></a>[EmojiSkinToneVariants](#emojiskintonevariants)
  - <a id="index_EmojiRandom"></a>[EmojiRandom](#emojirandom)
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
  - <a id="index_SHA1"></a>[SHA1](#sha1)
  - <a id="index_SHA256"></a>[SHA256](#sha256)
  - <a id="index_SHA512"></a>[SHA512](#sha512)
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
- <a id="index_wifi"></a>[Wifi](#wifi)
  - <a id="index_WifiCode"></a>[WifiCode](#wificode)
  - <a id="index_WifiCode_EAP"></a>[WifiCode_EAP](#wificodeeap)
- <a id="index_x509certificates"></a>[X509Certificates](#x509certificates)
  - <a id="index_ParseX509"></a>[ParseX509](#parsex509)
  - <a id="index_CreateSelfSignedCertificate"></a>[CreateSelfSignedCertificate](#createselfsignedcertificate)
  - <a id="index_CreateCertificateAuthority"></a>[CreateCertificateAuthority](#createcertificateauthority)
  - <a id="index_SignCertificate"></a>[SignCertificate](#signcertificate)
  - <a id="index_CreateCertificateChain"></a>[CreateCertificateChain](#createcertificatechain)
## <a id="csharp" href="#index_csharp">CSharp</a>
* <function><a id="csharp"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">CSharp</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">CSharpScript</span>, <span style="color:#D75F00">Cs</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Evaluates C\# code using the CSharpScript runtime  
***code***: C\# code that should be executed
***input***: Configuration parameters when executing  
**Returns**: Output from execution  
**Examples**:
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

</pre></function>
## <a id="javascript" href="#index_javascript">JavaScript</a>
* <function><a id="javascript"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">JavaScript</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">Js</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Evaluates Javascript code using the YantraJS runtime  
***code***: Javascript code that should be executed
***input***: Configuration parameters when executing  
**Returns**: Output from execution  
**Examples**:
{
&nbsp;&nbsp;&nbsp;&nbsp;&quot;code&quot;: &quot;&quot;&quot;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;function fib(n) {
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return n &lt;= 1 ? n : fib(n \- 1) \+ fib(n \- 2);
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return fib(7);
&nbsp;&nbsp;&nbsp;&nbsp;&quot;&quot;&quot;,
&nbsp;&nbsp;&nbsp;&nbsp;&quot;result.expression&quot;: &quot;JavaScript(code)&quot;
}  

</pre></function>
## <a id="lua" href="#index_lua">Lua</a>
* <function><a id="lua"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Lua</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span></function>
## <a id="python" href="#index_python">Python</a>
* <function><a id="python"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Python</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">Py</span>)</function>
## <a id="ruby" href="#index_ruby">Ruby</a>
* <function><a id="ruby"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Ruby</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#87AF00; margin-left:1px; margin-right:1px">EvalInput</span> input = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">Task\<object\></span> -- (alias <span style="color:#D75F00">Rb</span>)</function>
## <a id="elliptic-curve-digital-signature-algorithm-esdsa" href="#index_elliptic-curve-digital-signature-algorithm-esdsa">Elliptic Curve Digital Signature Algorithm (ESDSA)</a>
* <function><a id="ecdsagenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ECDSAGenerate</span>() -> <span style="color:#87AF00">ValueTuple\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates an ECDSA key pair using the NIST P\-256 curve.  
**Returns**: A tuple containing the Base64\-encoded  

</pre></function>
* <function><a id="ecdsasign"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ECDSASign</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64PrivateKey) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Signs a message using the ECDSA algorithm with a provided  
***message***: The original message to be signed.
***base64PrivateKey***: The base64 encoded private key  

</pre></function>
* <function><a id="ecdsaverify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ECDSAVerify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Signature, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64PublicKey) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Verifies an ECDSA (Elliptic Curve Digital Signature Algorithm) signature for a given message.  
***message***: The original message that was signed.
***base64Signature***: The base64 encoded string representing the signature to be verified.
***base64PublicKey***: The base64 encoded public key  

</pre></function>
## <a id="hash-based-message-authentication-code-hmac" href="#index_hash-based-message-authentication-code-hmac">Hash-based Message Authentication Code (HMAC)</a>
* <function><a id="hmacgenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMACGenerate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> algorithm = <span style="color:#D70000; margin-right:1px">"SHA256"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a Base64 encoded HMAC key for the specified algorithm.  
***algorithm***: The hashing algorithm to use for HMAC (e.g., &quot;SHA256&quot;).  
**Returns**: A string representing the Base64 encoded HMAC key.  

</pre></function>
* <function><a id="hmacsign"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMACSign</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> algorithm = <span style="color:#D70000; margin-right:1px">"SHA256"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Creates an HMAC (Hash\-based Message Authentication Code) signature for a given message using the specified key and algorithm.  
***message***: The input string message to be signed.
***base64Key***: The base64\-encoded secret key used for creating the HMAC signature.
***algorithm***: The hashing algorithm to use, with a default of &quot;SHA256&quot;.  
**Returns**: A base64\-encoded string representing the HMAC signature of the message.  
**Remarks**:
This function uses UTF\-8 encoding for converting the input message into bytes. 
It creates an HMAC using the specified or default algorithm and computes the hash of the input message bytes.
The computed hash is then converted to a base64 string and returned as the signature.
Ensure that the key provided in base64 format is correctly decoded to prevent errors during HMAC generation.  

</pre></function>
* <function><a id="hmacverify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMACVerify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Signature, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> algorithm = <span style="color:#D70000; margin-right:1px">"SHA256"</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Verifies if the provided Base64\-encoded HMAC signature matches the expected HMAC 
signature generated from the given message and key using the specified hash algorithm.  
***message***: The original message for which the HMAC signature is to be verified.
***base64Signature***: The Base64\-encoded HMAC signature to verify against the expected signature.
***base64Key***: The Base64\-encoded key used to generate the HMAC signature.
***algorithm***: The hash algorithm to use for generating the HMAC signature (default is &quot;SHA256&quot;).  
**Returns**: True if the provided signature matches the generated signature; otherwise, false.  

</pre></function>
## <a id="advanced-encryption-standard-aes" href="#index_advanced-encryption-standard-aes">Advanced Encryption Standard (AES)</a>
* <function><a id="aesgenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AESGenerate</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySizeBits = <span style="color:#5FAFAF; margin-right:1px">256</span>) -> <span style="color:#87AF00">ValueTuple\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a new pair of AES Key and Initial Vector (IV)  
***keySizeBits***: AES key size to be created  
**Returns**: Key and IV pair  

</pre></function>
* <function><a id="aesencrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AESEncrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> plaintext, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64IV) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Encrypts a given plaintext using AES encryption with the provided base64 key and IV.  
***plaintext***: The text to be encrypted.
***base64Key***: The base64\-encoded AES key.
***base64IV***: The base64\-encoded IV.  
**Returns**: The base64\-encoded encrypted ciphertext.  

</pre></function>
* <function><a id="aesdecrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AESDecrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64CipherText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64Key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64IV) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Decrypts a base64\-encrypted data using the provided key and initialization vector.  
***base64CipherText***: The encrypted base64 string.
***base64Key***: The base64\-encoded encryption key.
***base64IV***: The base64\-encoded initialization vector.  
**Returns**: The decrypted AES data as a UTF8 string.  

</pre></function>
## <a id="rivest-shamir-adleman-rsa" href="#index_rivest-shamir-adleman-rsa">Rivest Shamir Adleman (RSA)</a>
* <function><a id="rsagenerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RSAGenerate</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySize = <span style="color:#5FAFAF; margin-right:1px">2048</span>) -> <span style="color:#87AF00">ValueTuple\<string, string\></span></function>
* <function><a id="rsaencrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RSAEncrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> plaintext, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64PublicKey) -> <span style="color:#87AF00">string</span></function>
* <function><a id="rsadecrypt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RSADecrypt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64CipherText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64PrivateKey) -> <span style="color:#87AF00">string</span></function>
## <a id="barcode" href="#index_barcode">Barcode</a>
* <function><a id="generateqrcode"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateQRCode</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> payload, <span style="color:#87AF00; margin-left:1px; margin-right:1px">Generator</span> generator = <span style="color:#87AF00; margin-right:1px">Krynetic.Database.Plugins.BarcodePlugin+Generator.PNG</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> pixelsPerModule = <span style="color:#5FAFAF; margin-right:1px">20</span>) -> <span style="color:#87AF00">object</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a QR code based on the provided payload and image generator.  
***payload***: The data to encode in the QR code.
***generator***: The type of image generator to use. Defaults to PNG.
***pixelsPerModule***: The number of pixels per module in the generated QR code.  
**Returns**: An object representing the generated QR code, string or byte\[\].  

</pre></function>
## <a id="built-in" href="#index_built-in">Built-In</a>
* <function><a id="length"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Length</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> obj) -> <span style="color:#5FAFAF">int</span></function>
* <function><a id="type"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Type</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> data) -> <span style="color:#87AF00">DatabaseType</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Returns the database type based on the provided data.  
***data***: The data to determine the database type for.  
**Returns**: The database type.  

</pre></function>
* <function><a id="tobytes"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToBytes</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> value) -> <span style="color:#87AF00">byte[]</span></function>
* <function><a id="array"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Array</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">param object[]</span> items) -> <span style="color:#87AF00">object[]</span></function>
## <a id="cache" href="#index_cache">Cache</a>
* <function><a id="cacheget"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CacheGet</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">object</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Caches a value retrieved from the application cache. If the key is not found in the cache, the method returns null.  
***key***: The key of the value to retrieve.  
**Returns**: The cached value or null if it was not found.  

</pre></function>
* <function><a id="cacheset"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">CacheSet</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">TimeSpan?</span> ttl = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Sets a value in the cache with an optional time\-to\-live (TTL).  
***key***: The key to set.
***value***: The value to store.
***ttl***: Optional TTL, defaults to null.  
**Returns**: True if the cache was successfully set. False otherwise.  

</pre></function>
* <function><a id="cacheremove"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">CacheRemove</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Removes the specified key from the cache.  
***key***: The key to be removed.  

</pre></function>
* <function><a id="cacheclear"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">CacheClear</span>() -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Clears the cache by calling the Clear method on the underlying cache.  

</pre></function>
## <a id="captcha" href="#index_captcha">Captcha</a>
* <function><a id="createcaptcha"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CreateCaptcha</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length = <span style="color:#5FAFAF; margin-right:1px">6</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> width = <span style="color:#5FAFAF; margin-right:1px">200</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> height = <span style="color:#5FAFAF; margin-right:1px">70</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> ttlSeconds = <span style="color:#5FAFAF; margin-right:1px">300</span>) -> <span style="color:#87AF00">ValueTuple\<string, byte[]\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Creates a CAPTCHA challenge with the specified parameters.  
***length***: The length of the CAPTCHA code. Defaults to 6.
***width***: The width of the CAPTCHA image. Defaults to 200 pixels.
***height***: The height of the CAPTCHA image. Defaults to 70 pixels.
***ttlSeconds***: The time\-to\-live (TTL) for the CAPTCHA in seconds. Defaults to 300.  
**Returns**: A tuple containing the generated token and PNG image.  

</pre></function>
* <function><a id="validatecaptcha"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ValidateCaptcha</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> token, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> userInput) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Validates a CAPTCHA token against the stored tokens.  
***token***: The CAPTCHA token to validate.
***userInput***: The user&apos;s input string for comparison.  
**Returns**: True if the token is valid, false otherwise.  

</pre></function>
## <a id="colors" href="#index_colors">Colors</a>
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
## <a id="compression" href="#index_compression">Compression</a>
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
## <a id="containers" href="#index_containers">Containers</a>
* <function><a id="container"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">Container</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> containerName, <span style="color:#87AF00; margin-left:1px; margin-right:1px">param string[]</span> command) -> <span style="color:#87AF00">Task\<object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Executes a command within the specified container asynchronously.  
***containerName***: The name of the container to execute the command in.
***command***: An array of strings representing the command and its arguments to be executed.  
**Returns**: A task that represents the asynchronous operation. The task result contains an anonymous object with properties: StandardOutput, StandardError, ExitCode if successful; otherwise, a string message indicating the container does not exist.  

</pre></function>
## <a id="conversions" href="#index_conversions">Conversions</a>
* <function><a id="convertangle"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertAngle</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts an angle value from one unit to another.  
***value***: The numeric value of the angle.
***fromUnit***: The current unit of the angle, which can be &quot;rad&quot;, &quot;radian&quot;, &quot;radians&quot;, &quot;deg&quot;, &quot;degree&quot;, &quot;degrees&quot;, &quot;grad&quot;, &quot;gradian&quot;, or &quot;gradians&quot;.
***toUnit***: The desired unit for conversion, which can be &quot;rad&quot;, &quot;radian&quot;, &quot;radians&quot;, &quot;deg&quot;, &quot;degree&quot;, &quot;degrees&quot;, &quot;grad&quot;, &quot;gradian&quot;, or &quot;gradians&quot;.  
**Returns**: The angle converted to the specified unit.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when either &apos;fromUnit&apos; or &apos;toUnit&apos; is unsupported.  

</pre></function>
* <function><a id="convertfuelefficiency"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertFuelEfficiency</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts fuel efficiency between different units.  
***value***: The value of fuel efficiency in the source unit.
***fromUnit***: The current unit of measurement (&quot;l/100km&quot;, &quot;mpg&quot; for US miles per gallon, or &quot;ukmpg&quot; for UK miles per gallon).
***toUnit***: The target unit of measurement (&quot;l/100km&quot;, &quot;mpg&quot; for US miles per gallon, or &quot;ukmpg&quot; for UK miles per gallon).  
**Returns**: The converted value in the target unit.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when an unsupported fromUnit or toUnit is specified.  

</pre></function>
* <function><a id="convertluminance"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertLuminance</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a luminance value from one unit to another.  
***value***: The luminance value to be converted.
***fromUnit***: The unit of the input luminance value. Supported units are &quot;cd/m2&quot;, &quot;candela per square meter&quot;, &quot;nits&quot;, &quot;lambert&quot;, and &quot;foot\-lambert&quot;.
***toUnit***: The target unit for conversion. Supported units are &quot;cd/m2&quot;, &quot;candela per square meter&quot;, &quot;nits&quot;, &quot;lambert&quot;, and &quot;foot\-lambert&quot;.  
**Returns**: The luminance value converted to the specified target unit.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when an unsupported fromUnit or toUnit is provided.  

</pre></function>
* <function><a id="convertfrequency"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertFrequency</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a frequency value from one unit of measurement to another.
The function supports conversions between Hertz (Hz), Kilohertz (kHz),
Megahertz (MHz), and Gigahertz (GHz).  
***value***: The numerical frequency value to be converted.
***fromUnit***: The unit of the input frequency. Supported units include &quot;hz&quot;, &quot;hertz&quot;,
&quot;khz&quot;, &quot;kilohertz&quot;, &quot;mhz&quot;, &quot;megahertz&quot;, &quot;ghz&quot;, and &quot;gigahertz&quot;.
***toUnit***: The target unit for conversion. Supported units include &quot;hz&quot;, &quot;hertz&quot;,
&quot;khz&quot;, &quot;kilohertz&quot;, &quot;mhz&quot;, &quot;megahertz&quot;, &quot;ghz&quot;, and &quot;gigahertz&quot;.  
**Returns**: The converted frequency value in the specified target unit.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when either \`fromUnit\` or \`toUnit\` is not supported.  

</pre></function>
* <function><a id="convertforce"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertForce</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a force value from one unit to another.  
***value***: The magnitude of the force to convert.
***fromUnit***: The original unit of the force. Supported units are &quot;N&quot;, &quot;newton&quot;, &quot;newtons&quot;, 
&quot;kgf&quot;, &quot;kilogram\-force&quot; for conversion from, and &quot;N&quot;, &quot;newton&quot;, &quot;newtons&quot;, &quot;kgf&quot;, &quot;kilogram\-force&quot;,
&quot;lbf&quot;, &quot;pound\-force&quot; for conversion to.
***toUnit***: The target unit of the force. Supported units are &quot;N&quot;, &quot;newton&quot;, &quot;newtons&quot;, 
&quot;kgf&quot;, &quot;kilogram\-force&quot;, &quot;lbf&quot;, &quot;pound\-force&quot;.  
**Returns**: The converted force value in the specified toUnit.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when an unsupported fromUnit or toUnit is provided.  

</pre></function>
* <function><a id="convertsoundlevel"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertSoundLevel</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a sound level between decibels (dB) and power ratio.  
***value***: The value to convert.
***fromUnit***: The unit of the input value. Supported values are &quot;db&quot; or &quot;ratio&quot;.
***toUnit***: The target unit for conversion. Only &quot;ratio&quot; is supported as a conversion from &quot;db&quot;.  
**Returns**: The converted sound level in the specified target unit.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when unsupported units are provided or if there&apos;s an attempt to convert between unsupported units.  

</pre></function>
* <function><a id="convertpressure"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertPressure</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a pressure value from one unit of measurement to another.  
***value***: The numerical value of the pressure to convert.
***fromUnit***: The unit of measurement of the input pressure. Supported units are &apos;Pa&apos;, &apos;Pascal&apos;, &apos;Pascals&apos;, &apos;bar&apos;, &apos;bars&apos;, &apos;psi&apos;, &apos;pound per square inch&apos;, &apos;pounds per square inch&apos;, &apos;atm&apos;, &apos;atmosphere&apos;, and &apos;atmospheres&apos;.
***toUnit***: The unit of measurement for the output pressure. Supported units are &apos;Pa&apos;, &apos;Pascal&apos;, &apos;Pascals&apos;, &apos;bar&apos;, &apos;bars&apos;, &apos;psi&apos;, &apos;pound per square inch&apos;, &apos;pounds per square inch&apos;, &apos;atm&apos;, &apos;atmosphere&apos;, and &apos;atmospheres&apos;.  
**Returns**: The converted pressure value in the specified output unit of measurement.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when an unsupported fromUnit or toUnit is provided.  

</pre></function>
* <function><a id="convertenergy"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertEnergy</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts an energy value from one unit to another.  
***value***: The energy value to convert.
***fromUnit***: The unit of the input energy value. Supported units include:
&quot;j&quot;, &quot;joule&quot;, &quot;joules&quot; (J),
&quot;kj&quot;, &quot;kilojoule&quot;, &quot;kilojoules&quot; (kJ),
&quot;cal&quot;, &quot;calorie&quot;, &quot;calories&quot; (cal),
&quot;kcal&quot;, &quot;kilocalorie&quot;, &quot;kilocalories&quot; (kcal),
&quot;wh&quot;, &quot;watt hour&quot;, &quot;watt hours&quot; (Wh).
***toUnit***: The unit to convert the energy value into. Supported units include:
&quot;j&quot;, &quot;joule&quot;, &quot;joules&quot; (J),
&quot;kj&quot;, &quot;kilojoule&quot;, &quot;kilojoules&quot; (kJ),
&quot;cal&quot;, &quot;calorie&quot;, &quot;calories&quot; (cal),
&quot;kcal&quot;, &quot;kilocalorie&quot;, &quot;kilocalories&quot; (kcal),
&quot;wh&quot;, &quot;watt hour&quot;, &quot;watt hours&quot; (Wh).  
**Returns**: The energy value converted to the specified unit.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when an unsupported fromUnit or toUnit is provided.  

</pre></function>
* <function><a id="convertpower"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertPower</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a power value from one unit to another.  
***value***: The numerical value of the power.
***fromUnit***: The unit of the input power, supported units are: &quot;w&quot;, &quot;watt&quot;, &quot;watts&quot;, &quot;kw&quot;, &quot;kilowatt&quot;, &quot;kilowatts&quot;, &quot;hp&quot;, &quot;horsepower&quot;.
***toUnit***: The target unit for conversion, supported units are: &quot;w&quot;, &quot;watt&quot;, &quot;watts&quot;, &quot;kw&quot;, &quot;kilowatt&quot;, &quot;kilowatts&quot;, &quot;hp&quot;, &quot;horsepower&quot;.  
**Returns**: The converted power value in the specified target unit.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when an unsupported fromUnit or toUnit is provided.  

</pre></function>
* <function><a id="convertdatasize"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertDataSize</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a data size from one unit to another.  
***value***: The numeric value representing the amount of data.
***fromUnit***: The unit of measurement for the input value (e.g., &quot;bytes&quot;, &quot;KB&quot;).
***toUnit***: The target unit of measurement to convert to (e.g., &quot;MB&quot;, &quot;bits&quot;).  
**Returns**: The converted data size in the specified target unit.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when an unsupported fromUnit or toUnit is provided.  

</pre></function>
* <function><a id="convertmass"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertMass</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a mass value from one unit to another.  
***value***: The numeric value of the mass to be converted.
***fromUnit***: A string representing the initial unit of measurement (e.g., &quot;kg&quot;, &quot;g&quot;, &quot;lb&quot;).
***toUnit***: A string representing the target unit of measurement (e.g., &quot;kg&quot;, &quot;g&quot;, &quot;oz&quot;).  
**Returns**: A double representing the converted mass in the target unit.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when an unsupported fromUnit or toUnit is provided.  

</pre></function>
* <function><a id="convertvolume"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertVolume</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a volume from one unit to another.  
***value***: The numerical value of the volume to convert.
***fromUnit***: The unit of the input volume. Supported units include liters (l, liter, liters), milliliters (ml, milliliter, milliliters), gallons (gal, gallon, gallons), cups (cup, cups), and fluid ounces (floz, fluid ounce, fluid ounces).
***toUnit***: The unit to convert the volume into. Supported units include those listed for fromUnit.  
**Returns**: The converted volume in the specified target unit.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when either the \`fromUnit\` or \`toUnit\` is unsupported.  

</pre></function>
* <function><a id="convertarea"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertArea</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a specified area value from one unit of measurement to another.  
***value***: The numeric value representing the area to convert.
***fromUnit***: The unit of measurement for the input area (e.g., &quot;m2&quot;, &quot;km2&quot;, &quot;ft2&quot;).
***toUnit***: The target unit of measurement for conversion (e.g., &quot;m2&quot;, &quot;in2&quot;, &quot;acre&quot;).  
**Returns**: The converted area value in the specified target unit.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when an unsupported fromUnit or toUnit is provided.  

</pre></function>
* <function><a id="convertspeed"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertSpeed</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a speed value from one unit of measurement to another.
Supported units for conversion are meters per second (mps, m/s, meters per second),
kilometers per hour (kmh, km/h, kilometers per hour), miles per hour (mph, miles per hour),
and knots (knot, knots). The function first converts the input speed to meters per second,
then converts it to the desired output unit.  
***value***: The speed value to convert.
***fromUnit***: The unit of measurement for the input speed. Valid units include &quot;mps&quot;, &quot;m/s&quot;,
&quot;meters per second&quot;, &quot;kmh&quot;, &quot;km/h&quot;, &quot;kilometers per hour&quot;, &quot;mph&quot;, &quot;miles per hour&quot;, &quot;knot&quot;, and &quot;knots&quot;.
***toUnit***: The unit of measurement for the output speed. Valid units include &quot;mps&quot;, &quot;m/s&quot;,
&quot;meters per second&quot;, &quot;kmh&quot;, &quot;km/h&quot;, &quot;kilometers per hour&quot;, &quot;mph&quot;, &quot;miles per hour&quot;, &quot;knot&quot;, and &quot;knots&quot;.  
**Returns**: The converted speed value in the desired unit of measurement.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when an unsupported fromUnit or toUnit is provided.  

</pre></function>
* <function><a id="converttime"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertTime</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a time value from one unit to another.  
***value***: The numeric value representing the time.
***fromUnit***: The unit of the input time value. Supported units are &quot;s&quot;, &quot;sec&quot;, &quot;second&quot;, &quot;seconds&quot;,
&quot;min&quot;, &quot;minute&quot;, &quot;minutes&quot;, &quot;h&quot;, &quot;hr&quot;, &quot;hour&quot;, &quot;hours&quot;, &quot;day&quot;, &quot;days&quot;, &quot;ms&quot;, 
&quot;millisecond&quot;, and &quot;milliseconds&quot;.
***toUnit***: The unit to convert the input time value into. Supported units are &quot;s&quot;, &quot;sec&quot;,
&quot;second&quot;, &quot;seconds&quot;, &quot;min&quot;, &quot;minute&quot;, &quot;minutes&quot;, &quot;h&quot;, &quot;hr&quot;, &quot;hour&quot;, &quot;hours&quot;, &quot;day&quot;, 
&quot;days&quot;, &quot;ms&quot;, &quot;millisecond&quot;, and &quot;milliseconds&quot;.  
**Returns**: A double representing the converted time value in the target unit.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when an unsupported fromUnit or toUnit is provided.  

</pre></function>
* <function><a id="convertlength"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ConvertLength</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> value, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fromUnit, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toUnit) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a length value from one unit to another.  
***value***: The numerical value representing the length.
***fromUnit***: The unit of measurement for the input value. Supported units include meters (m, meter, meters), kilometers (km, kilometer, kilometers), centimeters (cm, centimeter, centimeters), millimeters (mm, millimeter, millimeters), miles (mi, mile, miles), US miles (usmile, us mile, us miles), yards (yd, yard, yards), feet (ft, foot, feet), and inches (in, inch, inches).
***toUnit***: The unit of measurement for the output value. Supported units include meters (m, meter, meters), kilometers (km, kilometer, kilometers), centimeters (cm, centimeter, centimeters), millimeters (mm, millimeter, millimeters), miles (mi, mile, miles), US miles (usmile, us mile, us miles), yards (yd, yard, yards), feet (ft, foot, feet), and inches (in, inch, inches).  
**Returns**: The converted length value in the specified toUnit.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when an unsupported fromUnit or toUnit is provided.  

</pre></function>
## <a id="cookies" href="#index_cookies">Cookies</a>
* <function><a id="parsecookie"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseCookie</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cookie) -> <span style="color:#87AF00">Dictionary\<string, object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a cookie string into a dictionary of key\-value pairs, where values are dynamically typed objects.  
***cookie***: The cookie string to parse.  
**Returns**: A dictionary containing the parsed key\-value pairs from the cookie string. The keys are strings and
        the values can be of type null, bool, int, long, double, DateTime, Guid, or string, depending on their format in the input.
        If the input is empty or null, an empty dictionary with case\-insensitive string comparison for keys is returned.  

</pre></function>
* <function><a id="createcookie"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CreateCookie</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> data) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Creates a cookie string from the provided key\-value pairs in the data dictionary.
Each key and value pair is concatenated with an &apos;=&apos; character, and multiple
pairs are separated by &apos;; &apos;. If the input dictionary contains no elements, an empty string is returned.  
***data***: A dictionary containing cookie name and values as key\-value pairs.  
**Returns**: A string representing a formatted cookie with all provided data.  

</pre></function>
* <function><a id="getcookievalue"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetCookieValue</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cookie, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">object</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the value of a specific cookie key from a cookie string.  
***cookie***: The full cookie string to search.
***key***: The cookie key whose value should be retrieved.  
**Returns**: The value associated with the specified cookie key if found; otherwise, null.
The returned value may be of type bool, int, long, double, DateTime, Guid, or string.  

</pre></function>
* <function><a id="setcookievalue"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SetCookieValue</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cookie, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Sets or updates a cookie key with the specified value and returns the updated cookie string.  
***cookie***: The original cookie string.
***key***: The cookie key to set or update.
***value***: The value to assign to the cookie key.  
**Returns**: A new cookie string containing the updated key\-value pair.  

</pre></function>
* <function><a id="removecookiekey"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RemoveCookieKey</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cookie, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Removes a specific cookie key from a cookie string.  
***cookie***: The original cookie string.
***key***: The cookie key to remove.  
**Returns**: A new cookie string with the specified key removed.  

</pre></function>
* <function><a id="hascookiekey"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HasCookieKey</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cookie, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether a specific cookie key exists within a cookie string.  
***cookie***: The cookie string to inspect.
***key***: The cookie key to check for existence.  
**Returns**: true if the specified key exists; otherwise, false.  

</pre></function>
* <function><a id="mergecookies"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">MergeCookies</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> baseCookie, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> overrideCookie) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Merges two cookie strings, where values from the override cookie replace values
from the base cookie when keys collide.  
***baseCookie***: The base cookie string.
***overrideCookie***: The cookie string whose values take precedence.  
**Returns**: A merged cookie string containing keys from both inputs.  

</pre></function>
* <function><a id="cookiecount"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CookieCount</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cookie) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Counts the number of distinct cookie key\-value pairs in a cookie string.  
***cookie***: The cookie string to analyze.  
**Returns**: The total number of parsed cookie entries.  

</pre></function>
## <a id="date" href="#index_date">Date</a>
* <function><a id="tounixtimeseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToUnixTimeSeconds</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset</span> dt) -> <span style="color:#5FAFAF">long</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a given DateTimeOffset to its Unix timestamp in seconds.
The Unix timestamp represents the number of seconds that have elapsed since 
00:00:00 UTC on 1 January 1970, not counting leap seconds.  
***dt***: The DateTimeOffset value to convert.  
**Returns**: A long integer representing the Unix timestamp in seconds.  

</pre></function>
* <function><a id="tounixtimemilliseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToUnixTimeMilliseconds</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset</span> dt) -> <span style="color:#5FAFAF">long</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the given DateTimeOffset to Unix time expressed in milliseconds.
Unix time is defined as the number of milliseconds that have elapsed since 00:00:00 UTC on January 1, 1970 (excluding leap seconds).  
***dt***: The DateTimeOffset value to convert.  
**Returns**: A long integer representing the number of milliseconds since the Unix epoch.  

</pre></function>
* <function><a id="fromunixtimeseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromUnixTimeSeconds</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">long</span> seconds) -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a Unix timestamp (seconds since January 1, 1970) to a 
DateTimeOffset value in the local time zone.  
***seconds***: The number of seconds that have elapsed since January 1, 1970.  
**Returns**: A DateTimeOffset object representing the equivalent date and time in the local time zone.  

</pre></function>
* <function><a id="fromunixtimemilliseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromUnixTimeMilliseconds</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">long</span> milliseconds) -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the specified Unix time in milliseconds to a DateTimeOffset value.  
***milliseconds***: The number of 100\-nanosecond intervals since January 1, 1970 (midnight UTC).  
**Returns**: A DateTimeOffset value that is equivalent to the specified Unix time in milliseconds.  
**Exceptions**:
**Type**: ArgumentOutOfRangeException
**Description**: Thrown when the input value represents a date earlier than January 1, 0001. \-OR\- Thrown when the input value represents a date later than December 31, 9999.  

</pre></function>
* <function><a id="nowprecise"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NowPrecise</span>() -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Provides the current date and time in UTC with high precision.  
**Returns**: A DateTimeOffset object representing the current date and time in Coordinated Universal Time (UTC).  

</pre></function>
* <function><a id="now"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Now</span>() -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the current date and time based on the loading options provided in the context.
This function returns a DateTimeOffset value representing &quot;now&quot; as defined within the context&apos;s 
LoadingOptions. It is used to ensure consistency in timing across different parts of an application 
or plugin system that share the same context configuration.  
**Returns**: A DateTimeOffset value representing the current date and time as specified by the context&apos;s LoadingOptions.NowShared property.  

</pre></function>
* <function><a id="nowntp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">NowNtp</span>() -> <span style="color:#87AF00">Task\<DateTimeOffset\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the current network time from an NTP server asynchronously.  
**Returns**: A task that represents the asynchronous operation, and contains a DateTimeOffset object representing the current date and time as reported by the NTP server.  

</pre></function>
## <a id="documentation" href="#index_documentation">Documentation</a>
* <function><a id="documentationtyped"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DocumentationTyped</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> function) -> <span style="color:#87AF00">XmlDocumentation</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the typed XML documentation for a specified function.  
***function***: The name of the function whose documentation is being retrieved.  
**Returns**: The parsed XML documentation object corresponding to the given function, or null if not found.  

</pre></function>
* <function><a id="documentation"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Documentation</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> function) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the XML documentation for a specified function within the given loader context data.  
***function***: The name of the function whose documentation is to be retrieved.  
**Returns**: A string representing the raw XML documentation for the specified function, 
        or null if no documentation is found.  

</pre></function>
## <a id="emojis" href="#index_emojis">Emojis</a>
* <function><a id="emojiraw"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EmojiRaw</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> alias) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Gets the raw Unicode string of the emoji associated with the given alias.  
***alias***: The emoji alias (e.g. :tada:).  
**Returns**: The raw Unicode emoji, or an empty string if not found.  
**Examples**:
EmojiRaw(&quot;:tada:&quot;); // &quot;🎉&quot;  

</pre></function>
* <function><a id="emojialias"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EmojiAlias</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> raw) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Gets the primary alias of the emoji represented by the raw Unicode string.  
***raw***: The raw Unicode emoji (e.g. 🎉).  
**Returns**: The emoji alias, or an empty alias if not found.  
**Examples**:
EmojiAlias(&quot;🎉&quot;); // &quot;:tada:&quot;  

</pre></function>
* <function><a id="emojify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Emojify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Replaces emoji aliases in the input text with their raw Unicode equivalents.  
***text***: A text containing emoji aliases.  
**Returns**: The emojified text.  
**Examples**:
Emojify(&quot;initial :tada: commit&quot;); // &quot;initial 🎉 commit&quot;  

</pre></function>
* <function><a id="demojify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Demojify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Replaces raw Unicode emojis in the input text with their alias representations.  
***text***: A text containing raw Unicode emojis.  
**Returns**: The demojified text.  
**Examples**:
Demojify(&quot;initial 🎉 commit&quot;); // &quot;initial :tada: commit&quot;  

</pre></function>
* <function><a id="emojifind"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EmojiFind</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> query) -> <span style="color:#87AF00">string[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Finds emojis that match the given query and returns their raw Unicode values.  
***query***: A search value matched against emoji description, category, aliases or tags.  
**Returns**: An array of raw Unicode emojis.  
**Examples**:
EmojiFind(&quot;party&quot;); // \[&quot;🎉&quot;, &quot;🥳&quot;, ...\]  

</pre></function>
* <function><a id="emojifindaliases"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EmojiFindAliases</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> query) -> <span style="color:#87AF00">string[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Finds emojis that match the given query and returns their primary aliases.  
***query***: A search value matched against emoji description, category, aliases or tags.  
**Returns**: An array of emoji aliases.  
**Examples**:
EmojiFindAliases(&quot;party&quot;); // \[&quot;:tada:&quot;, &quot;:partying\_face:&quot;, ...\]  

</pre></function>
* <function><a id="emojiskintonevariants"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EmojiSkinToneVariants</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Gets all raw Unicode skin tone variants for the specified emoji.  
***value***: An emoji alias or raw Unicode string that supports skin tone modifiers.  
**Returns**: An array of raw Unicode skin tone variants.  
**Examples**:
EmojiSkinToneVariants(&quot;✌️&quot;); // \[&quot;✌🏻&quot;,&quot;✌🏼&quot;,&quot;✌🏽&quot;,&quot;✌🏾&quot;,&quot;✌🏿&quot;\]  

</pre></function>
* <function><a id="emojirandom"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EmojiRandom</span>() -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Gets a random emoji from the global emoji set.  
**Returns**: A raw Unicode emoji.  
**Examples**:
EmojiRandom(); // &quot;🎉&quot;  

</pre></function>
## <a id="encoding" href="#index_encoding">Encoding</a>
* <function><a id="base64encode"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Base64Encode</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> plainText) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Encodes a given plain text string into its Base64 representation.  
***plainText***: The input string to be encoded in UTF\-8 and then converted to Base64.  
**Returns**: A Base64\-encoded string derived from the provided plain text.  

</pre></function>
* <function><a id="base64decode"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Base64Decode</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> base64EncodedData) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Decodes a Base64 encoded string into its original UTF\-8 representation.  
***base64EncodedData***: The Base64 encoded data to be decoded.  
**Returns**: A string representing the decoded UTF\-8 text from the provided Base64 input.  

</pre></function>
## <a id="environment" href="#index_environment">Environment</a>
* <function><a id="getenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> defaultValue = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the value of an environment variable specified by the given key.  
***key***: The name of the environment variable to retrieve.
***defaultValue***: The default value to return if the environment variable is not found or its value is null.
This parameter is optional and defaults to null.  
**Returns**: The value of the environment variable as a string, or the specified default value
if the environment variable does not exist or has a null value.  
**Exceptions**:
**Type**: ArgumentNullException
**Description**: Thrown when the key argument is null or empty.  

</pre></function>
* <function><a id="getenvorthrow"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetEnvOrThrow</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the value of a specified environment variable or throws an exception if it is not set.  
***key***: The key of the environment variable to retrieve.  
**Returns**: The value of the specified environment variable.  
**Exceptions**:
**Type**: ArgumentNullException
**Description**: Thrown when the provided key is null or empty.  
**Type**: InvalidOperationException
**Description**: Thrown when the environment variable with the specified key is not set.  

</pre></function>
* <function><a id="hasenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HasEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Checks if a specified environment variable exists.  
***key***: The key of the environment variable to check.  
**Returns**: True if the environment variable with the given key exists and is not null; otherwise, false.  
**Exceptions**:
**Type**: ArgumentNullException
**Description**: Thrown when the provided key is null or empty.  

</pre></function>
* <function><a id="getallenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetAllEnv</span>() -> <span style="color:#87AF00">Dictionary\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves all environment variables as a dictionary with the variable names as keys and their corresponding values as strings.  
**Returns**: A dictionary where each key is an environment variable name (string) and each value is its associated value (string), or null if not set.  

</pre></function>
* <function><a id="expandenv"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExpandEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Expands any environment variables contained within the specified string.  
***value***: The input string that may contain environment variable references.  
**Returns**: A new string with all environment variables in &quot;value&quot; replaced by their corresponding values.  
**Exceptions**:
**Type**: ArgumentNullException
**Description**: Thrown when the provided value is null.  

</pre></function>
* <function><a id="setenv"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">SetEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Sets an environment variable for the current process.  
***key***: The name of the environment variable to set. Cannot be null or empty.
***value***: The value of the environment variable. Can be null, which removes any existing value for the key.  
**Exceptions**:
**Type**: ArgumentNullException
**Description**: Thrown when the key is null or an empty string.  

</pre></function>
* <function><a id="clearenv"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">ClearEnv</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Clears the environment variable specified by the given key. If the key exists in the environment variables, 
it is removed by setting its value to null.  
***key***: The name of the environment variable to clear.  

</pre></function>
## <a id="exchange-rate" href="#index_exchange-rate">Exchange rate</a>
* <function><a id="exchangerate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExchangeRate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> from, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> to) -> <span style="color:#87AF00">Task\<decimal\></span></function>
## <a id="extraction" href="#index_extraction">Extraction</a>
* <function><a id="extractemails"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExtractEmails</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">List\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Extracts and returns a list of email addresses found within the specified input string using regular expressions.  
***input***: The text from which to extract emails.  
**Returns**: A list containing all email addresses identified in the input string.  

</pre></function>
* <function><a id="extracturls"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExtractUrls</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">List\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Represents a plugin function that extracts URLs from the given input string.
This method uses regular expressions to identify and return a list of URL strings found in the input.  
***input***: The input string from which URLs are extracted.  
**Returns**: A list containing all URLs found within the input string. Returns an empty list if no URLs are found.  

</pre></function>
* <function><a id="extractemailuser"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ExtractEmailUser</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> email) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Extracts and returns the user portion of an email address.  
***email***: The full email address from which to extract the user.  
**Returns**: A string representing the user part before the &apos;@&apos; symbol, or an empty string if invalid or null.  

</pre></function>
## <a id="geolocation" href="#index_geolocation">Geolocation</a>
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
## <a id="globally-unique-identifier-guid" href="#index_globally-unique-identifier-guid">Globally Unique Identifier (Guid)</a>
* <function><a id="generateuuid1"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid1</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a UUID version 1 which is based on the current date and time, ensuring uniqueness through node and clock sequence identifiers.
This function creates a new GUID by manually setting its components to align with the UUID v1 specification.  
**Returns**: A Guid representing a UUID version 1.  

</pre></function>
* <function><a id="generateuuid3"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid3</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">Guid</span> namespaceId, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> name) -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a UUID version 3 using MD5 hashing algorithm based on the provided namespace identifier and name.  
***namespaceId***: The GUID representing the UUID namespace.
***name***: The name used to generate the UUID.  
**Returns**: A new Guid instance that represents a UUID version 3.  

</pre></function>
* <function><a id="generateuuid4"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid4</span>() -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">GenerateUuid</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a Version 4 Universally Unique Identifier (UUID) as a string.  
**Returns**: A string representing the generated UUID in its canonical form.  

</pre></function>
* <function><a id="generateuuid5"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid5</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> namespaceId, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> name) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a UUID version 5 based on the given namespace ID and name.
This method utilizes SHA1 hashing to ensure uniqueness according to RFC 4122 specifications.  
***namespaceId***: A valid GUID string representing the namespace.
***name***: The name or identifier for which the UUID is generated.  
**Returns**: A string representation of the generated UUID version 5.  

</pre></function>
* <function><a id="generateuuid6"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateUuid6</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a version 1.6 UUID using the current system time as its basis.
The function creates a GUID by combining a timestamp and random bytes,
conforming to the variant 1.6 specification of the UUID standard.  
**Returns**: A unique identifier (GUID) formatted according to Version 1.6.  

</pre></function>
* <function><a id="generatecombguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateCombGuid</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a COMB (combined) GUID which is sorted lexicographically. 
The method creates a new GUID using the current time in UTC and combines it with 
a date\-based prefix to ensure that the GUIDs are ordered by creation time.  
**Returns**: A new Guid object containing a timestamp component for sorting purposes.  

</pre></function>
* <function><a id="generatetimeorderedguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateTimeOrderedGuid</span>() -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a time\-ordered GUID using the current system ticks to ensure temporal order.
This function is marked as unsafe and serves as a plugin function with the specified identifier.  
**Returns**: A unique identifier (GUID) that incorporates the current UTC timestamp for ordering.  

</pre></function>
## <a id="hashing" href="#index_hashing">Hashing</a>
* <function><a id="crc32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CRC32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">uint</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Computes the CRC\-32 hash of a given string using UTF\-8 encoding.  
***input***: The input string for which to compute the CRC\-32 hash.  
**Returns**: A uint representing the computed CRC\-32 hash value.  

</pre></function>
* <function><a id="crc64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CRC64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Computes the CRC\-64 checksum for a given input string.  
***input***: The input string to calculate the checksum for.  
**Returns**: An unsigned long representing the 64\-bit CRC checksum of the input string.  
**Remarks**:
This function uses UTF\-8 encoding to convert the input string into bytes and then computes the CRC\-64 hash.  

</pre></function>
* <function><a id="xxhash32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">XXHash32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> seed = <span style="color:#5FAFAF; margin-right:1px">0</span>) -> <span style="color:#5FAFAF">uint</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Computes a 32\-bit hash value for the specified input string using the XXHash algorithm.  
***input***: The input string to be hashed.
***seed***: An optional seed value to initialize the hashing process. Default is 0.  
**Returns**: A uint representing the computed hash value of the input string.  

</pre></function>
* <function><a id="xxhash64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">XXHash64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">long</span> seed = <span style="color:#5FAFAF; margin-right:1px">0</span>) -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Computes the XXH64 hash of a given input string using the specified seed value.  
***input***: The input string to be hashed.
***seed***: An optional seed value for the hash function. Defaults to 0 if not provided.  
**Returns**: Returns the computed XXH64 hash as an unsigned long (ulong).  

</pre></function>
* <function><a id="sha1"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA1</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the SHA\-1 hash for a given input string and returns it as a hexadecimal string.
This method utilizes the provided hashing function from the SHA1 class to ensure 
secure hashing of the specified value. The result is returned in a standard format 
suitable for verification or storage purposes. Usage involves passing the target 
string which will be hashed using the SHA\-1 algorithm, leveraging an external plugin 
mechanism.  
***value***: The input string to hash.  
**Returns**: A hexadecimal string representation of the SHA\-1 hash of the input value.  

</pre></function>
* <function><a id="sha256"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA256</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Computes the SHA\-256 hash of the specified input string.
Utilizes a plugin function mechanism to apply the SHA\-256 hashing algorithm.  
***value***: The input string to be hashed.  
**Returns**: A hexadecimal string representing the SHA\-256 hash of the input.  

</pre></function>
* <function><a id="sha512"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SHA512</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Computes the SHA\-512 hash of a given input string.  
***value***: The input string to be hashed.  
**Returns**: A hexadecimal string representation of the SHA\-512 hash.  
**Remarks**:
This method is marked as a plugin function for dynamic loading.  

</pre></function>
* <function><a id="md5"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">MD5</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Computes the MD5 hash of a given input string.
This method utilizes a custom plugin function mechanism to process the string.  
***value***: The input string to be hashed.  
**Returns**: A hexadecimal string representing the MD5 hash of the input.  

</pre></function>
* <function><a id="hmacsha256"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMAC_SHA256</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Computes the HMAC\-SHA256 hash for a given key and value.  
***key***: The secret key used in the hashing process.
***value***: The data to be hashed using the provided key.  
**Returns**: A hexadecimal string representing the HMAC\-SHA256 hash of the input value.  

</pre></function>
* <function><a id="hmacsha512"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HMAC_SHA512</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> value) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Computes the HMAC\-SHA512 hash for the given key and value.  
***key***: The secret key used for hashing.
***value***: The input data to be hashed.  
**Returns**: A string representation of the resulting HMAC\-SHA512 hash.  

</pre></function>
## <a id="hypertext-transfer-protocol-http" href="#index_hypertext-transfer-protocol-http">Hypertext Transfer Protocol (HTTP)</a>
* <function><a id="http"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HTTP</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> url, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> method, <span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> headers, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> body, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> mode) -> <span style="color:#87AF00">Task\<object\></span></function>
## <a id="json" href="#index_json">JSON</a>
* <function><a id="tojson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToJSON</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> obj, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> indented) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Serializes an object to a JSON string with optional indentation.  
***obj***: The object to serialize. Can be null.
***indented***: A boolean indicating whether the output JSON should be indented for readability.
If true, the resulting JSON will include whitespace and line breaks.
If false, the resulting JSON will be compact without unnecessary spaces or newlines.  
**Returns**: A string representation of the serialized object in JSON format. Returns null if the input object is null.  

</pre></function>
* <function><a id="formatjson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FormatJSON</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> json, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> indented = <span style="color:#5FAFAF; margin-right:1px">true</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Formats a JSON string with optional indentation.  
***json***: The JSON string to format. Can be null.
***indented***: A boolean indicating whether the output should be indented for readability. Default is true.  
**Returns**: A formatted JSON string if input is valid; otherwise, null.  

</pre></function>
* <function><a id="parsejson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseJSON</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> json) -> <span style="color:#87AF00">object</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a JSON string and deserializes it into an object.  
***json***: The JSON string to parse.  
**Returns**: An object representing the deserialized data from the input JSON, or null if the input is null.  

</pre></function>
## <a id="json-web-token-jwt" href="#index_json-web-token-jwt">JSON Web Token (JWT)</a>
* <function><a id="encodejwt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EncodeJwt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> claims, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> secret) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Encodes a JSON Web Token (JWT) using the specified claims and secret key.
The token is composed of three parts: header, payload, and signature. 
The header specifies the algorithm (&quot;HS256&quot;) used for signing the JWT, 
while the payload contains the claims to be encoded in the JWT. 
Finally, the signature is generated using HMAC SHA\-256 with the secret key.  
***claims***: A dictionary of claims to include in the JWT.
***secret***: The secret key used for signing the JWT.  
**Returns**: A string representing the encoded JWT.  

</pre></function>
* <function><a id="decodejwt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">DecodeJwt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> token, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> secret = <span style="color:#D70000; margin-right:1px">null</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> includeMetadata = <span style="color:#5FAFAF; margin-right:1px">false</span>) -> <span style="color:#87AF00">IDictionary\<string, object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Decodes a JWT (JSON Web Token) and validates its HMAC\-SHA256 signature using an optional secret.
Throws exceptions for invalid tokens or signatures. Optionally includes token metadata in the output.  
***token***: The JWT to decode.
***secret***: Optional secret key used to validate the signature (for HMAC\-SHA256).
***includeMetadata***: Whether to include the JWT header and signature as metadata in the returned dictionary.  
**Returns**: A dictionary containing the decoded JWT payload, optionally including header and signature metadata.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when the token is empty or null.  
**Type**: FormatException
**Description**: Thrown when the token does not have exactly three parts separated by dots.  
**Type**: NotSupportedException
**Description**: Thrown when the algorithm specified in the JWT header is not HS256.  
**Type**: CryptographicException
**Description**: Thrown when the signature of the token cannot be validated with the given secret.  

</pre></function>
* <function><a id="isjwt"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsJwt</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> token) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines if the provided string is a valid JWT (JSON Web Token).  
***token***: The token to be validated as a JWT.  
**Returns**: True if the token is a valid JWT; otherwise, false.  

</pre></function>
## <a id="large-language-model-llm" href="#index_large-language-model-llm">Large Language Model (LLM)</a>
* <function><a id="ailmstudio"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AI_LMStudio</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> prompt, <span style="color:#87AF00; margin-left:1px; margin-right:1px">LMStudioConfig</span> config) -> <span style="color:#87AF00">Task\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Asynchronously communicates with the LMStudio AI model to generate a chat completion response.
The function creates and sends a request using specified configurations, then returns the generated content as a string.  
***prompt***: The user input prompt for the AI model.
***config***: Configuration settings for the LMStudioClient, including endpoint URL, model type, maximum tokens,
and temperature. The configuration cannot be null.  
**Returns**: A task representing the asynchronous operation, which upon completion provides a string
containing the AI\-generated response based on the given prompt.  

</pre></function>
* <function><a id="aiopenai"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">AI_OpenAI</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> prompt, <span style="color:#87AF00; margin-left:1px; margin-right:1px">OpenAIConfig</span> config) -> <span style="color:#87AF00">Task\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Asynchronously interacts with OpenAI&apos;s API to generate a response based on the provided prompt.
Utilizes configuration settings for API key or endpoint, model specification,
and various other parameters such as maximum tokens and temperature for generation.  
***prompt***: The user input string prompting the AI for a specific task.
***config***: Configuration object containing OpenAI API details like API key, model type,
endpoint URI, max tokens limit, and temperature settings.  
**Returns**: A Task that represents the asynchronous operation, which upon completion yields
the generated response string from the AI based on the user prompt.  

</pre></function>
## <a id="lookup" href="#index_lookup">Lookup</a>
* <function><a id="lookup"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Lookup</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> fullkey = <span style="color:#D70000; margin-right:1px">""</span>) -> <span style="color:#87AF00">object</span> -- (alias <span style="color:#D75F00">$</span>)</function>
* <function><a id="parent"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Parent</span>() -> <span style="color:#87AF00">string</span></function>
* <function><a id="self"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Self</span>() -> <span style="color:#87AF00">string</span></function>
## <a id="math" href="#index_math">Math</a>
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
## <a id="multipurpose-internet-mail-extensions-mime" href="#index_multipurpose-internet-mail-extensions-mime">Multipurpose Internet Mail Extensions (MIME)</a>
* <function><a id="getmimefromextension"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetMimeFromExtension</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> ext) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the MIME type associated with a given file extension.  
***ext***: The file extension for which to retrieve the MIME type. Must not be null or whitespace.  
**Returns**: A string representing the MIME type, or an empty string if the extension is null, whitespace, or has no associated MIME type.  

</pre></function>
* <function><a id="getextensionfrommime"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GetExtensionFromMime</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> mime) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the file extension associated with a given MIME type. If the MIME type is null, empty, or whitespace,
an empty string is returned. Otherwise, the method trims any leading or trailing whitespace from the input and 
attempts to find the first corresponding extension using the MimeTypes.GetMimeTypeExtensions method.
If no suitable extension is found, it defaults to &quot;.bin&quot;.  
***mime***: The MIME type for which to retrieve the file extension.  
**Returns**: A string representing the associated file extension or &quot;.bin&quot; if none are found; an empty string
if the input MIME type is null, empty, or only whitespace.  

</pre></function>
## <a id="networking" href="#index_networking">Networking</a>
* <function><a id="istcpportopen"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsTcpPortOpen</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> hostName, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> port, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> timeoutMs = <span style="color:#5FAFAF; margin-right:1px">5000</span>) -> <span style="color:#87AF00">Task\<bool\></span></function>
* <function><a id="whois"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Whois</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> ip) -> <span style="color:#87AF00">Task\<WhoisResponseScoped\></span></function>
* <function><a id="isvpn"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsVPN</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> ip) -> <span style="color:#87AF00">Task\<bool\></span></function>
## <a id="one-time-password-otp" href="#index_one-time-password-otp">One-Time Password (OTP)</a>
* <function><a id="generatetotp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">GenerateTOTP</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset?</span> at = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a Time\-based One\-Time Password (TOTP) based on the provided secret key.  
***key***: The base32 encoded secret key used to generate the TOTP.
***at***: An optional DateTimeOffset representing the time for which the TOTP is calculated. 
If not specified, the current UTC time is used.  
**Returns**: A string representation of the 6\-digit TOTP code generated from the provided key and time.  

</pre></function>
* <function><a id="verifytotp"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">VerifyTOTP</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> key, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> code, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> window = <span style="color:#5FAFAF; margin-right:1px">0</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Verifies a Time\-based One\-Time Password (TOTP) against the provided key and time window.  
***key***: The base32\-encoded secret key used to generate TOTP.
***code***: The TOTP code to be verified.
***window***: The number of past and future intervals (default is 0) to check for validity, where each interval is 30 seconds.  
**Returns**: True if the provided code matches a valid TOTP generated within the specified time window; otherwise, false.  

</pre></function>
* <function><a id="remainingtotpseconds"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RemainingTOTPSeconds</span>() -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the remaining time in seconds until the next Time\-based One\-Time Password (TOTP) changes.
TOTPs are typically refreshed every 30 seconds, and this function computes how many seconds 
remain before the next refresh. This can be useful for applications requiring synchronization
or timing\-related operations based on TOTP intervals.  
**Returns**: An integer representing the number of seconds remaining until the next TOTP change.
The return value will be an integer between 0 and 29, inclusive.  

</pre></function>
## <a id="parsing" href="#index_parsing">Parsing</a>
* <function><a id="parsebool"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseBool</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Attempts to parse the provided string as a boolean value.  
***text***: The string representation of a boolean value.  
**Returns**: A boolean value that represents the parsed result from the input text.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string cannot be parsed into a boolean value.
The exception message includes the invalid input string for clarity.  

</pre></function>
* <function><a id="parsesbyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseSByte</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">sbyte</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the given string into an sbyte value. Throws a FormatException if parsing fails.  
***text***: The string representation of a number to parse.  
**Returns**: The parsed sbyte value.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input cannot be converted to an sbyte, indicating that
the format is invalid for parsing into the specified range.  

</pre></function>
* <function><a id="parsebyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseByte</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">byte</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the specified string into a byte using invariant culture and integer number styles.
If parsing fails, a FormatException is thrown.  
***text***: The input string to parse.  
**Returns**: The parsed byte value.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the format of the string is invalid or if it does not represent a valid byte value.  

</pre></function>
* <function><a id="parseint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseInt16</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">short</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the specified text into a 16\-bit signed integer (Int16).  
***text***: The string representation of the number to parse.  
**Returns**: A short value parsed from the input text.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input cannot be parsed as Int16, indicating that
the format is not valid for an Int16 within the range of 
short.MinValue..short.MaxValue.  

</pre></function>
* <function><a id="parseuint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUInt16</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">ushort</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the given string representation of a number into an unsigned 16\-bit integer (UInt16).  
***text***: The string that contains the number to be parsed.  
**Returns**: The UInt16 value that results from parsing the specified string.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the format of the string is invalid or if it falls outside
the range of a UInt16 (0..65535).  

</pre></function>
* <function><a id="parseint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseInt32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a string into an integer (Int32) using invariant culture formatting. 
Throws a FormatException if the parsing is unsuccessful.  
***text***: The text to parse as an Int32.  
**Returns**: The parsed integer value.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string cannot be parsed into a valid Int32.  

</pre></function>
* <function><a id="parseuint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUInt32</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">uint</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a string into an unsigned 32\-bit integer.  
***text***: The string representation of the number to be parsed.  
**Returns**: The parsed unsigned 32\-bit integer value.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string cannot be converted to a valid UInt32 value within the range of uint.MinValue and uint.MaxValue.  

</pre></function>
* <function><a id="parseint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseInt64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">long</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Attempts to parse the provided string into a 64\-bit integer (Int64). If parsing fails, it throws a FormatException.  
***text***: The string representation of a number to be parsed.  
**Returns**: The successfully parsed long value if the conversion succeeds.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string cannot be parsed as an Int64.  

</pre></function>
* <function><a id="parseuint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUInt64</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the specified string representation of a number into its equivalent unsigned 64\-bit integer (ulong).  
***text***: A string containing the number to convert.  
**Returns**: The parsed unsigned 64\-bit integer value.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string does not represent a valid unsigned 64\-bit integer.
The exception message includes the text that could not be parsed and the range of valid values for an unsigned 64\-bit integer.  

</pre></function>
* <function><a id="parsefloat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseFloat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">float</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Attempts to parse the specified string into a single\-precision floating\-point number.  
***text***: The string representation of a number to parse.  
**Returns**: A float value parsed from the given text if successful.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the parsing operation fails, indicating that the input string does not represent a valid single\-precision floating\-point number.  

</pre></function>
* <function><a id="parsedouble"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseDouble</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a string representation of a number into a double value.  
***text***: The string to be parsed.  
**Returns**: The parsed double value if successful.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string cannot be parsed as a valid double.  

</pre></function>
* <function><a id="parsedecimal"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseDecimal</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">decimal</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Attempts to parse a string into a decimal number using invariant culture and specific number styles.
If parsing is unsuccessful, it throws a FormatException with a message indicating the failure.  
***text***: The string representation of a decimal number to be parsed.  
**Returns**: The parsed decimal value if successful.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string cannot be converted to a decimal using the specified parsing settings.
The exception message includes the input text that failed to parse.  

</pre></function>
* <function><a id="parsetimespan"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseTimeSpan</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">TimeSpan</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the specified string and converts it into a TimeSpan object using invariant culture settings.  
***text***: The string representation of time duration to parse.  
**Returns**: A TimeSpan representing the parsed time duration.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the format of the specified string is invalid or it does not represent a valid TimeSpan.  

</pre></function>
* <function><a id="parsedatetimeoffset"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseDateTimeOffset</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a string into a DateTimeOffset object using the specified culture (InvariantCulture).
Throws a FormatException if parsing fails.  
***text***: The string representation of the date and time offset.  
**Returns**: A DateTimeOffset object parsed from the input string.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string cannot be parsed as a DateTimeOffset.  

</pre></function>
* <function><a id="parseipaddress"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseIPAddress</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">IPAddress</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a string representation of an IP address into an IPAddress object.  
***text***: The string containing the IP address.  
**Returns**: An IPAddress object representing the parsed IP address.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input text cannot be parsed as a valid IP address.
The exception message will specify the input string that failed to parse.  

</pre></function>
* <function><a id="parseguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseGuid</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">Guid</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Attempts to parse the specified string into a GUID (Globally Unique Identifier).  
***text***: The string representation of a GUID to be parsed.  
**Returns**: A GUID that matches the text if parsing succeeds.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the input string does not represent a valid GUID.  

</pre></function>
* <function><a id="parsesemver"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseSemVer</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> version) -> <span style="color:#87AF00">SemVer</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a given string into a Semantic Version (SemVer) object.
This method uses a regular expression to validate and extract version components: major, minor, and patch.  
***version***: The semantic version string to be parsed.  
**Returns**: A SemVer object containing the major, minor, and patch numbers extracted from the input string.  
**Exceptions**:
**Type**: FormatException
**Description**: Thrown when the provided version string does not match the semantic version format,
or if any of the numeric components (major, minor, patch) cannot be parsed as integers.  

</pre></function>
## <a id="password" href="#index_password">Password</a>
* <function><a id="hashpassword"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">HashPassword</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> iterations = <span style="color:#5FAFAF; margin-right:1px">150000</span>, <span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset?</span> expiresAt = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Hashes the provided password using PBKDF2 with a random salt and specified number of iterations.
Optionally sets an expiration time for the hash.  
***password***: The password to be hashed.
***iterations***: The number of iterations for the key derivation function. Defaults to Iterations constant if not provided.
***expiresAt***: An optional DateTimeOffset representing when the hash expires. If null, sets it to NoExpiration.  
**Returns**: A formatted string containing the iteration count, expiration time (or default), salt, and hashed key.  

</pre></function>
* <function><a id="verifypassword"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">VerifyPassword</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> hash, <span style="color:#87AF00; margin-left:1px; margin-right:1px">DateTimeOffset?</span> now = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Verifies whether a given password matches the provided hash and optionally checks for expiration.  
***password***: The plain text password to verify.
***hash***: The hashed string containing iterations, expiration time, salt, and expected hash.
***now***: Optional parameter representing the current date and time. Defaults to current UTC time if not provided.  
**Returns**: True if the password matches the hash and is within the valid expiration period; otherwise, false.  

</pre></function>
* <function><a id="passwordentropybits"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PasswordEntropyBits</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password) -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Calculates the entropy in bits of a given password based on its character set diversity and length.  
***password***: The input password whose entropy is to be calculated.  
**Returns**: The entropy value in bits, representing the unpredictability or randomness of the password.  

</pre></function>
* <function><a id="isstrongpassword"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsStrongPassword</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> minEntropyBits = <span style="color:#5FAFAF; margin-right:1px">80</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified password meets the minimum entropy requirement.  
***password***: The password to evaluate.
***minEntropyBits***: The minimum number of bits of entropy required for a strong password. 
Default is 80 bits.  
**Returns**: True if the password&apos;s entropy meets or exceeds the specified threshold; otherwise, false.  

</pre></function>
## <a id="path" href="#index_path">Path</a>
* <function><a id="pathcombine"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathCombine</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">param string[]</span> parts) -> <span style="color:#87AF00">string</span></function>
* <function><a id="pathchild"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathChild</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> path) -> <span style="color:#87AF00">string</span></function>
* <function><a id="pathparent"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathParent</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> path) -> <span style="color:#87AF00">string</span></function>
* <function><a id="pathparts"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathParts</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> path) -> <span style="color:#87AF00">string[]</span></function>
* <function><a id="pathid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">PathId</span>() -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">Id</span>)</function>
## <a id="print" href="#index_print">Print</a>
* <function><a id="print"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Print</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> message) -> <span style="color:#87AF00">void</span> -- (alias <span style="color:#D75F00">Echo</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Prints the specified message to both the console and debug output.  
***message***: The message to print.  

</pre></function>
## <a id="random" href="#index_random">Random</a>
* <function><a id="randombool"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomBool</span>() -> <span style="color:#5FAFAF">bool</span></function>
* <function><a id="randomint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomInt64</span>() -> <span style="color:#5FAFAF">long</span></function>
* <function><a id="randomuint64"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomUInt64</span>() -> <span style="color:#5FAFAF">ulong</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a random unsigned 64\-bit integer using the underlying random number generator.
This function is marked as a plugin function and can be used to obtain random values for various purposes.  
**Returns**: A randomly generated 64\-bit unsigned integer.  

</pre></function>
* <function><a id="randomint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomInt32</span>() -> <span style="color:#5FAFAF">int</span></function>
* <function><a id="randomuint32"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomUInt32</span>() -> <span style="color:#5FAFAF">uint</span></function>
* <function><a id="randomint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomInt16</span>() -> <span style="color:#5FAFAF">short</span></function>
* <function><a id="randomuint16"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomUInt16</span>() -> <span style="color:#5FAFAF">ushort</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates and returns a random 16\-bit unsigned integer.  
**Returns**: A random ushort value.  

</pre></function>
* <function><a id="randomsbyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomSByte</span>() -> <span style="color:#5FAFAF">sbyte</span></function>
* <function><a id="randombyte"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomByte</span>() -> <span style="color:#5FAFAF">byte</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a random byte using the underlying random number generator.  

</pre></function>
* <function><a id="randomfloat"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomFloat</span>() -> <span style="color:#5FAFAF">float</span></function>
* <function><a id="randomdouble"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomDouble</span>() -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates and returns a random double value using the underlying random number generator.  
**Returns**: A randomly generated double value.  

</pre></function>
* <function><a id="randomdecimal"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomDecimal</span>() -> <span style="color:#87AF00">decimal</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a random decimal number using a predefined random number generator.  
**Returns**: A randomly generated decimal value. The characteristics of the randomness depend on the implementation within rng.Decimal().  

</pre></function>
* <function><a id="randomstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomString</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a random string of the specified length using a predefined random number generator.  
***length***: The desired length of the generated random string.  
**Returns**: A randomly generated string with the given length. The content and characteristics of the randomness depend on the implementation within rng.String(length).  

</pre></function>
* <function><a id="randombytes"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomBytes</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> count) -> <span style="color:#87AF00">byte[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates an array of random bytes with the specified length.  
***count***: The number of random bytes to generate.  
**Returns**: An array containing &apos;count&apos; randomly generated bytes.  

</pre></function>
* <function><a id="randomdatetime"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomDateTime</span>() -> <span style="color:#87AF00">DateTimeOffset</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates and returns a random DateTimeOffset with the current date and 
time offset set to zero. The function utilizes a pseudo\-random number generator 
to produce a random long value representing seconds since Unix epoch (1970\-01\-01T00:00:00Z).
This ensures that the returned DateTimeOffset is within plausible historical bounds.  
**Returns**: A random DateTimeOffset with an offset of zero.  

</pre></function>
## <a id="really-simple-syndication-rss" href="#index_really-simple-syndication-rss">Really Simple Syndication (RSS)</a>
* <function><a id="fetchrss"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FetchRSS</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> url) -> <span style="color:#87AF00">Task\<Feed\></span></function>
## <a id="regex" href="#index_regex">Regex</a>
* <function><a id="regexismatch"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RegexIsMatch</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> pattern, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines if the specified input string matches a given regular expression pattern.  
***pattern***: The regular expression pattern to match against.
***input***: The input string to test for a match.  
**Returns**: True if the input string matches the pattern; otherwise, false.  

</pre></function>
* <function><a id="regexmatch"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RegexMatch</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> pattern, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">Match</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Finds the first match for a regular expression within a given input string.  
***pattern***: The regex pattern to be matched against the input string.
***input***: The input string in which to search for matches.  
**Returns**: A Match object representing the first successful match of the pattern in the input, or an empty match if no patterns were found.  

</pre></function>
* <function><a id="regexmatches"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RegexMatches</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> pattern, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">Match[]</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves an array of matches based on a regular expression pattern applied to the input string.  
***pattern***: The regex pattern used for matching.
***input***: The input string where the search is performed.  
**Returns**: An array containing all matches found in the input string according to the specified pattern.  

</pre></function>
## <a id="roman-numerals" href="#index_roman-numerals">Roman Numerals</a>
* <function><a id="toromannumeral"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToRomanNumeral</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> number) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts an integer to its corresponding Roman numeral representation.
This function does not support negative numbers and returns &quot;N&quot; for zero.  
***number***: The integer value to convert.  
**Returns**: A string representing the Roman numeral equivalent of the input number.  
**Exceptions**:
**Type**: ArgumentOutOfRangeException
**Description**: Thrown when a negative number is provided, as Roman numerals do not support negatives.  

</pre></function>
* <function><a id="fromromannumeral"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromRomanNumeral</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> roman) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a Roman numeral string to its corresponding integer value.  
***roman***: The Roman numeral string to convert. The input should be in uppercase and 
can optionally contain whitespace which will be ignored.  
**Returns**: The integer representation of the given Roman numeral.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown when the input Roman numeral string is empty or contains only whitespace.  
**Type**: FormatException
**Description**: Thrown when the input contains invalid characters that do not 
correspond to any Roman numeral symbols in SymbolMap.  

</pre></function>
## <a id="secure-string" href="#index_secure-string">Secure String</a>
* <function><a id="tosecurestring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToSecureString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Encrypts the specified input string using AES encryption and returns a secure string.
The method throws an exception if the input is null. It performs AES encryption with 
a 256\-bit key size, CBC mode, and PKCS7 padding. An HMAC\-SHA256 is computed over the IV 
concatenated with the cipher text to ensure integrity, and the final payload includes the
IV, cipher text, and MAC. Sensitive data buffers are cleared after use.  
***input***: The input string to be encrypted.  
**Returns**: A Base64 encoded string representing the encrypted data including the IV, 
cipher text, and HMAC\-SHA256 MAC.  
**Remarks**:
Set custom secret via ENV &apos;SECURE\_SECRET&apos;  

</pre></function>
* <function><a id="fromsecurestring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FromSecureString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> encrypted) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a Base64 encoded string that represents an encrypted and HMAC\-protected payload into its plaintext form.
This method performs decryption using AES with CBC mode and verifies the integrity of the data using HMAC\-SHA256.  
***encrypted***: The Base64 encoded string containing the encrypted data, initialization vector (IV), 
and message authentication code (MAC). The input must not be null.  
**Returns**: A string representing the decrypted plaintext content.  
**Exceptions**:
**Type**: ArgumentNullException
**Description**: Thrown when the input parameter &apos;encrypted&apos; is null.  
**Type**: FormatException
**Description**: Thrown if the payload format is invalid or does not meet expected length requirements.  
**Type**: CryptographicException
**Description**: Thrown when the MAC verification fails, indicating potential data tampering.  

</pre></function>
## <a id="string" href="#index_string">String</a>
* <function><a id="reverse"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Reverse</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> text) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Reverses the order of characters in a given input string using an efficient method.
This function leverages the Span&lt;T&gt; and String.Create to perform the reversal operation 
in place, minimizing allocations and enhancing performance.  
***text***: The string whose characters are to be reversed.  
**Returns**: A new string with its characters in reverse order compared to the input.  

</pre></function>
* <function><a id="repeatstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RepeatString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> times) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Repeats the given input string a specified number of times.  
***input***: The string to be repeated.
***times***: The number of times to repeat the string. Must be non\-negative.  
**Returns**: A new string consisting of the input string repeated &apos;times&apos; times concatenated together. If &apos;times&apos; is zero, an empty string is returned.  

</pre></function>
* <function><a id="truncate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Truncate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> suffix = <span style="color:#D70000; margin-right:1px">"…"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Truncates the given input string to a specified length and appends a suffix if truncation occurs.  
***input***: The original string to be truncated.
***length***: The maximum allowed length for the output string. If the input is shorter, it&apos;s returned unchanged.
***suffix***: The string to append at the end if truncation occurs, defaulting to an ellipsis character (…).  
**Returns**: The truncated string with suffix appended if necessary; otherwise, returns the original string.  

</pre></function>
* <function><a id="countwords"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CountWords</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Counts the number of words in the provided input string using a regular expression pattern.  
***input***: The input string from which to count the words.  
**Returns**: The total number of words found in the input string.  

</pre></function>
* <function><a id="randomstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RandomString</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> length, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> allowedChars = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Generates a random string of the specified length using either provided allowed characters or a default character set.  
***length***: The length of the random string to generate. Must be non\-negative.
***allowedChars***: An optional parameter specifying which characters can be used in the generated string. 
If null, a default set of alphanumeric characters is used.  
**Returns**: A randomly generated string of specified length using allowed or default characters.  
**Exceptions**:
**Type**: ArgumentOutOfRangeException
**Description**: Thrown when the specified length is negative.  
**Type**: ArgumentException
**Description**: Thrown when the character set (either provided or default) is empty.  

</pre></function>
* <function><a id="slugify"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Slugify</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> separator = <span style="color:#D70000; margin-right:1px">"-"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Transforms the input string into a URL\-friendly slug format.
Converts all characters to lowercase, replaces non\-alphanumeric 
characters with hyphens, and trims leading/trailing hyphens.  
***input***: The input string to be converted into a slug.  
**Returns**: A URL\-friendly version of the input string as a lowercase string with hyphens.  

</pre></function>
* <function><a id="joinstrings"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">JoinStrings</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">IEnumerable\<string\></span> items, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> delimiter = <span style="color:#D70000; margin-right:1px">","</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Joins a collection of strings into a single string using the specified delimiter.  
***items***: The collection of strings to join.
***delimiter***: A string used to separate each element in the joined string. Defaults to &quot;,&quot; if not provided.  
**Returns**: A single string that is the concatenation of the elements in items, separated by occurrences of delimiter.  

</pre></function>
* <function><a id="splitstring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SplitString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> delimiter = <span style="color:#D70000; margin-right:1px">","</span>) -> <span style="color:#87AF00">List\<string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Splits the input string into a list of substrings based on the specified delimiter.  
***input***: The string to be split.
***delimiter***: The delimiter used to separate the substrings. Defaults to a comma (&quot;,&quot;) if not provided.  
**Returns**: A list containing each substring resulting from the split operation.  

</pre></function>
* <function><a id="removewhitespace"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">RemoveWhitespace</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Removes all whitespace characters from the specified input string.
This function utilizes a regular expression to identify and eliminate all forms of 
whitespace, including spaces, tabs, and newlines. The result is returned as a single,
contiguous string without any whitespace characters.  
***input***: The input string from which whitespace will be removed.  
**Returns**: A new string with all whitespace characters removed.  

</pre></function>
* <function><a id="countoccurrences"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CountOccurrences</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> source, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> substring) -> <span style="color:#5FAFAF">int</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Counts the occurrences of a specified substring within the provided source string.
Utilizes regular expressions to ensure accurate matching. If either input is null or empty, they are treated as empty strings by default.  
***source***: The string in which to search for occurrences.
***substring***: The substring to count within the source string.  
**Returns**: The number of times the specified substring occurs in the source string.  

</pre></function>
* <function><a id="startswithignorecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">StartsWithIgnoreCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> prefix) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified input string begins with a given prefix,
ignoring case differences.  
***input***: The string to test.
***prefix***: The prefix to look for at the start of the input string.  
**Returns**: true if input starts with prefix, ignoring case; otherwise, false.  

</pre></function>
* <function><a id="endswithignorecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">EndsWithIgnoreCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> suffix) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether a specified string ends with the given suffix,
ignoring case. If either the input or the suffix is null, appropriate
handling ensures no exceptions are thrown.  
***input***: The string to be evaluated.
***suffix***: The suffix to compare against.  
**Returns**: True if the input ends with the specified suffix ignoring case; otherwise, false.  

</pre></function>
* <function><a id="containsignorecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ContainsIgnoreCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> source, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> toCheck) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified substring is present in the given string, 
ignoring case sensitivity.  
***source***: The source string to search within.
***toCheck***: The substring to locate in the source string.  
**Returns**: True if the substring is found; otherwise, false. Returns false if either input is null.  

</pre></function>
* <function><a id="isalpha"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsAlpha</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified string contains only alphabetic characters.
Utilizes a regular expression to match the entire input against alphabet\-only patterns. 
If the input is null, it defaults to an empty string before performing the check.  
***input***: The string to evaluate.  
**Returns**: true if the input contains only alphabetic characters; otherwise, false.  

</pre></function>
* <function><a id="isalphanumeric"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsAlphaNumeric</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified string contains only alphanumeric characters.
Uses a predefined regular expression pattern to check if each character in the input 
is either a letter (uppercase or lowercase) or a digit. Returns true if all characters 
match this criteria, otherwise returns false. If the input is null or empty, it defaults 
to an empty string and evaluates accordingly.  
***input***: The string to be evaluated for alphanumeric content.  
**Returns**: True if the string is composed solely of letters and digits; otherwise, false.  

</pre></function>
* <function><a id="islowercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsLowerCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines if a given string is in lowercase.  
***input***: The string to check.  
**Returns**: True if the input string is entirely in lowercase, or null/empty; otherwise, false.  
**Remarks**:
Uses string.ToLowerInvariant to perform case\-insensitive comparison,
ensuring that culture\-specific casing rules do not affect the result.  

</pre></function>
* <function><a id="isuppercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsUpperCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified string is entirely in uppercase.  
***input***: The string to evaluate.  
**Returns**: true if the input is null or an empty string, or if all characters in the input are uppercase; otherwise, false.  

</pre></function>
* <function><a id="tostring"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToString</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">object</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">Str</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the specified object to its string representation. Returns a special 
string for null objects, uses invariant culture formatting for convertible 
objects, and handles tracked dictionaries uniquely by including their Id.  
***input***: The input object to convert to string.  
**Returns**: A string representing the input object, or special representations
for null, tracked dictionaries, and convertible types. Returns null 
if conversion fails for non\-conformant objects.  

</pre></function>
* <function><a id="format"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">Format</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> format, <span style="color:#87AF00; margin-left:1px; margin-right:1px">param object[]</span> args) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Formats the specified string using the provided arguments.  
***format***: The composite format string.
***args***: An array of objects to write using format.  
**Returns**: A formatted string according to the format and args specified.  

</pre></function>
## <a id="string-casing" href="#index_string-casing">String Casing</a>
* <function><a id="tolowercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToLowerCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">LowerCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the specified string to lowercase using culture\-invariant settings.  
***input***: The string to be converted to lowercase. Can be null or empty.  
**Returns**: A new string with all characters converted to lowercase, or the original input if it is null or empty.  

</pre></function>
* <function><a id="touppercase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToUpperCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">UpperCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the specified string to uppercase using the current culture&apos;s TextInfo.  
***input***: The string to be converted to uppercase. If null or empty, returns as is.  
**Returns**: The uppercase representation of the input string, or the original input if it is null or empty.  

</pre></function>
* <function><a id="totitlecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToTitleCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">TitleCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the specified string to title case using invariant culture.
This method ensures that each word in the input string is capitalized,
while maintaining any existing casing for words that should remain unchanged.  
***input***: The string to convert to title case.  
**Returns**: A string with each word converted to title case. If the input is null or empty, returns the original input.  

</pre></function>
* <function><a id="tokebabcase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToKebabCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">KebabCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a given string to Kebab Case format. This involves replacing spaces and underscores with hyphens, converting uppercase letters to lowercase, and ensuring no consecutive hyphens are present. It handles null or empty input gracefully by returning the input as is  
***input***: The string to be converted to Kebab Case.  
**Returns**: A new string formatted in Kebab Case or the original input if it was null or empty.  

</pre></function>
* <function><a id="tocamelcase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToCamelCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">CamelCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a given string to CamelCase format. It transforms the input by 
capitalizing the first letter of each word while removing spaces and other 
whitespace characters, ensuring that only the initial character of the entire 
string is in lowercase unless it was originally uppercase.  
***input***: The string to convert to CamelCase.  
**Returns**: A new string in CamelCase format derived from the input. Returns 
the original string if it is null or empty.  

</pre></function>
* <function><a id="tosnakecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToSnakeCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">SnakeCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the provided input string from PascalCase or CamelCase to snake\_case.
The conversion involves replacing uppercase letters with underscores followed by their lowercase equivalents. 
Consecutive underscores are reduced to a single underscore, and any leading/trailing underscores are removed.  
***input***: The input string to convert.  
**Returns**: A new string in snake\_case format or the original input if it is null or empty.  

</pre></function>
* <function><a id="tosentencecase"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ToSentenceCase</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#87AF00">string</span> -- (alias <span style="color:#D75F00">SentenceCase</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts the first character of a given string to uppercase while converting all other characters in the string to lowercase.
If the input is null or empty, it returns the input unchanged.  
***input***: The string to be converted to sentence case.  
**Returns**: A new string with the first character capitalized and remaining characters in lowercase, or the original input if it&apos;s null or empty.  

</pre></function>
## <a id="system" href="#index_system">System</a>
* <function><a id="systemthrottlercallspersecond"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">System_ThrottlerCallsPerSecond</span>() -> <span style="color:#5FAFAF">double</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves the number of allowed calls per second for the current throttler.  
**Returns**: The calls per second limit set by the Throttler. Returns double.MaxValue if no Throttler is present.  

</pre></function>
* <function><a id="systemisinmemory"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">System_IsInMemory</span>() -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the system is operating in memory mode.  
**Returns**: A boolean value indicating if the store configuration specifies an in\-memory mode.  

</pre></function>
* <function><a id="systemcompact"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_Compact</span>() -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Initiates a compaction process on the data store associated with the given loader context.
This operation reduces storage space and improves efficiency by optimizing stored data.  

</pre></function>
* <function><a id="systemimportfromfile"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_ImportFromFile</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> filepath) -> <span style="color:#87AF00">DataChangeType</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Imports data from a specified JSON file and applies import options through the given context.  
***filepath***: The path to the JSON file that should be imported.  
**Returns**: A DataChangeType indicating the result of the import operation.  

</pre></function>
* <function><a id="systemexporttofile"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_ExportToFile</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> filepath, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> indent = <span style="color:#5FAFAF; margin-right:1px">false</span>) -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Exports the data from the provided LoaderContextData store to a specified file.  
***filepath***: The path of the file where the data should be exported.
***indent***: A boolean value indicating whether the exported data should be formatted with indentation.
Default is false, which results in no indentation.  

</pre></function>
* <function><a id="systemshutdowm"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_Shutdowm</span>() -> <span style="color:#87AF00">void</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Initiates the shutdown process for the system by cancelling the 
ongoing operations linked to a specific shutdown token source. This 
function is protected and should be executed within contexts where
it&apos;s safe to invoke system\-level shutdown procedures.  

</pre></function>
* <function><a id="systeminfo"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">System_Info</span>() -> <span style="color:#87AF00">SystemInfo</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Retrieves system information including runtime statistics, memory usage,
disk status, and environment details. The method calculates CPU usage percentage
based on the current process&apos;s processor time relative to uptime, checks for degraded 
performance conditions (e.g., high CPU or memory usage), and gathers comprehensive 
data about the system&apos;s runtime environment, memory utilization, and available disk space.  
**Returns**: A SystemInfo object containing detailed information
about the current state of the system including uptime, CPU load, memory allocation,
garbage collection metrics, disk drive details, and environmental settings such as OS 
architecture and processor count.  

</pre></function>
## <a id="temperature" href="#index_temperature">Temperature</a>
* <function><a id="fahrenheittocelsius"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FahrenheitToCelsius</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> f) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">FtoC</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a temperature from Fahrenheit to Celsius.  
***f***: The temperature in Fahrenheit.  
**Returns**: The equivalent temperature in Celsius.  

</pre></function>
* <function><a id="fahrenheittokelvin"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FahrenheitToKelvin</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> f) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">FtoK</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a temperature from Fahrenheit to Kelvin.  
***f***: The temperature in degrees Fahrenheit.  
**Returns**: The equivalent temperature in Kelvin.  

</pre></function>
* <function><a id="celsiustokelvin"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CelsiusToKelvin</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> c) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">CtoK</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a temperature value from Celsius to Kelvin.  
***c***: The temperature in degrees Celsius.  
**Returns**: The equivalent temperature in Kelvin.  

</pre></function>
* <function><a id="celsiustofahrenheit"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CelsiusToFahrenheit</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> c) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">CtoF</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a temperature value from Celsius to Fahrenheit.  
***c***: The temperature in degrees Celsius.  
**Returns**: The equivalent temperature in degrees Fahrenheit.  

</pre></function>
* <function><a id="kelvintocelsius"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">KelvinToCelsius</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> k) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">KtoC</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a temperature from Kelvin to Celsius.  
***k***: The temperature in Kelvin.  
**Returns**: The equivalent temperature in Celsius.  

</pre></function>
* <function><a id="kelvintofahrenheit"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">KelvinToFahrenheit</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> k) -> <span style="color:#5FAFAF">double</span> -- (alias <span style="color:#D75F00">KtoF</span>)<pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Converts a temperature from Kelvin to Fahrenheit.  
***k***: The temperature in Kelvin.  
**Returns**: The equivalent temperature in Fahrenheit.  

</pre></function>
## <a id="templating" href="#index_templating">Templating</a>
* <function><a id="smartformat"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">SmartFormat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> format, <span style="color:#87AF00; margin-left:1px; margin-right:1px">param object[]</span> args) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Formats the input string using smart formatting with extended capabilities. This function leverages a custom formatter that can be influenced by context data passed as a parameter. The formatted output adheres to culture\-invariant rules.  
***format***: The format string specifying how the arguments should be formatted and combined.
***args***: An array of objects containing the data to format according to the specified format string.  
**Returns**: A string resulting from applying smart formatting rules to the input data, using culture\-invariant formatting conventions.  

</pre></function>
* <function><a id="scribanformat"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">ScribanFormat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> templateText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> model = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Formats a provided template text using the Scriban templating engine, optionally applying a model as context data.
Incorporates custom methods from the loader context into the rendering process if available.
Throws an InvalidOperationException if the parsed template contains errors.  
***templateText***: The template text to be formatted using Scriban.
***model***: An optional dictionary of string keys and object values representing the model data for rendering. Defaults to null if not provided.  
**Returns**: A string result of the rendered template after applying the given model data or default contexts.  

</pre></function>
* <function><a id="handlebarsformat"></a><b>function</b> <span style="color:#AF5F5F">[may modify] </span><span style="color:#D75F00; margin-right: 2px">HandlebarsFormat</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> templateText, <span style="color:#87AF00; margin-left:1px; margin-right:1px">IDictionary\<string, object\></span> model = <span style="color:#87AF00; margin-right:1px">null</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Formats a given text using Handlebars syntax with an optional model for data binding.
The function creates a Handlebars instance and configures it to use custom compile\-time features,
then compiles the template and renders it with the provided model (or an empty dictionary if none is supplied).  
***templateText***: The text of the Handlebars template to be compiled and rendered.
***model***: An optional dictionary representing the model that provides values for the placeholders in the template.  
**Returns**: A formatted string resulting from rendering the Handlebars template with the provided model.  

</pre></function>
## <a id="uniform-resource-locator-url" href="#index_uniform-resource-locator-url">Uniform Resource Locator (URL)</a>
* <function><a id="parseuriquery"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUriQuery</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> uri) -> <span style="color:#87AF00">Dictionary\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the query parameters from a given URI and returns them as a dictionary.  
***uri***: The absolute URI containing query parameters to parse.  
**Returns**: A dictionary where each key is a parameter name and each value is the corresponding parameter value. 
If a parameter has no value, its entry in the dictionary will have an empty string as the value.  

</pre></function>
* <function><a id="parseuriparts"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUriParts</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> uriString) -> <span style="color:#87AF00">Dictionary\<string, object\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses the given URI string into its components and returns them as a dictionary.  
***uriString***: The URI string to be parsed.  
**Returns**: A dictionary containing the components of the URI such as scheme, host, port, path,
query, fragment, user info, absolute URI, segments, and whether it is an absolute URI. 
If the input is a relative URI, only the original string is treated as the path.  
**Exceptions**:
**Type**: ArgumentException
**Description**: Thrown if the provided URI string format is invalid or
if an unexpected error occurs during parsing.  

</pre></function>
## <a id="user-agent-ua" href="#index_user-agent-ua">User agent (UA)</a>
* <function><a id="parseuseragent"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseUserAgent</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> userAgent) -> <span style="color:#87AF00">UserAgent</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses a user agent string to extract information about the browser or device.  
***userAgent***: The user agent string to be parsed.  
**Returns**: A UserAgent object containing the name, version, and optionally platform type and name.  
**Exceptions**:
**Type**: InvalidDataException
**Description**: Thrown when the provided user agent string cannot be parsed and results in an unknown type with no identifiable information.  

</pre></function>
## <a id="validation" href="#index_validation">Validation</a>
* <function><a id="isvalidemail"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsValidEmail</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> address) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Validates whether a given email address string is valid.  
***address***: The email address to validate.  
**Returns**: True if the email address is valid and not null; otherwise, false.  

</pre></function>
* <function><a id="isvalidphonenumber"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsValidPhoneNumber</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> number, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> defaultRegion = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines if the provided phone number is valid based on regional formatting rules.  
***number***: The phone number to be validated. If null, returns false.
***defaultRegion***: Optional region code used when no region is specified in the phone number; can also be null.  
**Returns**: True if the phone number is valid according to regional rules, otherwise false.  

</pre></function>
* <function><a id="iscreditcardinfovalid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsCreditCardInfoValid</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cardNo, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> expiryDate = <span style="color:#D70000; margin-right:1px">null</span>, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> cvv = <span style="color:#D70000; margin-right:1px">null</span>) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines if the credit card information provided is valid.
Validates the credit card number, CVV, and expiry date according to specified patterns and conditions.  
***cardNo***: The credit card number as a string.
***expiryDate***: Optional. The expiry date of the credit card in &quot;MM/yyyy&quot; format.
***cvv***: Optional. The CVV code of the credit card.  
**Returns**: True if all provided credit card information is valid; otherwise, false.  

</pre></function>
* <function><a id="validatejson"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ValidateJson</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> json, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> schema) -> <span style="color:#87AF00">Task\<bool\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Validates a JSON string against the provided JSON Schema.  
***json***: The JSON string to validate.
***schema***: The JSON schema in string format used for validation.  
**Returns**: A task that represents the asynchronous operation. The task result contains a boolean indicating whether the JSON is valid against the schema (true if valid, false otherwise).  

</pre></function>
* <function><a id="isurl"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsUrl</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Checks if the provided string is a valid absolute URL.  
***input***: The string to be checked as a potential URL.  
**Returns**: True if the input is a valid absolute URL, otherwise false.  

</pre></function>
* <function><a id="isnumeric"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsNumeric</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified string can be parsed as a numeric value.
Utilizes the double.TryParse method to check if the conversion is successful.  
***input***: The input string to evaluate for its numeric nature.  
**Returns**: true if the string represents a valid double; otherwise, false.  

</pre></function>
* <function><a id="isguid"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">IsGuid</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> input) -> <span style="color:#5FAFAF">bool</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Determines whether the specified string is a valid GUID.  
***input***: The string to check for being a valid GUID.  
**Returns**: True if the input string represents a valid GUID; otherwise, false.  

</pre></function>
## <a id="weather" href="#index_weather">Weather</a>
* <function><a id="fetchweather"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">FetchWeather</span>(<span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lat, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">double</span> lon, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> openweathermapApiKey) -> <span style="color:#87AF00">Task\<Dictionary\<string, object\>\></span></function>
## <a id="wifi" href="#index_wifi">Wifi</a>
* <function><a id="wificode"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">WifiCode</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> ssid, <span style="color:#87AF00; margin-left:1px; margin-right:1px">WifiAuth</span> auth, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password = <span style="color:#D70000; margin-right:1px">null</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> hidden = <span style="color:#5FAFAF; margin-right:1px">false</span>) -> <span style="color:#87AF00">string</span></function>
* <function><a id="wificodeeap"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">WifiCode_EAP</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> ssid, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> identity, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> password, <span style="color:#87AF00; margin-left:1px; margin-right:1px">WifiEapMethod</span> eap, <span style="color:#87AF00; margin-left:1px; margin-right:1px">WifiPhase2</span> phase2 = <span style="color:#87AF00; margin-right:1px">Krynetic.Database.Plugins.WifiPlugin+WifiPhase2.MSCHAPV2</span>, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> anonymousIdentity = <span style="color:#D70000; margin-right:1px">null</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">bool</span> hidden = <span style="color:#5FAFAF; margin-right:1px">false</span>) -> <span style="color:#87AF00">string</span></function>
## <a id="x509certificates" href="#index_x509certificates">X509Certificates</a>
* <function><a id="parsex509"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">ParseX509</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> certPemString) -> <span style="color:#87AF00">Certificate</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Parses an X.509 certificate from a PEM\-formatted string and creates a Certificate object containing detailed information about the certificate.  
***certPemString***: The PEM\-encoded certificate as a string.  
**Returns**: A Certificate object with properties such as thumbprint, serial number, validity period, issuer, subject  

</pre></function>
* <function><a id="createselfsignedcertificate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CreateSelfSignedCertificate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> subject, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySize = <span style="color:#5FAFAF; margin-right:1px">2048</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> validDays = <span style="color:#5FAFAF; margin-right:1px">365</span>, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> hashAlg = <span style="color:#D70000; margin-right:1px">"SHA256"</span>) -> <span style="color:#87AF00">string</span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Creates a self\-signed X.509 certificate with the specified subject name, RSA key size,
validity period in days, and hash algorithm.  
***subject***: The subject name of the certificate.
***keySize***: The size of the RSA key, default is 2048 bits.
***validDays***: The number of days for which the certificate is valid. Default is 365 days.
***hashAlg***: The hash algorithm to use, default is &quot;SHA256&quot;.  
**Returns**: A PEM formatted string containing both the certificate and private key  

</pre></function>
* <function><a id="createcertificateauthority"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CreateCertificateAuthority</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> subject, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySize = <span style="color:#5FAFAF; margin-right:1px">4096</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> validDays = <span style="color:#5FAFAF; margin-right:1px">3650</span>) -> <span style="color:#87AF00">ValueTuple\<string, string\></span><pre style="color:#009700; background-color:#051012; margin-bottom:0px; margin-top:6px; padding:8px 12px 10px 12px; white-space:pre-wrap;">
**Summary**: Creates a self\-signed Certificate Authority (CA) with specified subject name, RSA key size, and validity period.  
***subject***: The subject name for the X.500 distinguished name of the certificate authority in a string format.
***keySize***: Optional parameter specifying the size of the RSA key to be generated. Defaults to 4096 bits if not provided.
***validDays***: Optional parameter indicating the number of days for which the certificate is valid. Defaults to 3650 days if not provided.  
**Returns**: A tuple containing two strings:
\- CertPem: The PEM\-encoded representation of the self\-signed certificate.
\- KeyPem: The PEM\-encoded representation of the self\-signed certificate.  

</pre></function>
* <function><a id="signcertificate"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">SignCertificate</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> subject, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> issuerCertPem, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> issuerKeyPem, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> keySize = <span style="color:#5FAFAF; margin-right:1px">2048</span>, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> validDays = <span style="color:#5FAFAF; margin-right:1px">365</span>) -> <span style="color:#87AF00">string</span></function>
* <function><a id="createcertificatechain"></a><b>function</b> <span style="color:#87AF00">[pure] </span><span style="color:#D75F00; margin-right: 2px">CreateCertificateChain</span>(<span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> leafSubject, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> caCertPem, <span style="color:#87AF00; margin-left:1px; margin-right:1px">string</span> caKeyPem, <span style="color:#5FAFAF; margin-left:1px; margin-right:1px">int</span> validDays = <span style="color:#5FAFAF; margin-right:1px">365</span>) -> <span style="color:#87AF00">string</span></function>
