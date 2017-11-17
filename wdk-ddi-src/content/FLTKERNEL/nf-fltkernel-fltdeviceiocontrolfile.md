---
UID: NF.fltkernel.FltDeviceIoControlFile
title: FltDeviceIoControlFile
author: windows-driver-content
description: FltDeviceIoControlFile sends a control code directly to a specified device driver, causing the corresponding driver to perform the specified action.
old-location: ifsk\fltdeviceiocontrolfile.htm
ms.assetid: f9a6998d-f340-47ad-a9be-ff7ef76c627e
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltDeviceIoControlFile
req.alt-loc: FltMgr.lib,FltMgr.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: FltDeviceIoControlFile
req.iface: 
---

# FltDeviceIoControlFile function



## -description
<p><b>FltDeviceIoControlFile</b> sends a control code directly to a specified device driver, causing the corresponding driver to perform the specified action. </p>


## -syntax

````
NTSTATUS FltDeviceIoControlFile(
  _In_      PFLT_INSTANCE Instance,
  _In_      PFILE_OBJECT  FileObject,
  _In_      ULONG         IoControlCode,
  _In_opt_  PVOID         InputBuffer,
  _In_      ULONG         InputBufferLength,
  _Out_     PVOID         OutputBuffer,
  _In_      ULONG         OutputBufferLength,
  _Out_opt_ PULONG        LengthReturned
);
````


## -parameters
<dl>

### -param <i>Instance</i> [in]

<dd>
<p>Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. </p>
</dd>

### -param <i>FileObject</i> [in]

<dd>
<p>File object pointer for the file or device that is the target of this request. This parameter is required and cannot be <b>NULL</b>. </p>
</dd>

### -param <i>IoControlCode</i> [in]

<dd>
<p>IOCTL_<i>XXX</i> code that indicates which device I/O operation is to be carried out. The value of this parameter determines the formats and required lengths of the <i>InputBuffer</i> and <i>OutputBuffer</i>, and it determines which of the following parameter pairs (<i>InputBuffer</i> and <i>InputBufferLength</i>, or <i>OutputBuffer</i> and <i>OutputBufferLength</i>) is required. </p>
</dd>

### -param <i>InputBuffer</i> [in, optional]

<dd>
<p>Pointer to a caller-allocated input buffer that contains device-specific information to be given to the target driver. If the <i>IoControlCode</i> parameter specifies an operation that does not require input data, this parameter is optional and can be <b>NULL</b>. </p>
</dd>

### -param <i>InputBufferLength</i> [in]

<dd>
<p>Size, in bytes, of the buffer at <i>InputBuffer</i>. This value is ignored if <i>InputBuffer</i> is <b>NULL</b>. </p>
</dd>

### -param <i>OutputBuffer</i> [out]

<dd>
<p>Pointer to a caller-allocated output buffer in which information is returned from the target driver. If the <i>IoControlCode</i> parameter specifies an operation that does not require output data, this parameter is optional and can be <b>NULL</b>. </p>
</dd>

### -param <i>OutputBufferLength</i> [in]

<dd>
<p>Size, in bytes, of the buffer at <i>OutputBuffer</i>. This value is ignored if <i>OutputBuffer</i> is <b>NULL</b>. </p>
</dd>

### -param <i>LengthReturned</i> [out, optional]

<dd>
<p>Pointer to a caller-allocated variable that receives the size, in bytes, of the information returned in the buffer at <i>OutputBuffer</i>. This parameter is optional and can be <b>NULL</b>. </p>
</dd>
</dl>

## -returns
<p><b>FltDeviceIoControlFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value. </p>

## -remarks
<p>For more information about the system-defined IOCTL_<i>XXX</i> codes, see the Remarks section of the reference entry for <b>DeviceIoControl</b> in the Microsoft Windows SDK documentation. </p>

<p>For more information about the system-defined IOCTL_<i>XXX</i> codes, see the Remarks section of the reference entry for <b>DeviceIoControl</b> in the Microsoft Windows SDK documentation. </p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542988">FltFsControlFile</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltDeviceIoControlFile function%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>