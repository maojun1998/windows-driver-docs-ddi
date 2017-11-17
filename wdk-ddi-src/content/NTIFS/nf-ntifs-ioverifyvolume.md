---
UID: NF.ntifs.IoVerifyVolume
title: IoVerifyVolume
author: windows-driver-content
description: The IoVerifyVolume routine sends a volume verify request to the given removable-media device.
old-location: ifsk\ioverifyvolume.htm
ms.assetid: 46e29607-ee09-4db4-a501-68a3bc678e16
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoVerifyVolume
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
req.irql: < DISPATCH_LEVEL
ms.keywords: IoVerifyVolume
req.iface: 
---

# IoVerifyVolume function



## -description
<p>The <b>IoVerifyVolume</b> routine sends a volume verify request to the given removable-media device. </p>


## -syntax

````
NTSTATUS IoVerifyVolume(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ BOOLEAN        AllowRawMount
);
````


## -parameters
<dl>

### -param <i>DeviceObject</i> [in]

<dd>
<p>Pointer to the device object for the device on which the volume is to be verified. </p>
</dd>

### -param <i>AllowRawMount</i> [in]

<dd>
<p>Set to <b>TRUE</b> if this verify request is being issued on behalf of a DASD open request and a raw mount should be performed if the verify request fails.</p>
</dd>
</dl>

## -returns
<p><b>IoVerifyVolume</b> can return one of the following NTSTATUS values: </p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl><dl>
<dt><b>STATUS_WRONG_VOLUME</b></dt>
</dl><p> </p>

## -remarks
<p><b>IoVerifyVolume</b> sends a volume verify request to the given removable-media device. </p>

<p>If the verify operation fails, the I/O Manager sends a volume mount request to the device. </p>

<p>Before using <a href="https://msdn.microsoft.com/library/windows/hardware/ff548529">IoSetDeviceToVerify</a> and <b>IoVerifyVolume</b>, driver writers are strongly encouraged to study the way these routines are used in the FASTFAT sample. </p>

<p>For more information about removable-media devices, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563916">Supporting Removable Media</a>. </p>

<p><b>IoVerifyVolume</b> sends a volume verify request to the given removable-media device. </p>

<p>If the verify operation fails, the I/O Manager sends a volume mount request to the device. </p>

<p>Before using <a href="https://msdn.microsoft.com/library/windows/hardware/ff548529">IoSetDeviceToVerify</a> and <b>IoVerifyVolume</b>, driver writers are strongly encouraged to study the way these routines are used in the FASTFAT sample. </p>

<p>For more information about removable-media devices, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563916">Supporting Removable Media</a>. </p>

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
<p>&lt; DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549212">IoGetDeviceToVerify</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548529">IoSetDeviceToVerify</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoVerifyVolume routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>