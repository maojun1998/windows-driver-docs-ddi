---
UID: NF.ntifs.ZwSetQuotaInformationFile
title: ZwSetQuotaInformationFile
author: windows-driver-content
description: The ZwSetQuotaInformationFile routine changes quota entries for the volume associated with the FileHandle parameter. All of the quota entries in the specified buffer are applied to the volume.
old-location: kernel\zwsetquotainformationfile.htm
ms.assetid: 40c7a74c-eace-4d01-8a55-2c3c8bace8fb
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwSetQuotaInformationFile,NtSetQuotaInformationFile
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
ms.keywords: ZwSetQuotaInformationFile
req.iface: 
---

# ZwSetQuotaInformationFile function



## -description
<p>The <b>ZwSetQuotaInformationFile</b> routine changes quota entries for the volume associated with the <i>FileHandle</i> parameter. All of the quota entries in the specified buffer are applied to the volume. </p>


## -syntax

````
NTSTATUS ZwSetQuotaInformationFile(
  _In_  HANDLE           FileHandle,
  _Out_ PIO_STATUS_BLOCK IoStatusBlock,
  _In_  PVOID            Buffer,
  _In_  ULONG            Length
);
````


## -parameters
<dl>

### -param <i>FileHandle</i> [in]

<dd>
<p>A handle for the file object that represents the file or volume for which the quota information is to be modified.</p>
</dd>

### -param <i>IoStatusBlock</i> [out]

<dd>
<p>The address of the caller's I/O status block.</p>
</dd>

### -param <i>Buffer</i> [in]

<dd>
<p>A buffer containing the new quota entries that should be applied to the volume. The quota information must be formatted as one or more <a href="https://msdn.microsoft.com/library/windows/hardware/ff540342">FILE_QUOTA_INFORMATION</a> structures. The <b>NextEntryOffset</b> field in the <b>FILE_QUOTA_INFORMATION</b> structure contains the offset, in bytes, of the next quota entry in the list. If there are no more entries after the current one, this member is zero.</p>
</dd>

### -param <i>Length</i> [in]

<dd>
<p>The length in bytes of the buffer. </p>
</dd>
</dl>

## -returns
<p>The <b>ZwSetQuotaInformationFile</b> routine returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: </p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES </b></dt>
</dl><p>There were insufficient resources to complete the operation. This is an error code.</p><dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl><p>Quotas are not enabled on the volume. This is an error code.</p><dl>
<dt><b>STATUS_MEDIA_WRITE_PROTECTED</b></dt>
</dl><p>The volume is read only. This is an error code. </p>

<p> </p>

## -remarks
<p>The <b>ZwSetQuotaInformationFile</b> routine applies all of the quota entries in the specified <i>Buffer</i> parameter to the volume.</p>

<p>The <b>IoCheckQuotaBufferValidity</b> function can check whether the specified quota buffer passed as the <i>Buffer</i> parameter is valid.</p>

<p>A call to <b>ZwSetQuotaInformationFile</b> will result in an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549401">IRP_MJ_SET_QUOTA</a> request being sent to the device object that is associated with the file object whose handle is stored in the <i>FileHandle</i> parameter.</p>

<p>If the underlying file system does not support quota information (FAT and CDFS file systems, for example), <b>ZwSetQuotaInformationFile</b> will fail returning STATUS_INVALID_DEVICE_REQUEST.</p>

<p>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.</p>

<p>The <b>ZwSetQuotaInformationFile</b> routine applies all of the quota entries in the specified <i>Buffer</i> parameter to the volume.</p>

<p>The <b>IoCheckQuotaBufferValidity</b> function can check whether the specified quota buffer passed as the <i>Buffer</i> parameter is valid.</p>

<p>A call to <b>ZwSetQuotaInformationFile</b> will result in an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549401">IRP_MJ_SET_QUOTA</a> request being sent to the device object that is associated with the file object whose handle is stored in the <i>FileHandle</i> parameter.</p>

<p>If the underlying file system does not support quota information (FAT and CDFS file systems, for example), <b>ZwSetQuotaInformationFile</b> will fail returning STATUS_INVALID_DEVICE_REQUEST.</p>

<p>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.</p>

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
<p>Available in Windows 7 and later versions of Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or FltKernel.h)</dt>
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
<p>PASSIVE_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975204">PowerIrpDDis</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540298">FILE_GET_QUOTA_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540342">FILE_QUOTA_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548279">IoCheckQuotaBufferValidity</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549293">IRP_MJ_QUERY_QUOTA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549401">IRP_MJ_SET_QUOTA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567064">ZwQueryQuotaInformationFile</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwSetQuotaInformationFile routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>