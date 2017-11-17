---
UID: NS.bdatypes._BDA_DISEQC_RESPONSE
title: BDA_DISEQC_RESPONSE
author: windows-driver-content
description: TBD.
old-location: stream\bda_diseqc_response.htm
ms.assetid: 724FD17B-D12B-423D-AA0E-93D9D31DC93E
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: stream
req.header: bdatypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BDA_DISEQC_RESPONSE
req.alt-loc: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: BDA_DISEQC_RESPONSE, BDA_DISEQC_RESPONSE, *PBDA_DISEQC_RESPONSE
req.iface: 
---

# BDA_DISEQC_RESPONSE structure



## -description
<p>TBD</p>


## -syntax

````
typedef struct _BDA_DISEQC_RESPONSE {
  ULONG ulRequestId;
  ULONG ulPacketLength;
  BYTE  argbPacketData[8];
} BDA_DISEQC_RESPONSE, *PBDA_DISEQC_RESPONSE;
````


## -struct-fields
<dl>

### -field <b>ulRequestId</b>

<dd>
<p>TBD</p>
</dd>

### -field <b>ulPacketLength</b>

<dd>
<p>TBD</p>
</dd>

### -field <b>argbPacketData</b>

<dd>
<p>TBD</p>
</dd>
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
<dt>Bdatypes.h</dt>
</dl>
</td>
</tr>
</table>