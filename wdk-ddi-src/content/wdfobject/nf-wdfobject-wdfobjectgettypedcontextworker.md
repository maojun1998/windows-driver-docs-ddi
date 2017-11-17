---
UID: NF.wdfobject.WdfObjectGetTypedContextWorker
title: WdfObjectGetTypedContextWorker
author: windows-driver-content
description: The WdfObjectGetTypedContextWorker method is reserved for internal use only. Use the WdfObjectGetTypedContext macro instead.
old-location: wdf\wdfobjectgettypedcontextworker.htm
ms.assetid: 1d95084b-16c4-468e-84af-47650292c5a1
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdfobject.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WdfObjectGetTypedContextWorker
req.alt-loc: wdfobject.h
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
ms.keywords: WdfObjectGetTypedContextWorker
req.iface: 
req.product: Windows 10 or later.
---

# WdfObjectGetTypedContextWorker function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WdfObjectGetTypedContextWorker</b> method is reserved for internal use only. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548749">WdfObjectGetTypedContext</a> macro instead.</p>


## -syntax

````
PVOID WdfObjectGetTypedContextWorker(
  _In_ WDFOBJECT                      Handle,
  _In_ PCWDF_OBJECT_CONTEXT_TYPE_INFO TypeInfo
);
````


## -parameters
<dl>

### -param <i>Handle</i> [in]

<dd></dd>

### -param <i>TypeInfo</i> [in]

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
<dt>Wdfobject.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>
</td>
</tr>
</table>