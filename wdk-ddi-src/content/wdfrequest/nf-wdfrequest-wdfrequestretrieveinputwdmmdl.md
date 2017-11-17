---
UID: NF.wdfrequest.WdfRequestRetrieveInputWdmMdl
title: WdfRequestRetrieveInputWdmMdl
author: windows-driver-content
description: The WdfRequestRetrieveInputWdmMdl method retrieves a memory descriptor list (MDL) that represents an I/O request's input buffer.
old-location: wdf\wdfrequestretrieveinputwdmmdl.htm
ms.assetid: 8046d9e4-d4a2-4aeb-92b2-a48277af8b41
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfRequestRetrieveInputWdmMdl
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, InputBufferAPI, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, MdlAfterReqCompletedIntIoctl, MdlAfterReqCompletedIntIoctlA, MdlAfterReqCompletedIoctl, MdlAfterReqCompletedIoctlA, MdlAfterReqCompletedRead, MdlAfterReqCompletedWrite, MdlAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
ms.keywords: WdfRequestRetrieveInputWdmMdl
req.iface: 
req.product: Windows 10 or later.
---

# WdfRequestRetrieveInputWdmMdl function



## -description
<p class="CCE_Message">[Applies to KMDF only]</p>
<p>The <b>WdfRequestRetrieveInputWdmMdl</b> method retrieves a memory descriptor list (MDL) that represents an I/O request's input buffer.</p>


## -syntax

````
NTSTATUS WdfRequestRetrieveInputWdmMdl(
  _In_  WDFREQUEST Request,
  _Out_ PMDL       *Mdl
);
````


## -parameters
<dl>

### -param <i>Request</i> [in]

<dd>
<p>A handle to a framework request object. </p>
</dd>

### -param <i>Mdl</i> [out]

<dd>
<p>A pointer to a location that receives a pointer to an MDL.</p>
</dd>
</dl>

## -returns
<p><b>WdfRequestRetrieveInputWdmMdl</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>An input parameter is invalid.</p><dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl><p>The request type is not valid or the request is using <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">neither buffered nor direct I/O</a>. For more information about supported methods for accessing data buffers, see the following Remarks section.</p><dl>
<dt><b>STATUS_INTERNAL_ERROR</b></dt>
</dl><p>The request has already been completed.</p><dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl><p>The input buffer's length is zero.</p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>There is insufficient memory.</p>

<p> </p>

<p>This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


</p>

<p>A bug check occurs if the driver supplies an invalid object handle.</p>

## -remarks
<p>A request's input buffer contains information, such as data to be written to a disk, that was supplied by the originator of the request. Your driver can call <b>WdfRequestRetrieveInputWdmMdl</b> for a write request or a device I/O control request, but not for a read request (because read requests do not provide input data).</p>

<p>The <b>WdfRequestRetrieveInputWdmMdl</b> method retrieves the input buffer's MDL for I/O requests that use the <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">buffered I/O</a> method or the <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">direct I/O</a> method for accessing data buffers. If the request's I/O control code is <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>, or if the request came from another kernel-mode driver, <b>WdfRequestRetrieveInputWdmMdl</b> also supports I/O requests that use <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">neither buffered nor direct I/O</a>. </p>

<p>If <b>WdfRequestRetrieveInputWdmMdl</b> returns STATUS_SUCCESS, the driver receives a pointer to an MDL that describes the input buffer. </p>

<p>The driver must not access a request's MDL after <a href="wdf.completing_i_o_requests">completing the I/O request</a>.</p>

<p>For more information about <b>WdfRequestRetrieveInputWdmMdl</b>, see <a href="wdf.accessing_data_buffers_in_kmdf_drivers">Accessing Data Buffers in Framework-Based Drivers</a>.</p>

<p>The following code example is part of an <a href="https://msdn.microsoft.com/5a0fa3b4-d020-4664-afa4-352573d4f079">EvtIoWrite</a> callback function that obtains an MDL for an I/O request's input buffer. If the call to <b>WdfRequestRetrieveInputWdmMdl</b> fails, the driver completes the request with the error status that <b>WdfRequestRetrieveInputWdmMdl</b> returns.</p>

<p>A request's input buffer contains information, such as data to be written to a disk, that was supplied by the originator of the request. Your driver can call <b>WdfRequestRetrieveInputWdmMdl</b> for a write request or a device I/O control request, but not for a read request (because read requests do not provide input data).</p>

<p>The <b>WdfRequestRetrieveInputWdmMdl</b> method retrieves the input buffer's MDL for I/O requests that use the <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">buffered I/O</a> method or the <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">direct I/O</a> method for accessing data buffers. If the request's I/O control code is <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>, or if the request came from another kernel-mode driver, <b>WdfRequestRetrieveInputWdmMdl</b> also supports I/O requests that use <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">neither buffered nor direct I/O</a>. </p>

<p>If <b>WdfRequestRetrieveInputWdmMdl</b> returns STATUS_SUCCESS, the driver receives a pointer to an MDL that describes the input buffer. </p>

<p>The driver must not access a request's MDL after <a href="wdf.completing_i_o_requests">completing the I/O request</a>.</p>

<p>For more information about <b>WdfRequestRetrieveInputWdmMdl</b>, see <a href="wdf.accessing_data_buffers_in_kmdf_drivers">Accessing Data Buffers in Framework-Based Drivers</a>.</p>

<p>The following code example is part of an <a href="https://msdn.microsoft.com/5a0fa3b4-d020-4664-afa4-352573d4f079">EvtIoWrite</a> callback function that obtains an MDL for an I/O request's input buffer. If the call to <b>WdfRequestRetrieveInputWdmMdl</b> fails, the driver completes the request with the error status that <b>WdfRequestRetrieveInputWdmMdl</b> returns.</p>

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
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfrequest.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547165">InputBufferAPI</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547261">InvalidReqAccess</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547267">InvalidReqAccessLocal</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549038">MdlAfterReqCompletedIntIoctl</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549042">MdlAfterReqCompletedIntIoctlA</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549047">MdlAfterReqCompletedIoctl</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549056">MdlAfterReqCompletedIoctlA</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549058">MdlAfterReqCompletedRead</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549075">MdlAfterReqCompletedWrite</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549077">MdlAfterReqCompletedWriteA</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550021">WdfRequestRetrieveOutputWdmMdl</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestRetrieveInputWdmMdl method%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>