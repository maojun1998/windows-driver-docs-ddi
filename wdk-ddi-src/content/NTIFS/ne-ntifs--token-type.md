---
UID: NE.ntifs._TOKEN_TYPE
title: TOKEN_TYPE
author: windows-driver-content
description: The TOKEN_TYPE enumeration type contains values that differentiate between a primary token and an impersonation token.
old-location: ifsk\token_type.htm
ms.assetid: 2ad78d17-9baa-45cf-a620-01c2ccd14338
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: ifsk
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TOKEN_TYPE
req.alt-loc: ntifs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: VOLUME_READ_PLEX_INPUT, VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
req.iface: 
---

# TOKEN_TYPE enumeration



## -description
<p>The TOKEN_TYPE enumeration type contains values that differentiate between a primary token and an impersonation token. </p>


## -syntax

````
typedef enum _TOKEN_TYPE { 
  TokenPrimary        = 1,
  TokenImpersonation  = 2
} TOKEN_TYPE, *PTOKEN_TYPE;
````


## -enum-fields
<dl>

### -field <a id="TokenPrimary"></a><a id="tokenprimary"></a><a id="TOKENPRIMARY"></a><b>TokenPrimary</b>

<dd>
<p>Indicates a primary token. </p>
</dd>

### -field <a id="TokenImpersonation"></a><a id="tokenimpersonation"></a><a id="TOKENIMPERSONATION"></a><b>TokenImpersonation</b>

<dd>
<p>Indicates an impersonation token. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556838">TOKEN_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556849">TOKEN_STATISTICS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567102">ZwSetInformationToken</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_TYPE enumeration%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>