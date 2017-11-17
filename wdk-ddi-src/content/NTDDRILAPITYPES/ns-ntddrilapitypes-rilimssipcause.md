---
UID: NS.ntddrilapitypes.RILIMSSIPCAUSE
title: RILIMSSIPCAUSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimssipcause.htm
ms.assetid: 79a57fc5-1526-4f18-b51c-7d045092fcb4
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
req.alt-api: RILIMSSIPCAUSE
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
ms.keywords: RILIMSSIPCAUSE, RILIMSSIPCAUSE, *LPRILIMSSIPCAUSE
req.iface: 
---

# RILIMSSIPCAUSE structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef struct _RILIMSSIPCAUSE {
  DWORD  dwCauseValue;
  DWORD  dwReasonValue;
} RILIMSSIPCAUSE, RILIMSSIPCAUSE;
````


## -struct-fields
<dl>

### -field <b>dwCauseValue</b>

<dd></dd>

### -field <b>dwReasonValue</b>

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