---
UID: NS.ntddrilapitypes.RILVERSIONPARAMS
title: RILVERSIONPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilversionparams.htm
ms.assetid: c6931cee-2b86-4bf8-9e9d-b04e2df9eb12
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
req.alt-api: RILVERSIONPARAMS
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
ms.keywords: RILVERSIONPARAMS, RILVERSIONPARAMS, *LPRILVERSIONPARAMS
req.iface: 
---

# RILVERSIONPARAMS structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef struct _RILVERSIONPARAMS {
  WORD  Minor;
  WORD  Major;
} RILVERSIONPARAMS, RILVERSIONPARAMS;
````


## -struct-fields
<dl>

### -field <b>Minor</b>

<dd></dd>

### -field <b>Major</b>

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