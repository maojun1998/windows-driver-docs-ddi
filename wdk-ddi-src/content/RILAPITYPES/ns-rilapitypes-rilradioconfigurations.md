---
UID: NS.rilapitypes.RILRADIOCONFIGURATIONS
title: RILRADIOCONFIGURATIONS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradioconfigurations_2.htm
ms.assetid: fdd53162-b884-4360-b80a-14225abc1185
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
req.alt-api: RILRADIOCONFIGURATIONS
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
ms.keywords: RILRADIOCONFIGURATIONS, RILRADIOCONFIGURATIONS
req.iface: 
req.product: Windows 10 or later.
---

# RILRADIOCONFIGURATIONS structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef struct _RILRADIOCONFIGURATIONS {
  DWORD                     dwNumberOfConfigurations;
  RILRADIOCONFIGURATION [1] stConfigurations;
} RILRADIOCONFIGURATIONS, RILRADIOCONFIGURATIONS;
````


## -struct-fields
<dl>

### -field <b>dwNumberOfConfigurations</b>

<dd></dd>

### -field <b>stConfigurations</b>

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