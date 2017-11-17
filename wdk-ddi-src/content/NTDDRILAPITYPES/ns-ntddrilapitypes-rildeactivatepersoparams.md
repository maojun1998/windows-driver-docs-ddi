---
UID: NS.ntddrilapitypes.RILDEACTIVATEPERSOPARAMS
title: RILDEACTIVATEPERSOPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildeactivatepersoparams.htm
ms.assetid: 408ae5d4-f83f-4e4a-9850-a7bae70a2da2
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILDEACTIVATEPERSOPARAMS
req.alt-loc: ntddrilapitypes.h
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
ms.keywords: RILDEACTIVATEPERSOPARAMS, RILDEACTIVATEPERSOPARAMS, *LPRILDEACTIVATEPERSOPARAMS
req.iface: 
---

# RILDEACTIVATEPERSOPARAMS structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef struct _RILDEACTIVATEPERSOPARAMS {
  DWORD      dwPersoFeature;
  char [256] szPassword;
} RILDEACTIVATEPERSOPARAMS, RILDEACTIVATEPERSOPARAMS;
````


## -struct-fields
<dl>

### -field <b>dwPersoFeature</b>

<dd></dd>

### -field <b>szPassword</b>

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
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>