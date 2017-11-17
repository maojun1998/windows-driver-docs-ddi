---
UID: NS.ntddrilapitypes.RILSENDRTTDATAPARAMS
title: RILSENDRTTDATAPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendrttdataparams.htm
ms.assetid: 733b8ccc-5335-4c7e-bfc0-4618b0b3a4d8
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
req.alt-api: RILSENDRTTDATAPARAMS
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
ms.keywords: RILSENDRTTDATAPARAMS, RILSENDRTTDATAPARAMS, *LPRILSENDRTTDATAPARAMS
req.iface: 
---

# RILSENDRTTDATAPARAMS structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef struct _RILSENDRTTDATAPARAMS {
  DWORD       cbSize;
  DWORD       dwID;
  DWORD       dwExecutor;
  WCHAR [127] wszRTTText;
} RILSENDRTTDATAPARAMS, RILSENDRTTDATAPARAMS;
````


## -struct-fields
<dl>

### -field <b>cbSize</b>

<dd></dd>

### -field <b>dwID</b>

<dd></dd>

### -field <b>dwExecutor</b>

<dd></dd>

### -field <b>wszRTTText</b>

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