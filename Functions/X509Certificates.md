## X509Certificates
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
