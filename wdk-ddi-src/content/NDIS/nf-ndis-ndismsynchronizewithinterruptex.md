---
UID: NF.ndis.NdisMSynchronizeWithInterruptEx
title: NdisMSynchronizeWithInterruptEx
author: windows-driver-content
description: Miniport drivers call the NdisMSynchronizeWithInterruptEx function to synchronize the execution of a miniport driver-supplied function with the MiniportInterrupt function.
old-location: netvista\ndismsynchronizewithinterruptex.htm
ms.assetid: 5dca9258-a3ae-43f4-a5aa-d591165d72ed
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMSynchronizeWithInterruptEx
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: NdisMDeregisterInterruptEx
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DIRQL
ms.keywords: NdisMSynchronizeWithInterruptEx
req.iface: 
---

# NdisMSynchronizeWithInterruptEx function



## -description
<p>Miniport drivers call the
  <b>NdisMSynchronizeWithInterruptEx</b> function to synchronize the execution of a miniport driver-supplied
  function with the 
  <a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a> function.</p>


## -syntax

````
BOOLEAN NdisMSynchronizeWithInterruptEx(
  _In_ NDIS_HANDLE NdisInterruptHandle,
  _In_ ULONG       MessageId,
  _In_ PVOID       SynchronizeFunction,
  _In_ PVOID       SynchronizeContext
);
````


## -parameters
<dl>

### -param <i>NdisInterruptHandle</i> [in]

<dd>
<p>An interrupt handle that the miniport driver obtained in a previous call to the 
     <a href="https://msdn.microsoft.com/db0b3d51-5bbb-45fb-8c45-dda8c2212b5f">
     NdisMRegisterInterruptEx</a> function.</p>
</dd>

### -param <i>MessageId</i> [in]

<dd>
<p>A message-signaled interrupt with which the driver must synchronize. If NDIS did not grant message
     signaled interrupts for the driver, NDIS ignores this parameter. 
     <i>MessageId</i> is an index to the 
     <a href="https://msdn.microsoft.com/e5007381-2436-4eb6-85cd-7145361ab793">
     IO_INTERRUPT_MESSAGE_INFO_ENTRY</a> structures inside a 
     <a href="https://msdn.microsoft.com/d740d55e-6549-494d-9b2a-39d5c2e670d3">
     IO_INTERRUPT_MESSAGE_INFO</a> structure. NDIS passes a pointer to the associated
     IO_INTERRUPT_MESSAGE_INFO structure at the 
     <b>MessageInfoTable</b> member when the driver successfully registers for MSI with the 
     <b>NdisMRegisterInterruptEx</b> function.</p>
</dd>

### -param <i>SynchronizeFunction</i> [in]

<dd>
<p>The entry point of the driver's 
     <a href="https://msdn.microsoft.com/aac1ff91-76aa-46a0-8e8a-85b9f8c3323c">
     MiniportSynchronizeInterrupt</a> function.</p>
</dd>

### -param <i>SynchronizeContext</i> [in]

<dd>
<p>A pointer to a miniport-driver-determined context area that is passed to the 
     <i>MiniportSynchronizeInterrupt</i> function at 
     <i>SynchronizeContext</i> .</p>
</dd>
</dl>

## -returns
<p><b>NdisMSynchronizeWithInterruptEx</b> returns the Boolean value that 
     <i>MiniportSynchronizeInterrupt</i> returns.</p>

## -remarks
<p>Miniport drivers that register an interrupt with
    <b>NdisMRegisterInterruptEx</b> use
    <b>NdisMSynchronizeWithInterruptEx</b>. The value that the 
    <a href="https://msdn.microsoft.com/aac1ff91-76aa-46a0-8e8a-85b9f8c3323c">
    MiniportSynchronizeInterrupt</a> function returns is also returned by 
    <b>NdisMSynchronizeWithInterruptEx</b>. This propagated value provides status to the caller.</p>

<p>Any miniport driver function that shares resources with any other driver function that runs at DIRQL
    must use 
    <b>NdisMSynchronizeWithInterruptEx</b> to synchronize its access to those resources. The 
    <i>MiniportSynchronizeInterrupt</i> function also runs at DIRQL, and the shared resources are protected by
    a system-allocated spin lock. Thus, the shared resources are protected from simultaneous access by the 
    <i>MiniportInterrupt</i> function and the caller.</p>

<p><b>NdisMSynchronizeWithInterruptEx</b> releases the system spin lock and restores the original IRQL of its
    caller before it returns control.</p>

<p>For more information about acquiring and releasing NDIS spin locks, see 
    <a href="netvista.synchronization_and_notification_in_network_drivers">Synchronization
    and Notification in Network Drivers</a>.</p>

<p>Miniport drivers that register an interrupt with
    <b>NdisMRegisterInterruptEx</b> use
    <b>NdisMSynchronizeWithInterruptEx</b>. The value that the 
    <a href="https://msdn.microsoft.com/aac1ff91-76aa-46a0-8e8a-85b9f8c3323c">
    MiniportSynchronizeInterrupt</a> function returns is also returned by 
    <b>NdisMSynchronizeWithInterruptEx</b>. This propagated value provides status to the caller.</p>

<p>Any miniport driver function that shares resources with any other driver function that runs at DIRQL
    must use 
    <b>NdisMSynchronizeWithInterruptEx</b> to synchronize its access to those resources. The 
    <i>MiniportSynchronizeInterrupt</i> function also runs at DIRQL, and the shared resources are protected by
    a system-allocated spin lock. Thus, the shared resources are protected from simultaneous access by the 
    <i>MiniportInterrupt</i> function and the caller.</p>

<p><b>NdisMSynchronizeWithInterruptEx</b> releases the system spin lock and restores the original IRQL of its
    caller before it returns control.</p>

<p>For more information about acquiring and releasing NDIS spin locks, see 
    <a href="netvista.synchronization_and_notification_in_network_drivers">Synchronization
    and Notification in Network Drivers</a>.</p>

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
<p>&lt;= DIRQL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563575">NdisMDeregisterInterruptEx</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550576">IO_INTERRUPT_MESSAGE_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/e5007381-2436-4eb6-85cd-7145361ab793">
   IO_INTERRUPT_MESSAGE_INFO_ENTRY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/aac1ff91-76aa-46a0-8e8a-85b9f8c3323c">
   MiniportSynchronizeInterrupt</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563649">NdisMRegisterInterruptEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMSynchronizeWithInterruptEx function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>