---
UID: NF.netioddk.NmrProviderDetachClientComplete
title: NmrProviderDetachClientComplete
author: windows-driver-content
description: The NmrProviderDetachClientComplete function notifies the NMR that a provider module has completed detaching from a client module.
old-location: netvista\nmrproviderdetachclientcomplete.htm
ms.assetid: a52b3cfc-d6bd-4569-8b09-36dce65d017f
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: netioddk.h
req.include-header: Wsk.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating
   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NmrProviderDetachClientComplete
req.alt-loc: netio.lib,netio.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Netio.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: NmrProviderDetachClientComplete
req.iface: 
---

# NmrProviderDetachClientComplete function



## -description
<p>The 
  <b>NmrProviderDetachClientComplete</b> function notifies the NMR that a provider module has completed
  detaching from a client module.</p>


## -syntax

````
VOID NmrProviderDetachClientComplete(
  _In_ HANDLE NmrBindingHandle
);
````


## -parameters
<dl>

### -param <i>NmrBindingHandle</i> [in]

<dd>
<p>A handle used by the NMR to represent the binding between the client module and the provider
     module. The NMR passes this handle to the provider module when it calls the provider module's 
     <a href="https://msdn.microsoft.com/6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3">ProviderAttachClient</a> callback
     function.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>A provider module calls the 
    <b>NmrProviderDetachClientComplete</b> function when it asynchronously completes detaching from a client
    module after returning STATUS_PENDING from its 
    <a href="https://msdn.microsoft.com/0f29bf89-856c-4019-a966-3e666a7fc78d">ProviderDetachClient</a> callback
    function.</p>

<p>A provider module should not call the 
    <b>NmrProviderDetachClientComplete</b> function if it returns STATUS_SUCCESS from its 
    <a href="https://msdn.microsoft.com/0f29bf89-856c-4019-a966-3e666a7fc78d">ProviderDetachClient</a> callback
    function.</p>

<p>A provider module calls the 
    <b>NmrProviderDetachClientComplete</b> function when it asynchronously completes detaching from a client
    module after returning STATUS_PENDING from its 
    <a href="https://msdn.microsoft.com/0f29bf89-856c-4019-a966-3e666a7fc78d">ProviderDetachClient</a> callback
    function.</p>

<p>A provider module should not call the 
    <b>NmrProviderDetachClientComplete</b> function if it returns STATUS_SUCCESS from its 
    <a href="https://msdn.microsoft.com/0f29bf89-856c-4019-a966-3e666a7fc78d">ProviderDetachClient</a> callback
    function.</p>

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
<p>Available in Windows Vista and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Netioddk.h (include Wsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Netio.lib</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3">ProviderAttachClient</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/0f29bf89-856c-4019-a966-3e666a7fc78d">ProviderDetachClient</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NmrProviderDetachClientComplete function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>