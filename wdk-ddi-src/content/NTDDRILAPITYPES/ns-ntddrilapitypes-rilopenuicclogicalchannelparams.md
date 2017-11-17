---
UID: NS.ntddrilapitypes.RILOPENUICCLOGICALCHANNELPARAMS
title: RILOPENUICCLOGICALCHANNELPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilopenuicclogicalchannelparams.htm
ms.assetid: 4bc3a16b-dc9e-4c15-9083-75ac4608def5
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
req.alt-api: RILOPENUICCLOGICALCHANNELPARAMS
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
ms.keywords: RILOPENUICCLOGICALCHANNELPARAMS, RILOPENUICCLOGICALCHANNELPARAMS, *LPRILOPENUICCLOGICALCHANNELPARAMS
req.iface: 
---

# RILOPENUICCLOGICALCHANNELPARAMS structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef struct _RILOPENUICCLOGICALCHANNELPARAMS {
  DWORD     dwSlotIndex;
  DWORD     dwChannelGroup;
  DWORD     dwAppIdLength;
  BYTE [32] bAppId;
  DWORD     dwSelectP2Arg;
} RILOPENUICCLOGICALCHANNELPARAMS, RILOPENUICCLOGICALCHANNELPARAMS;
````


## -struct-fields
<dl>

### -field <b>dwSlotIndex</b>

<dd></dd>

### -field <b>dwChannelGroup</b>

<dd></dd>

### -field <b>dwAppIdLength</b>

<dd></dd>

### -field <b>bAppId</b>

<dd></dd>

### -field <b>dwSelectP2Arg</b>

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