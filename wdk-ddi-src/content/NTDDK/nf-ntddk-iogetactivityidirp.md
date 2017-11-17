---
UID: NF.ntddk.IoGetActivityIdIrp
title: IoGetActivityIdIrp
author: windows-driver-content
description: The IoGetActivityIdIrp routine retrieves the current activity ID associated with an IRP.
old-location: kernel\iogetactivityidirp.htm
ms.assetid: FAFF65EF-F1D8-4B54-B281-D5C4AC124E32
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoGetActivityIdIrp
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
ms.keywords: IoGetActivityIdIrp
req.iface: 
---

# IoGetActivityIdIrp function



## -description
<p>The IoGetActivityIdIrp routine retrieves the current activity ID associated with an IRP.</p>


## -syntax

````
NTSTATUS IoGetActivityIdIrp(
  _In_  PIRP   Irp,
  _Out_ LPGUID Guid
);
````


## -parameters
<dl>

### -param <i>Irp</i> [in]

<dd>
<p>The IRP from which to retrieve the activity ID.</p>
</dd>

### -param <i>Guid</i> [out]

<dd>
<p>A pointer to a location  to store the retrieved GUID.</p>
</dd>
</dl>

## -returns
<p>IoGetActivityIdIrp returns STATUS_SUCCESS if the call is successful. Possible error return values include the following.</p><dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl><p>No activity ID is associated with the request.</p>

<p> </p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
</td>
</tr>
</table>