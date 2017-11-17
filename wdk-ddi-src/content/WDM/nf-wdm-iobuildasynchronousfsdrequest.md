---
UID: NF.wdm.IoBuildAsynchronousFsdRequest
title: IoBuildAsynchronousFsdRequest
author: windows-driver-content
description: The IoBuildAsynchronousFsdRequest routine allocates and sets up an IRP to be sent to lower-level drivers.
old-location: kernel\iobuildasynchronousfsdrequest.htm
ms.assetid: cb633146-c3ab-4a09-bbcd-5964ecbf6e44
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
req.alt-api: IoBuildAsynchronousFsdRequest
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: ForwardedAtBadIrqlFsdAsync, IoBuildFsdComplete, IoBuildFsdForward, IoBuildFsdFree, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
ms.keywords: IoBuildAsynchronousFsdRequest
req.iface: 
req.product: Windows 10 or later.
---

# IoBuildAsynchronousFsdRequest function



## -description
<p>The <b>IoBuildAsynchronousFsdRequest</b> routine allocates and sets up an IRP to be sent to lower-level drivers.</p>


## -syntax

````
PIRP IoBuildAsynchronousFsdRequest(
  _In_     ULONG            MajorFunction,
  _In_     PDEVICE_OBJECT   DeviceObject,
  _Inout_  PVOID            Buffer,
  _In_opt_ ULONG            Length,
  _In_opt_ PLARGE_INTEGER   StartingOffset,
  _In_opt_ PIO_STATUS_BLOCK IoStatusBlock
);
````


## -parameters
<dl>

### -param <i>MajorFunction</i> [in]

<dd>
<p>The major function code to be set in the IRP. This code can be <a href="https://msdn.microsoft.com/library/windows/hardware/ff549268">IRP_MJ_PNP</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549235">IRP_MJ_FLUSH_BUFFERS</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549423">IRP_MJ_SHUTDOWN</a>.</p>
</dd>

### -param <i>DeviceObject</i> [in]

<dd>
<p>A pointer to the next-lower driver's device object. This object represents the target device for the read, write, flush, or shutdown operation.</p>
</dd>

### -param <i>Buffer</i> [in, out]

<dd>
<p>A pointer to a buffer into which data is read or from which data is written. The value of this argument is <b>NULL</b> for flush and shutdown requests.</p>
</dd>

### -param <i>Length</i> [in, optional]

<dd>
<p>The length, in bytes, of the buffer pointed to by <i>Buffer</i>. For devices such as disks, this value must be an integer multiple of the sector size. Starting with Windows 8, the sector size can be 4,096 or 512 bytes. In earlier versions of Windows, the sector size is always 512 bytes. This parameter is required for read and write requests, but must be zero for flush and shutdown requests.</p>
</dd>

### -param <i>StartingOffset</i> [in, optional]

<dd>
<p>A pointer to the starting offset on the input/output media. The value of this argument is zero for flush and shutdown requests.</p>
</dd>

### -param <i>IoStatusBlock</i> [in, optional]

<dd>
<p>A pointer to the address of an I/O status block in which the to-be-called drivers return final status about the requested operation.</p>
</dd>
</dl>

## -returns
<p><b>IoBuildAsynchronousFsdRequest</b> returns a pointer to an IRP, or a <b>NULL</b> pointer if the IRP cannot be allocated.</p>

## -remarks
<p>Intermediate or highest-level drivers can call <b>IoBuildAsynchronousFsdRequest</b> to set up IRPs for requests sent to lower-level drivers. The calling driver must supply an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine for the IRP, so the IRP can be deallocated with <a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a>. For more information about IRP deallocation, see Examples.</p>

<p>The IRP that gets built contains only enough information to get the operation started and to complete the IRP. No other context information is tracked because an asynchronous request is context-independent.</p>

<p>Lower-level drivers might impose restrictions on parameters supplied to this routine. For example, disk drivers might require that values supplied for <i>Length</i> and <i>StartingOffset</i> be integer multiples of the device's sector size.</p>

<p>An intermediate or highest-level driver also can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548330">IoBuildSynchronousFsdRequest</a> to set up requests it sends to lower-level drivers. Only a highest-level driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549397">IoMakeAssociatedIrp</a>.</p>

<p>During an <b>IoBuildAsynchronousFsdRequest</b> call, the I/O manager sets the <b>Tail.Overlay.Thread</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure to point to the caller's thread object, but does <u>not</u> take a counted reference to the thread object on behalf of the caller. After the caller sends the IRP to the driver for the target device, this driver might use the <b>Tail.Overlay.Thread</b> member to access the thread object. For example, a storage driver might call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549707">IoSetHardErrorOrVerifyDevice</a> routine and supply a pointer to the IRP as an input parameter. During this call, <b>IoSetHardErrorOrVerifyDevice</b> uses the <b>Tail.Overlay.Thread</b> member to access the thread object. When the thread object is accessed in this way, the driver that called <b>IoBuildAsynchronousFsdRequest</b> to allocate the IRP is responsible for ensuring that the thread object stays valid while the IRP is being handled.</p>

<p>To keep the thread object valid, the driver that calls <b>IoBuildAsynchronousFsdRequest</b> can take a counted reference on the thread object before sending the IRP. For example, this driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558688">ObReferenceObjectByPointerWithTag</a> routine and supply, as the <i>Object</i> parameter, the object pointer from the <b>Tail.Overlay.Thread</b> member of the <b>IRP</b> structure. Later, this driver's completion routine can dereference the object by calling a routine such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff557734">ObDereferenceObjectWithTag</a>.</p>

