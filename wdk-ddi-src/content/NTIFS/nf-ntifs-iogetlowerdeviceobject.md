---
UID: NF.ntifs.IoGetLowerDeviceObject
title: IoGetLowerDeviceObject
author: windows-driver-content
description: The IoGetLowerDeviceObject routine returns a pointer to the next-lower-level device object on the driver stack.
old-location: ifsk\iogetlowerdeviceobject.htm
ms.assetid: 2446dfee-baa4-4f7b-a5a0-ff13bf45ce4b
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoGetLowerDeviceObject
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
ms.keywords: IoGetLowerDeviceObject
req.iface: 
---

# IoGetLowerDeviceObject function



## -description
<p>The <b>IoGetLowerDeviceObject</b> routine returns a pointer to the next-lower-level device object on the driver stack.</p>


## -syntax

````
PDEVICE_OBJECT IoGetLowerDeviceObject(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters
<dl>

### -param <i>DeviceObject</i> [in]

<dd>
<p>A pointer to the device object in the stack for which the next-lower-level device object is to be returned. </p>
</dd>
</dl>

## -returns
<p><b>IoGetLowerDeviceObject</b> returns a pointer to the next-lower-level device object on the driver stack. </p>

## -remarks
<p>Given a pointer to a device object in a file system or device driver stack, <b>IoGetLowerDeviceObject</b> returns a pointer to the next-lower-level device object on the stack.</p>

<p><b>IoGetLowerDeviceObject</b> returns <b>NULL</b> if: </p>

<p>The next-lower-level driver is not loaded. </p>

<p>The next-lower-level driver is currently being unloaded, removed, or deleted. </p>

<p>The device object pointed to by <i>DeviceObject</i> is the lowest device object in the driver stack. </p>

<p>A file system filter driver typically uses <b>IoGetLowerDeviceObject</b> to determine whether it is already attached to the filter driver stack that is chained above a given file system device object. First, the filter calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549145">IoGetAttachedDeviceReference</a> to get a pointer to the topmost device object in the stack. Then it calls <b>IoGetLowerDeviceObject</b> repeatedly to walk the driver stack, checking each device object to see whether the object belongs to the filter driver. </p>

<p><b>IoGetLowerDeviceObject</b> increments the reference count on the next-lower-level device object. Thus every successful call to <b>IoGetLowerDeviceObject</b> must be matched by a subsequent call <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>. </p>

<p>Given a pointer to a device object in a file system or device driver stack, <b>IoGetLowerDeviceObject</b> returns a pointer to the next-lower-level device object on the stack.</p>

<p><b>IoGetLowerDeviceObject</b> returns <b>NULL</b> if: </p>

<p>The next-lower-level driver is not loaded. </p>

<p>The next-lower-level driver is currently being unloaded, removed, or deleted. </p>

<p>The device object pointed to by <i>DeviceObject</i> is the lowest device object in the driver stack. </p>

<p>A file system filter driver typically uses <b>IoGetLowerDeviceObject</b> to determine whether it is already attached to the filter driver stack that is chained above a given file system device object. First, the filter calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549145">IoGetAttachedDeviceReference</a> to get a pointer to the topmost device object in the stack. Then it calls <b>IoGetLowerDeviceObject</b> repeatedly to walk the driver stack, checking each device object to see whether the object belongs to the filter driver. </p>

<p><b>IoGetLowerDeviceObject</b> increments the reference count on the next-lower-level device object. Thus every successful call to <b>IoGetLowerDeviceObject</b> must be matched by a subsequent call <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>. </p>

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
<p>This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later. </p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548359">IoGetAttachedDevice</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549145">IoGetAttachedDeviceReference</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoGetLowerDeviceObject routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>