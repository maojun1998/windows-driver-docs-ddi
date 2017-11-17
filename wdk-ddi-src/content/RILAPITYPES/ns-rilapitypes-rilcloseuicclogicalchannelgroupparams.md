---
UID: NS.rilapitypes.RILCLOSEUICCLOGICALCHANNELGROUPPARAMS
title: RILCLOSEUICCLOGICALCHANNELGROUPPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcloseuicclogicalchannelgroupparams_2.htm
ms.assetid: 89d50918-2cd2-4889-aec4-fc9e2875855a
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
req.alt-api: RILCLOSEUICCLOGICALCHANNELGROUPPARAMS
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
ms.keywords: RILCLOSEUICCLOGICALCHANNELGROUPPARAMS, RILCLOSEUICCLOGICALCHANNELGROUPPARAMS
req.iface: 
req.product: Windows 10 or later.
---

# RILCLOSEUICCLOGICALCHANNELGROUPPARAMS structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef struct _RILCLOSEUICCLOGICALCHANNELGROUPPARAMS {
  DWORD  dwSlotIndex;
  DWORD  dwChannelGroup;
} RILCLOSEUICCLOGICALCHANNELGROUPPARAMS, RILCLOSEUICCLOGICALCHANNELGROUPPARAMS;
````


## -struct-fields
<dl>

### -field <b>dwSlotIndex</b>

<dd></dd>

### -field <b>dwChannelGroup</b>

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