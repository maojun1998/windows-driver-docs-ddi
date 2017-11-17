---
UID: NE.ntddrilapitypes.RILUMTSKIND
title: RILUMTSKIND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilumtskind.htm
ms.assetid: aedabb82-73d5-4953-bb7a-4ed526bff5a1
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: netvista
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILUMTSKIND
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
ms.keywords: TUPLE_REQUEST, TUPLE_REQUEST, *PTUPLE_REQUEST
req.iface: 
---

# RILUMTSKIND enumeration



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef enum _RILUMTSKIND { 
  RIL_UMTSKIND_HSDPA,
  RIL_UMTSKIND_HSUPA,
  RIL_UMTSKIND_HSPAPLUS,
  RIL_UMTSKIND_DC_HSPAPLUS,
  RIL_UMTSKIND_HSPAPLUS_64QAM,
  RIL_UMTSKIND_MAX
} RILUMTSKIND;
````


## -enum-fields
<dl>

### -field <a id="RIL_UMTSKIND_HSDPA"></a><a id="ril_umtskind_hsdpa"></a><b>RIL_UMTSKIND_HSDPA</b>

<dd></dd>

### -field <a id="RIL_UMTSKIND_HSUPA"></a><a id="ril_umtskind_hsupa"></a><b>RIL_UMTSKIND_HSUPA</b>

<dd></dd>

### -field <a id="RIL_UMTSKIND_HSPAPLUS"></a><a id="ril_umtskind_hspaplus"></a><b>RIL_UMTSKIND_HSPAPLUS</b>

<dd></dd>

### -field <a id="RIL_UMTSKIND_DC_HSPAPLUS"></a><a id="ril_umtskind_dc_hspaplus"></a><b>RIL_UMTSKIND_DC_HSPAPLUS</b>

<dd></dd>

### -field <a id="RIL_UMTSKIND_HSPAPLUS_64QAM"></a><a id="ril_umtskind_hspaplus_64qam"></a><b>RIL_UMTSKIND_HSPAPLUS_64QAM</b>

<dd></dd>

### -field <a id="RIL_UMTSKIND_MAX"></a><a id="ril_umtskind_max"></a><b>RIL_UMTSKIND_MAX</b>

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