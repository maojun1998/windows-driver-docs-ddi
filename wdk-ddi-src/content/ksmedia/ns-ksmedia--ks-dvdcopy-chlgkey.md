---
UID: NS.ksmedia._KS_DVDCOPY_CHLGKEY
title: KS_DVDCOPY_CHLGKEY
author: windows-driver-content
description: The KS_DVDCOPY_CHLGKEY structure is used to describe the challenge key information for the DVD copyright protection authentication process.
old-location: stream\ks_dvdcopy_chlgkey.htm
ms.assetid: 10be15fc-ca0e-40d4-8fe9-9682478f5c5b
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: stream
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KS_DVDCOPY_CHLGKEY
req.alt-loc: ksmedia.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
ms.keywords: KS_DVDCOPY_CHLGKEY, KS_DVDCOPY_CHLGKEY, *PKS_DVDCOPY_CHLGKEY
req.iface: 
---

# KS_DVDCOPY_CHLGKEY structure



## -description
<p>The KS_DVDCOPY_CHLGKEY structure is used to describe the challenge key information for the DVD copyright protection authentication process.</p>


## -syntax

````
typedef struct _KS_DVDCOPY_CHLGKEY {
  BYTE ChlgKey[10];
  BYTE Reserved[2];
} KS_DVDCOPY_CHLGKEY, *PKS_DVDCOPY_CHLGKEY;
````


## -struct-fields
<dl>

### -field <b>ChlgKey</b>

<dd>
<p>Specifies the DVD decoder minidriver's challenge key.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved. Do not use.</p>
</dd>
</dl>

## -remarks
<p>The KS_DVDCOPY_CHLGKEY structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565140">KSPROPERTY_DVDCOPY_CHLG_KEY</a> property.</p>

<p>For more information, see <a href="NULL">DVD Copyright Protection</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565140">KSPROPERTY_DVDCOPY_CHLG_KEY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DVDCOPY_CHLGKEY structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>