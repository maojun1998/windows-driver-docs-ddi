---
UID: NF.ndis.NdisUnbindAdapter
title: NdisUnbindAdapter
author: windows-driver-content
description: Protocol drivers call the NdisUnbindAdapter function to request NDIS to close a binding to an underlying miniport adapter.
old-location: netvista\ndisunbindadapter.htm
ms.assetid: 47aacc23-f7d1-4c14-9541-3207debef327
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisUnbindAdapter
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Protocol_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: NdisUnbindAdapter
req.iface: 
---

# NdisUnbindAdapter function



## -description
<p>Protocol drivers call the 
  <b>NdisUnbindAdapter</b> function to request NDIS to close a binding to an underlying miniport
  adapter.</p>


## -syntax

````
NDIS_STATUS NdisUnbindAdapter(
  _In_ NDIS_HANDLE NdisBindingHandle
);
````


## -parameters
<dl>

### -param <i>NdisBindingHandle</i> [in]

<dd>
<p>A handle that the protocol driver obtained from a call to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function. The handle
     identifies the binding to close.</p>
</dd>
</dl>

## -returns
<p><b>NdisUnbindAdapter</b> returns one of the following status values:</p><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p><b>NdisUnbindAdapter</b> successfully initiated the unbind operation.</p><dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><p><b>NdisUnbindAdapter</b> failed due to insufficient resources.</p>

<p> </p>

## -remarks
<p>Protocol drivers call 
    <b>NdisUnbindAdapter</b> outside the context of the 
    <a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">ProtocolUnbindAdapterEx</a> or 
    <a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a> functions.
    NDIS schedules a work item to call the protocol driver's 
    <i>ProtocolUnbindAdapterEx</i> function and returns immediately.</p>

<p>Before the call to 
    <b>NdisUnbindAdapter</b> returns, NDIS can already have closed the binding. Therefore, after the call
    returns, the caller must not assume that the handle it passed to the 
    <i>NdisBindingHandle</i> parameter is still valid.</p>

<p>Protocol drivers call 
    <b>NdisUnbindAdapter</b> outside the context of the 
    <a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">ProtocolUnbindAdapterEx</a> or 
    <a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a> functions.
    NDIS schedules a work item to call the protocol driver's 
    <i>ProtocolUnbindAdapterEx</i> function and returns immediately.</p>

<p>Before the call to 
    <b>NdisUnbindAdapter</b> returns, NDIS can already have closed the binding. Therefore, after the call
    returns, the caller must not assume that the handle it passed to the 
    <i>NdisBindingHandle</i> parameter is still valid.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547996">Irql_Protocol_Driver_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">ProtocolUnbindAdapterEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisUnbindAdapter function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>