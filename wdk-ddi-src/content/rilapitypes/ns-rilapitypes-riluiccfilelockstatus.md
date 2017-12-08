---
UID: NS.RILAPITYPES.RILUICCFILELOCKSTATUS
title: RILUICCFILELOCKSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccfilelockstatus_2.htm
old-project: netvista
ms.assetid: a06cba0a-9ab6-4125-a506-5cc1d0c1055c
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILUICCFILELOCKSTATUS, RILUICCFILELOCKSTATUS, *LPRILUICCFILELOCKSTATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILUICCFILELOCKSTATUS
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
req.product: Windows 10 or later.
---

# RILUICCFILELOCKSTATUS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax

````
typedef struct _RILUICCFILELOCKSTATUS {
  DWORD                                 cbSize;
  DWORD                                 dwParams;
  RILUICCFILELOCKSTATUSACCESSCONDITION  dwAccessCondition;
  BYTE [MAXNUM_PINREF]                  bPinRef;
} RILUICCFILELOCKSTATUS, RILUICCFILELOCKSTATUS;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwAccessCondition


### -field bPinRef


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>