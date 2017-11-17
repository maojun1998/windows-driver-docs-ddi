---
UID: NS.ndis._IPSEC_OFFLOAD_V2_ALGORITHM_INFO
title: IPSEC_OFFLOAD_V2_ALGORITHM_INFO
author: windows-driver-content
description: The IPSEC_OFFLOAD_V2_ALGORITHM_INFO structure specifies an algorithm that is used for a security association (SA).
old-location: netvista\ipsec_offload_v2_algorithm_info.htm
ms.assetid: 787e5a98-ba77-42d4-8624-abcc02fccf53
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPSEC_OFFLOAD_V2_ALGORITHM_INFO
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
ms.keywords: IPSEC_OFFLOAD_V2_ALGORITHM_INFO, IPSEC_OFFLOAD_V2_ALGORITHM_INFO, *PIPSEC_OFFLOAD_V2_ALGORITHM_INFO
req.iface: 
---

# IPSEC_OFFLOAD_V2_ALGORITHM_INFO structure



## -description
<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]</p>
<p>The IPSEC_OFFLOAD_V2_ALGORITHM_INFO structure specifies an algorithm that is used for a security
  association (SA).</p>


## -syntax

````
typedef struct _IPSEC_OFFLOAD_V2_ALGORITHM_INFO {
  ULONG Identifier;
  ULONG KeyLength;
  ULONG KeyOffsetBytes;
  ULONG AdditionalInfo;
} IPSEC_OFFLOAD_V2_ALGORITHM_INFO, *PIPSEC_OFFLOAD_V2_ALGORITHM_INFO;
````


## -struct-fields
<dl>

### -field <b>Identifier</b>

<dd>
<p>The encryption or authentication algorithm that is used for the SA. 
     </p>
<p>If the algorithm is an encryption algorithm, 
     <b>Identifier</b> can be any of the following values:</p>
<p></p>
<dl>

### -field <a id="IPSEC_OFFLOAD_V2_ENCRYPTION_NONE"></a><a id="ipsec_offload_v2_encryption_none"></a>IPSEC_OFFLOAD_V2_ENCRYPTION_NONE

<dd>
<p>Specifies no confidentiality algorithm. This value is used for null encryption--that is, when a
       packet is not encrypted but does include ESP authentication information.</p>
</dd>

### -field <a id="IPSEC_OFFLOAD_V2_ENCRYPTION_DES_CBC"></a><a id="ipsec_offload_v2_encryption_des_cbc"></a>IPSEC_OFFLOAD_V2_ENCRYPTION_DES_CBC

<dd>
<p>Specifies the DES algorithm for encrypting and decrypting ESP payloads.</p>
</dd>

### -field <a id="IPSEC_OFFLOAD_V2_ENCRYPTION_3_DES_CBC"></a><a id="ipsec_offload_v2_encryption_3_des_cbc"></a>IPSEC_OFFLOAD_V2_ENCRYPTION_3_DES_CBC

<dd>
<p>Specifies the triple-DES algorithm for encrypting and decrypting ESP payloads.</p>
</dd>

### -field <a id="IPSEC_OFFLOAD_V2_ENCRYPTION_AES_GCM_128"></a><a id="ipsec_offload_v2_encryption_aes_gcm_128"></a>IPSEC_OFFLOAD_V2_ENCRYPTION_AES_GCM_128

<dd>
<p>Specifies the AES-GCM 128 algorithm for encrypting and computing a cryptographic checksum or
       decrypting and validating a cryptographic checksum for an ESP payload. Note that this is a combined
       mode algorithm.</p>
</dd>

### -field <a id="IPSEC_OFFLOAD_V2_ENCRYPTION_AES_GCM_192"></a><a id="ipsec_offload_v2_encryption_aes_gcm_192"></a>IPSEC_OFFLOAD_V2_ENCRYPTION_AES_GCM_192

<dd>
<p>Specifies the AES-GCM 192 algorithm for encrypting and computing a cryptographic checksum or
       decrypting and validating a cryptographic checksum for an ESP payload. Note that this is a combined
       mode algorithm.</p>
</dd>

### -field <a id="IPSEC_OFFLOAD_V2_ENCRYPTION_AES_GCM_256"></a><a id="ipsec_offload_v2_encryption_aes_gcm_256"></a>IPSEC_OFFLOAD_V2_ENCRYPTION_AES_GCM_256

<dd>
<p>Specifies the AES-GCM 256 algorithm for encrypting and computing a cryptographic checksum or
       decrypting and validating a cryptographic checksum for an ESP payload. Note that this is a combined
       mode algorithm.</p>
</dd>

### -field <a id="IPSEC_OFFLOAD_V2_ENCRYPTION_AES_CBC_128"></a><a id="ipsec_offload_v2_encryption_aes_cbc_128"></a>IPSEC_OFFLOAD_V2_ENCRYPTION_AES_CBC_128

<dd>
<p>Specifies the Advanced Encryption Standard - cipher-block chaining mode (AES-CBC) 128 algorithm
       for encrypting and decrypting ESP payloads.</p>
</dd>

### -field <a id="IPSEC_OFFLOAD_V2_ENCRYPTION_AES_CBC_192"></a><a id="ipsec_offload_v2_encryption_aes_cbc_192"></a>IPSEC_OFFLOAD_V2_ENCRYPTION_AES_CBC_192

