---
UID: NS.rilapitypes.RILSENDSUPSERVICEDATAPARAMS
title: RILSENDSUPSERVICEDATAPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendsupservicedataparams_2.htm
ms.assetid: de9c7d56-5b57-4809-b5cf-93234c934d55
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILSENDSUPSERVICEDATAPARAMS
req.alt-loc: rilapitypes.h
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
ms.keywords: RILSENDSUPSERVICEDATAPARAMS, RILSENDSUPSERVICEDATAPARAMS
req.iface: 
req.product: Windows 10 or later.
---

# RILSENDSUPSERVICEDATAPARAMS structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef struct _RILSENDSUPSERVICEDATAPARAMS {
  DWORD     dwExecutor;
  DWORD     dwDataSize;
  WCHAR [1] wszData;
} RILSENDSUPSERVICEDATAPARAMS, RILSENDSUPSERVICEDATAPARAMS;
````


## -struct-fields
<dl>

### -field <b>dwExecutor</b>

<dd></dd>

### -field <b>dwDataSize</b>

<dd></dd>

### -field <b>wszData</b>

<dd></dd>
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
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>