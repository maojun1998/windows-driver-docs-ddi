---
UID: NE.rilapitypes.RILLTEKIND
title: RILLTEKIND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilltekind_2.htm
ms.assetid: ab80e0a2-d404-4333-8a3e-f8e74d8c7f20
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: netvista
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILLTEKIND
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
ms.keywords: RIL_WritePhonebookEntry
req.iface: 
req.product: Windows 10 or later.
---

# RILLTEKIND enumeration



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef enum _RILLTEKIND { 
  RIL_LTEKIND_FDD,
  RIL_LTEKIND_TDD,
  RIL_LTEKIND_RESERVED,
  RIL_LTEKIND_UNKNOWN_CA,
  RIL_LTEKIND_FDD_CA,
  RIL_LTEKIND_TDD_CA,
  RIL_LTEKIND_MAX
} RILLTEKIND;
````


## -enum-fields
<dl>

### -field <a id="RIL_LTEKIND_FDD"></a><a id="ril_ltekind_fdd"></a><b>RIL_LTEKIND_FDD</b>

<dd></dd>

### -field <a id="RIL_LTEKIND_TDD"></a><a id="ril_ltekind_tdd"></a><b>RIL_LTEKIND_TDD</b>

<dd></dd>

### -field <a id="RIL_LTEKIND_RESERVED"></a><a id="ril_ltekind_reserved"></a><b>RIL_LTEKIND_RESERVED</b>

<dd></dd>

### -field <a id="RIL_LTEKIND_UNKNOWN_CA"></a><a id="ril_ltekind_unknown_ca"></a><b>RIL_LTEKIND_UNKNOWN_CA</b>

<dd></dd>

### -field <a id="RIL_LTEKIND_FDD_CA"></a><a id="ril_ltekind_fdd_ca"></a><b>RIL_LTEKIND_FDD_CA</b>

<dd></dd>

### -field <a id="RIL_LTEKIND_TDD_CA"></a><a id="ril_ltekind_tdd_ca"></a><b>RIL_LTEKIND_TDD_CA</b>

<dd></dd>

### -field <a id="RIL_LTEKIND_MAX"></a><a id="ril_ltekind_max"></a><b>RIL_LTEKIND_MAX</b>

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