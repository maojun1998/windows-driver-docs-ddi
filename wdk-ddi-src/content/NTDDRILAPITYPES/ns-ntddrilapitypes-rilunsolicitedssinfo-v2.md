---
UID: NS.ntddrilapitypes.RILUNSOLICITEDSSINFO_V2
title: RILUNSOLICITEDSSINFO_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilunsolicitedssinfo_v2.htm
ms.assetid: f4b93f1e-8559-4145-a122-74d62b146afa
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
req.alt-api: RILUNSOLICITEDSSINFO_V2
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
ms.keywords: RILUNSOLICITEDSSINFO_V2, RILUNSOLICITEDSSINFO_V2, *LPRILUNSOLICITEDSSINFO_V2, RILUNSOLICITEDSSINFO, *LPRILUNSOLICITEDSSINFO
req.iface: 
---

# RILUNSOLICITEDSSINFO_V2 structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef struct _RILUNSOLICITEDSSINFO_V2 {
  DWORD                                 cbSize;
  DWORD                                 dwParams;
  DWORD                                 dwExecutor;
  DWORD                                 dwID;
  RILUNSOLICITEDSSINFONOTIFICATIONCODE  dwNotificationCode;
  RILADDRESS                            raAddress;
  RILSUBADDRESS                         rsaSubAddress;
  DWORD                                 dwCUGIndex;
  DWORD                                 dwHistorynfoLength;
  WCHAR [1]                             wszHistoryInfo;
} RILUNSOLICITEDSSINFO_V2, RILUNSOLICITEDSSINFO_V2;
````


## -struct-fields
<dl>

### -field <b>cbSize</b>

<dd></dd>

### -field <b>dwParams</b>

<dd></dd>

### -field <b>dwExecutor</b>

<dd></dd>

### -field <b>dwID</b>

<dd></dd>

### -field <b>dwNotificationCode</b>

<dd></dd>

### -field <b>raAddress</b>

<dd></dd>

### -field <b>rsaSubAddress</b>

<dd></dd>

### -field <b>dwCUGIndex</b>

<dd></dd>

### -field <b>dwHistorynfoLength</b>

<dd></dd>

### -field <b>wszHistoryInfo</b>

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