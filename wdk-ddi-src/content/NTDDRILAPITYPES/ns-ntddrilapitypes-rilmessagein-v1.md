---
UID: NS.ntddrilapitypes.RILMESSAGEIN_V1
title: RILMESSAGEIN_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessagein_v1.htm
ms.assetid: c9de99e4-556c-4b3b-a442-53fc52553d3d
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
req.alt-api: RILMESSAGEIN_V1
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
ms.keywords: RILMESSAGEIN_V1, RILMESSAGEIN_V1
req.iface: 
---

# RILMESSAGEIN_V1 structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef struct _RILMESSAGEIN_V1 {
  DWORD       cbSize;
  DWORD       dwExecutor;
  HUICCAPP    hUiccApp;
  DWORD       dwAckID;
  RILMESSAGE  rm;
} RILMESSAGEIN_V1, RILMESSAGEIN_V1;
````


## -struct-fields
<dl>

### -field <b>cbSize</b>

<dd></dd>

### -field <b>dwExecutor</b>

<dd></dd>

### -field <b>hUiccApp</b>

<dd></dd>

### -field <b>dwAckID</b>

<dd></dd>

### -field <b>rm</b>

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