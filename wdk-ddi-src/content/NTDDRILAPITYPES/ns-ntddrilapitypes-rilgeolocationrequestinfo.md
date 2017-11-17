---
UID: NS.ntddrilapitypes.RILGEOLOCATIONREQUESTINFO
title: RILGEOLOCATIONREQUESTINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgeolocationrequestinfo.htm
ms.assetid: f3fa5212-66c1-45f8-a96f-78d1f2f01fe8
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
req.alt-api: RILGEOLOCATIONREQUESTINFO
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
ms.keywords: RILGEOLOCATIONREQUESTINFO, RILGEOLOCATIONREQUESTINFO, *LPRILGEOLOCATIONREQUESTINFO
req.iface: 
---

# RILGEOLOCATIONREQUESTINFO structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef struct _RILGEOLOCATIONREQUESTINFO {
  DWORD  cbSize;
  DWORD  dwLatitude;
  DWORD  dwLongitude;
  DWORD  dwAltitude;
} RILGEOLOCATIONREQUESTINFO, RILGEOLOCATIONREQUESTINFO;
````


## -struct-fields
<dl>

### -field <b>cbSize</b>

<dd></dd>

### -field <b>dwLatitude</b>

<dd></dd>

### -field <b>dwLongitude</b>

<dd></dd>

### -field <b>dwAltitude</b>

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