<p>A driver might call <b>IoBuildAsynchronousFsdRequest</b> in one thread, and send the IRP allocated by this call in another thread. Before sending the IRP, this driver should set the <b>Tail.Overlay.Thread</b> member of the IRP to point to the thread object for the sending thread. Typically, the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559936">PsGetCurrentThread</a> routine to get the thread object pointer.</p>

<p>A driver that calls <b>IoBuildAsynchronousFsdRequest</b> to allocate an IRP does not necessarily need to take a counted reference on the thread object pointed to by the <b>Tail.Overlay.Thread</b> member of the IRP. The driver might instead use another technique to guarantee that this thread object remains valid while the IRP is being handled. For example, if the driver created the thread, the thread can wait until the IRP is completed to terminate itself.</p>

<p>Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a>, an additional step is required to free the buffer for an IRP built by <b>IoBuildAsynchronousFsdRequest</b> if the following are all true:</p>

<p>Before freeing the buffer for this IRP, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556381">MmUnlockPages</a> routine with <b>Irp-&gt;MdlAddress</b> as the parameter value. This call decrements the extra reference count that <b>IoBuildAsynchronousFsdRequest</b> added to the pool pages in the MDL. Otherwise, the subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549126">IoFreeMdl</a> will bug check because the reference count for these pool pages will be 2, not 1. The following code example shows the <b>MmUnlockPages</b>, <b>IoFreeMdl</b>, and <b>IoFreeIrp</b> calls for this case:</p>

<p>Intermediate or highest-level drivers can call <b>IoBuildAsynchronousFsdRequest</b> to set up IRPs for requests sent to lower-level drivers. The calling driver must supply an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine for the IRP, so the IRP can be deallocated with <a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a>. For more information about IRP deallocation, see Examples.</p>

<p>The IRP that gets built contains only enough information to get the operation started and to complete the IRP. No other context information is tracked because an asynchronous request is context-independent.</p>

<p>Lower-level drivers might impose restrictions on parameters supplied to this routine. For example, disk drivers might require that values supplied for <i>Length</i> and <i>StartingOffset</i> be integer multiples of the device's sector size.</p>

<p>An intermediate or highest-level driver also can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548330">IoBuildSynchronousFsdRequest</a> to set up requests it sends to lower-level drivers. Only a highest-level driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549397">IoMakeAssociatedIrp</a>.</p>

<p>During an <b>IoBuildAsynchronousFsdRequest</b> call, the I/O manager sets the <b>Tail.Overlay.Thread</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure to point to the caller's thread object, but does <u>not</u> take a counted reference to the thread object on behalf of the caller. After the caller sends the IRP to the driver for the target device, this driver might use the <b>Tail.Overlay.Thread</b> member to access the thread object. For example, a storage driver might call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549707">IoSetHardErrorOrVerifyDevice</a> routine and supply a pointer to the IRP as an input parameter. During this call, <b>IoSetHardErrorOrVerifyDevice</b> uses the <b>Tail.Overlay.Thread</b> member to access the thread object. When the thread object is accessed in this way, the driver that called <b>IoBuildAsynchronousFsdRequest</b> to allocate the IRP is responsible for ensuring that the thread object stays valid while the IRP is being handled.</p>

<p>To keep the thread object valid, the driver that calls <b>IoBuildAsynchronousFsdRequest</b> can take a counted reference on the thread object before sending the IRP. For example, this driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558688">ObReferenceObjectByPointerWithTag</a> routine and supply, as the <i>Object</i> parameter, the object pointer from the <b>Tail.Overlay.Thread</b> member of the <b>IRP</b> structure. Later, this driver's completion routine can dereference the object by calling a routine such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff557734">ObDereferenceObjectWithTag</a>.</p>

<p>A driver might call <b>IoBuildAsynchronousFsdRequest</b> in one thread, and send the IRP allocated by this call in another thread. Before sending the IRP, this driver should set the <b>Tail.Overlay.Thread</b> member of the IRP to point to the thread object for the sending thread. Typically, the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559936">PsGetCurrentThread</a> routine to get the thread object pointer.</p>

<p>A driver that calls <b>IoBuildAsynchronousFsdRequest</b> to allocate an IRP does not necessarily need to take a counted reference on the thread object pointed to by the <b>Tail.Overlay.Thread</b> member of the IRP. The driver might instead use another technique to guarantee that this thread object remains valid while the IRP is being handled. For example, if the driver created the thread, the thread can wait until the IRP is completed to terminate itself.</p>

<p>Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a>, an additional step is required to free the buffer for an IRP built by <b>IoBuildAsynchronousFsdRequest</b> if the following are all true:</p>

<p>Before freeing the buffer for this IRP, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556381">MmUnlockPages</a> routine with <b>Irp-&gt;MdlAddress</b> as the parameter value. This call decrements the extra reference count that <b>IoBuildAsynchronousFsdRequest</b> added to the pool pages in the MDL. Otherwise, the subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549126">IoFreeMdl</a> will bug check because the reference count for these pool pages will be 2, not 1. The following code example shows the <b>MmUnlockPages</b>, <b>IoFreeMdl</b>, and <b>IoFreeIrp</b> calls for this case:</p>

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
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975148">ForwardedAtBadIrqlFsdAsync</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975164">IoBuildFsdComplete</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975165">IoBuildFsdForward</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975166">IoBuildFsdFree</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549126">IoFreeMdl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549397">IoMakeAssociatedIrp</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549707">IoSetHardErrorOrVerifyDevice</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556381">MmUnlockPages</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557734">ObDereferenceObjectWithTag</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558688">ObReferenceObjectByPointerWithTag</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559936">PsGetCurrentThread</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoBuildAsynchronousFsdRequest routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>