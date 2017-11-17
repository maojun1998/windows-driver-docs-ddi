---
UID: NS.rilapitypes.RILPHONEBOOKADDITIONALNUMBER
title: RILPHONEBOOKADDITIONALNUMBER
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookadditionalnumber_2.htm
ms.assetid: 1f6cb182-f85d-4760-96ab-9bd473a08066
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
req.alt-api: RILPHONEBOOKADDITIONALNUMBER
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
ms.keywords: RILPHONEBOOKADDITIONALNUMBER, RILPHONEBOOKADDITIONALNUMBER
req.iface: 
req.product: Windows 10 or later.
---

# RILPHONEBOOKADDITIONALNUMBER structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef struct _RILPHONEBOOKADDITIONALNUMBER {
  DWORD       cbSize;
  DWORD       dwParams;
  RILADDRESS  raAddress;
  DWORD       dwNumId;
} RILPHONEBOOKADDITIONALNUMBER, RILPHONEBOOKADDITIONALNUMBER;
````


## -struct-fields
<dl>

### -field <b>cbSize</b>

<dd></dd>

### -field <b>dwParams</b>

<dd></dd>

### -field <b>raAddress</b>

<dd></dd>

### -field <b>dwNumId</b>

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