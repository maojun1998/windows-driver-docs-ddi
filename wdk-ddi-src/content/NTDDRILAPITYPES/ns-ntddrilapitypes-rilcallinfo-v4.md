---
UID: NS.ntddrilapitypes.RILCALLINFO_V4
title: RILCALLINFO_V4
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfo_v4.htm
ms.assetid: 456597d1-e24c-414c-b099-509078cafdc1
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
req.alt-api: RILCALLINFO_V4
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
ms.keywords: RILCALLINFO_V4, RILCALLINFO_V4, *LPRILCALLINFO_V4
req.iface: 
---

# RILCALLINFO_V4 structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef struct _RILCALLINFO_V4 {
  DWORD                           cbSize;
  DWORD                           dwParams;
  DWORD                           dwExecutor;
  DWORD                           dwID;
  RILCALLINFODIRECTION            dwDirection;
  RILCALLINFOSTATUS               dwStatus;
  RILCALLTYPE                     dwType;
  RILCALLINFOMULTIPARTY           dwMultiparty;
  RILADDRESS                      raAddress;
  RILSUBADDRESS                   rsaSubAddress;
  WCHAR [256]                     wszDescription;
  RILREMOTEPARTYINFOVALUE         dwNumberPresentationIndicator;
  RILREMOTEPARTYINFOVALUE         dwNamePresentationIndicator;
  DWORD                           dwFlags;
  RILCALLINFODISCONNECTINITIATOR  dwDisconnectInitiator;
  RILCALLINFODISCONNECTREASON     dwDisconnectReason;
  RILCALLDISCONNECTDETAILS        stDisconnectDetails;
  RILCALLMEDIAOFFERANSWERSET      rcmOfferAnswer;
  RILCALLHANDOVERSTATE            rchsHandoverState;
  RILCALLMODIFICATIONCAUSECODE    dwCallModificationCauseCode;
} RILCALLINFO_V4, RILCALLINFO_V4;
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

### -field <b>dwDirection</b>

<dd></dd>

### -field <b>dwStatus</b>

<dd></dd>

### -field <b>dwType</b>

<dd></dd>

### -field <b>dwMultiparty</b>

<dd></dd>

### -field <b>raAddress</b>

<dd></dd>

### -field <b>rsaSubAddress</b>

<dd></dd>

### -field <b>wszDescription</b>

<dd></dd>

### -field <b>dwNumberPresentationIndicator</b>

<dd></dd>

### -field <b>dwNamePresentationIndicator</b>

<dd></dd>

### -field <b>dwFlags</b>

<dd></dd>

### -field <b>dwDisconnectInitiator</b>

<dd></dd>

### -field <b>dwDisconnectReason</b>

<dd></dd>

### -field <b>stDisconnectDetails</b>

<dd></dd>

### -field <b>rcmOfferAnswer</b>

<dd></dd>

### -field <b>rchsHandoverState</b>

<dd></dd>

### -field <b>dwCallModificationCauseCode</b>

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