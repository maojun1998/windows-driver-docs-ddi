---
UID: NF.wdm.IoFreeIrp
title: IoFreeIrp
author: windows-driver-content
description: The IoFreeIrp routine releases a caller-allocated IRP from the caller's IoCompletion routine.
old-location: kernel\iofreeirp.htm
ms.assetid: 4a032d44-c6c2-4dce-97ea-28ac47f6ad6c
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoFreeIrp
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IoAllocateFree, IoBuildDeviceControlNoFree, IoBuildFsdFree, IoBuildSynchronousFsdRequestNoFree, HwStorPortProhibitedDDIs, IoFreeIrp
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
ms.keywords: IoFreeIrp
req.iface: 
req.product: Windows 10 or later.
---

# IoFreeIrp function



## -description
<p>The <b>IoFreeIrp</b> routine releases a caller-allocated IRP from the caller's <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine.</p>


## -syntax

````
VOID IoFreeIrp(
  _In_ PIRP Irp
);
````


## -parameters
<dl>

### -param <i>Irp</i> [in]

<dd>
<p>Pointer to the IRP that is to be released.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>This routine is the reciprocal to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548310">IoBuildAsynchronousFsdRequest</a>. The released IRP must have been allocated by the caller.</p>

<p>This routine also releases an IRP allocated with <a href="https://msdn.microsoft.com/library/windows/hardware/ff549397">IoMakeAssociatedIrp</a> in which the caller set up its <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine that returns STATUS_MORE_PROCESSING_REQUIRED for the associated IRP.</p>

<p><b>IoFreeIrp</b> does not free any MDLs that might be attached to the IRP. The driver that frees the IRP must explicitly free these MDLs. In addition, if the physical pages that are described by an MDL are locked, the driver must unlock the pages before it frees the MDL. However, the driver does not need to explicitly unmap these pages. Instead, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549126">IoFreeMdl</a> automatically unmaps the pages when it frees the MDL. For a code example that shows how to free an MDL chain, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.</p>

<p>This routine is the reciprocal to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548310">IoBuildAsynchronousFsdRequest</a>. The released IRP must have been allocated by the caller.</p>

<p>This routine also releases an IRP allocated with <a href="https://msdn.microsoft.com/library/windows/hardware/ff549397">IoMakeAssociatedIrp</a> in which the caller set up its <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine that returns STATUS_MORE_PROCESSING_REQUIRED for the associated IRP.</p>

<p><b>IoFreeIrp</b> does not free any MDLs that might be attached to the IRP. The driver that frees the IRP must explicitly free these MDLs. In addition, if the physical pages that are described by an MDL are locked, the driver must unlock the pages before it frees the MDL. However, the driver does not need to explicitly unmap these pages. Instead, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549126">IoFreeMdl</a> automatically unmaps the pages when it frees the MDL. For a code example that shows how to free an MDL chain, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.</p>

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
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975154">IoAllocateFree</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975160">IoBuildDeviceControlNoFree</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975166">IoBuildFsdFree</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975171">IoBuildSynchronousFsdRequestNoFree</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548310">IoBuildAsynchronousFsdRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549397">IoMakeAssociatedIrp</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoFreeIrp routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>