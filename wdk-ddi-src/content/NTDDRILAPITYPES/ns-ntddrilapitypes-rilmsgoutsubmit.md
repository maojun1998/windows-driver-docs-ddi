---
UID: NS.ntddrilapitypes.RILMSGOUTSUBMIT
title: RILMSGOUTSUBMIT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgoutsubmit.htm
ms.assetid: 83d15e40-b93f-4c7a-bfe4-db939c24b94f
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
req.alt-api: RILMSGOUTSUBMIT
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
ms.keywords: RILMSGOUTSUBMIT, RILMSGOUTSUBMIT, *LPRILMSGOUTSUBMIT
req.iface: 
---

# RILMSGOUTSUBMIT structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef struct _RILMSGOUTSUBMIT {
  RILADDRESS               raDestAddress;
  RILMSGPROTOCOLID         dwProtocolID;
  RILMSGDCS                rmdDataCoding;
  RILMSGOUTSUBMITVPFORMAT  dwVPFormat;
  RILSYSTEMTIME            stVP;
  DWORD                    dwMsgID;
  DWORD                    cbHdrLength;
  DWORD                    cchMsgLength;
  BYTE [256]               rgbHdr;
  BYTE [512]               rgbMsg;
} RILMSGOUTSUBMIT, RILMSGOUTSUBMIT;
````


## -struct-fields
<dl>

### -field <b>raDestAddress</b>

<dd></dd>

### -field <b>dwProtocolID</b>

<dd></dd>

### -field <b>rmdDataCoding</b>

<dd></dd>

### -field <b>dwVPFormat</b>

<dd></dd>

### -field <b>stVP</b>

<dd></dd>

### -field <b>dwMsgID</b>

<dd></dd>

### -field <b>cbHdrLength</b>

<dd></dd>

### -field <b>cchMsgLength</b>

<dd></dd>

### -field <b>rgbHdr</b>

<dd></dd>

### -field <b>rgbMsg</b>

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