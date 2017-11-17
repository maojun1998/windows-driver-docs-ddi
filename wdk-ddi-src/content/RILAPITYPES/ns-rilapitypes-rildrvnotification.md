---
UID: NS.rilapitypes.RILDRVNOTIFICATION
title: RILDRVNOTIFICATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildrvnotification_2.htm
ms.assetid: 30a05e7f-3761-4f73-8938-fb7a0e3a7f4c
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
req.alt-api: RILDRVNOTIFICATION
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
ms.keywords: RILDRVNOTIFICATION, RILDRVNOTIFICATION
req.iface: 
req.product: Windows 10 or later.
---

# RILDRVNOTIFICATION structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef struct _RILDRVNOTIFICATION {
  DWORD    cbSize;
  DWORD    cbSizeNeeded;
  DWORD    dwCode;
  HRESULT  hrCmdID;
  DWORD    dwDataSize;
  BYTE [1] pbData;
} RILDRVNOTIFICATION, RILDRVNOTIFICATION;
````


## -struct-fields
<dl>

### -field <b>cbSize</b>

<dd></dd>

### -field <b>cbSizeNeeded</b>

<dd></dd>

### -field <b>dwCode</b>

<dd></dd>

### -field <b>hrCmdID</b>

<dd></dd>

### -field <b>dwDataSize</b>

<dd></dd>

### -field <b>pbData</b>

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