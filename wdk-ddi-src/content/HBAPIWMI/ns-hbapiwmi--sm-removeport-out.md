---
UID: NS.hbapiwmi._SM_RemovePort_OUT
title: SM_RemovePort_OUT
author: windows-driver-content
description: The SM_RemovePort_OUT structure is used to receive output parameters from the SM_RemovePort WMI method.
old-location: storage\sm_removeport_out.htm
ms.assetid: 7ca1bd9f-8fd4-4d9d-8571-4d6e4b721f3b
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SM_RemovePort_OUT
req.alt-loc: hbapiwmi.h
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
ms.keywords: SM_RemovePort_OUT, SM_RemovePort_OUT, *PSM_RemovePort_OUT
req.iface: 
---

# SM_RemovePort_OUT structure



## -description
<p>The SM_RemovePort_OUT structure is used to receive output parameters from the SM_RemovePort WMI method.</p>


## -syntax

````
typedef struct _SM_RemovePort_OUT {
  ULONG HBAStatus;
} SM_RemovePort_OUT, *PSM_RemovePort_OUT;
````


## -struct-fields
<dl>

### -field <b>HBAStatus</b>

<dd>
<p>The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.</p>
</dd>
</dl>

## -remarks
<p>The WMI tool suite generates a declaration of the SM_RemovePort_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_EventControl WMI class.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>