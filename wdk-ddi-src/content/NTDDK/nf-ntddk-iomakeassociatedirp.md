---
UID: NF.ntddk.IoMakeAssociatedIrp
title: IoMakeAssociatedIrp
author: windows-driver-content
description: This routine is reserved for use by file systems and file system filter drivers.
old-location: kernel\iomakeassociatedirp.htm
ms.assetid: 96dd78f1-8b71-4707-8b66-20d80c198f81
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoMakeAssociatedIrp
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
req.irql: <= DISPATCH_LEVEL
ms.keywords: IoMakeAssociatedIrp
req.iface: 
---

# IoMakeAssociatedIrp function



## -description
<p>This routine is reserved for use by file systems and file system filter drivers. The <b>IoMakeAssociatedIrp</b> routine allocates and initializes an IRP to be associated with a master IRP sent to a highest-level driver, allowing the caller to split the original request and send associated IRPs on to lower-level drivers.</p>


## -syntax

````
PIRP IoMakeAssociatedIrp(
  _In_ PIRP  Irp,
  _In_ CCHAR StackSize
);
````


## -parameters
<dl>

### -param <i>Irp</i> [in]

<dd>
<p>Pointer to the master IRP that was input to a highest-level driver's Dispatch routine.</p>
</dd>

### -param <i>StackSize</i> [in]

<dd>
<p>Specifies the number of stack locations to be allocated for the associated IRP. The value must be at least equal to the <i>StackSize</i> of the next-lower driver's device object, but the associated IRP can have an additional stack location for the caller. </p>
</dd>
</dl>

## -returns
<p><b>IoMakeAssociatedIrp</b> returns a pointer to the associated IRP or returns a <b>NULL</b> pointer if an IRP cannot be allocated.</p>

## -remarks
<p>Only a highest-level driver can call this routine.</p>

<p>The I/O manager completes the master IRP automatically when lower drivers have completed all associated IRPs as long as the caller has not set its <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine in an associated IRP and returned STATUS_MORE_PROCESSING_REQUIRED from its <i>IoCompletion</i> routine. In these circumstances, the caller must explicitly complete the master IRP when that driver has determined that all associated IRPs were completed.</p>

<p>Only the master IRP is associated with a thread; associated IRPs are not. For this reason, the I/O manager cannot call <a href="https://msdn.microsoft.com/library/windows/hardware/hh406716">Cancel</a> routines for associated IRPs when a thread exits. When the master IRP's thread exits, the I/O manager calls the master IRP's <i>Cancel</i> routine. The <i>Cancel</i> routine is responsible for tracking down all associated IRPs and calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548338">IoCancelIrp</a> to cancel them.</p>

<p>Only a highest-level driver can call this routine.</p>

<p>The I/O manager completes the master IRP automatically when lower drivers have completed all associated IRPs as long as the caller has not set its <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine in an associated IRP and returned STATUS_MORE_PROCESSING_REQUIRED from its <i>IoCompletion</i> routine. In these circumstances, the caller must explicitly complete the master IRP when that driver has determined that all associated IRPs were completed.</p>

<p>Only the master IRP is associated with a thread; associated IRPs are not. For this reason, the I/O manager cannot call <a href="https://msdn.microsoft.com/library/windows/hardware/hh406716">Cancel</a> routines for associated IRPs when a thread exits. When the master IRP's thread exits, the I/O manager calls the master IRP's <i>Cancel</i> routine. The <i>Cancel</i> routine is responsible for tracking down all associated IRPs and calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548338">IoCancelIrp</a> to cancel them.</p>

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
<p>&lt;= DISPATCH_LEVEL</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548330">IoBuildSynchronousFsdRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoMakeAssociatedIrp routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>