<dd>
<p>Specifies the AES-CBC 192 algorithm for encrypting and decrypting ESP payloads.</p>
</dd>

### -field <a id="IPSEC_OFFLOAD_V2_ENCRYPTION_AES_CBC_256"></a><a id="ipsec_offload_v2_encryption_aes_cbc_256"></a>IPSEC_OFFLOAD_V2_ENCRYPTION_AES_CBC_256

<dd>
<p>Specifies the AES-CBC 256 algorithm for encrypting and decrypting ESP payloads.</p>
</dd>
</dl>
<p>If the algorithm is an authentication algorithm, 
     <b>Identifier</b> can be one of the following values:</p>
<p></p>
<dl>

### -field <a id="IPSEC_OFFLOAD_V2_AUTHENTICATION_MD5"></a><a id="ipsec_offload_v2_authentication_md5"></a>IPSEC_OFFLOAD_V2_AUTHENTICATION_MD5

<dd>
<p>Specifies the keyed message digest 5 (MD5) algorithm for computing or validating a cryptographic
       checksum.</p>
</dd>

### -field <a id="IPSEC_OFFLOAD_V2_AUTHENTICATION_SHA_1"></a><a id="ipsec_offload_v2_authentication_sha_1"></a>IPSEC_OFFLOAD_V2_AUTHENTICATION_SHA_1

<dd>
<p>Specifies the secure hash algorithm (SHA) 1 algorithm for computing or validating a
       cryptographic checksum.</p>
</dd>

### -field <a id="IPSEC_OFFLOAD_V2_AUTHENTICATION_SHA_256"></a><a id="ipsec_offload_v2_authentication_sha_256"></a>IPSEC_OFFLOAD_V2_AUTHENTICATION_SHA_256

<dd>
<p>Specifies the SHA 256 algorithm for computing or validating a cryptographic checksum.</p>
</dd>

### -field <a id="IPSEC_OFFLOAD_V2_AUTHENTICATION_AES_GCM_128"></a><a id="ipsec_offload_v2_authentication_aes_gcm_128"></a>IPSEC_OFFLOAD_V2_AUTHENTICATION_AES_GCM_128

<dd>
<p>Specifies the Advanced Encryption Standard - Galois/Counter Mode (AES- GMAC) 128 algorithm for
       computing or validating a cryptographic checksum.</p>
</dd>

### -field <a id="IPSEC_OFFLOAD_V2_AUTHENTICATION_AES_GCM_192"></a><a id="ipsec_offload_v2_authentication_aes_gcm_192"></a>IPSEC_OFFLOAD_V2_AUTHENTICATION_AES_GCM_192

<dd>
<p>Specifies the AES- GMAC 192 algorithm for computing or validating a cryptographic
       checksum.</p>
</dd>

### -field <a id="IPSEC_OFFLOAD_V2_AUTHENTICATION_AES_GCM_256"></a><a id="ipsec_offload_v2_authentication_aes_gcm_256"></a>IPSEC_OFFLOAD_V2_AUTHENTICATION_AES_GCM_256

<dd>
<p>Specifies the AES- GMAC 256 algorithm for computing or validating a cryptographic
       checksum.</p>
</dd>
</dl>
</dd>

### -field <b>KeyLength</b>

<dd>
<p>The length, in bytes, of the key for the algorithm. The key is contained in the array at the 
     <b>KeyData</b> member in the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff556977">IPSEC_OFFLOAD_V2_ADD_SA</a> structure.
     </p>
<p><b>KeyLength</b> indicates the length of the cryptographic algorithm, starting at the offset that is
     specified in 
     <b>KeyOffsetBytes</b> .</p>
<p>If both algorithms (
     <b>AuthenticationAlgorithm</b> and 
     <b>EncryptionAlgorithm</b> ) are specified in IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION, the keys are
     concatenated. The respective keys start at the offset that is specified in 
     <b>KeyOffsetBytes</b> .</p>
</dd>

### -field <b>KeyOffsetBytes</b>

<dd>
<p>The offset, in bytes, into in the array at the 
     <b>KeyData</b> member in the 
     <a href="https://msdn.microsoft.com/78c5e765-40e5-47f0-8460-a86124fb43d8">
     IPSEC_OFFLOAD_V2_ADD_SA</a> structure.</p>
</dd>

### -field <b>AdditionalInfo</b>

<dd>
<p>Additional information that should be interpreted differently based on the algorithm. For AES-GCM,
     
     <b>AdditionalInfo</b> contains the ICV length.</p>
</dd>
</dl>

## -remarks
<p>The IPSEC_OFFLOAD_V2_ALGORITHM_INFO structure specifies algorithm information in the 
    <b>EncryptionAlgorithm</b> and 
    <b>AuthenticationAlgorithm</b> members of the 
    <a href="https://msdn.microsoft.com/b2c5611e-930d-41a5-a07e-7de8f8584283">
    IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION</a> structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.1 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556977">IPSEC_OFFLOAD_V2_ADD_SA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b2c5611e-930d-41a5-a07e-7de8f8584283">
   IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20IPSEC_OFFLOAD_V2_ALGORITHM_INFO structure%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>