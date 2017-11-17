---
UID: NF.usbcamdi.USBCAMD_DriverEntry
title: USBCAMD_DriverEntry
author: windows-driver-content
description: The USBCAMD_DriverEntry function registers the minidriver with USBCAMD, effectively binding USBCAMD and the minidriver together.
old-location: stream\usbcamd_driverentry.htm
ms.assetid: ac77b121-2495-4739-8c8f-96d6c48e4dc6
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: stream
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBCAMD_DriverEntry
req.alt-loc: usbcamd2.lib,usbcamd2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Usbcamd2.lib
req.dll: 
req.irql: 
ms.keywords: USBCAMD_DriverEntry
req.iface: 
req.product: Windows 10 or later.
---

# USBCAMD_DriverEntry function



## -description
<p>The <b>USBCAMD_DriverEntry</b> function registers the minidriver with USBCAMD, effectively binding USBCAMD and the minidriver together.</p>


## -syntax

````
ULONG USBCAMD_DriverEntry(
  _In_ PVOID                           Context1,
  _In_ PVOID                           Context2,
  _In_ ULONG                           DeviceContextSize,
  _In_ ULONG                           FrameContextSize,
  _In_ PADAPTER_RECEIVE_PACKET_ROUTINE ReceivePacket
);
````


## -parameters
<dl>

### -param <i>Context1</i> [in]

<dd>
<p>Pointer to the first argument that is passed to the camera minidriver's DriverEntry function. This is effectively a pointer to the driver object that is created by the system and passed to DriverEntry.</p>
</dd>

### -param <i>Context2</i> [in]

<dd>
<p>Pointer to the second argument that is passed to the camera minidriver's DriverEntry function. This is effectively a pointer to the registry path that describes the minidriver's registry key.</p>
</dd>

### -param <i>DeviceContextSize</i> [in]

<dd>
<p>Specifies the size, in bytes, required for the minidriver's device-specific context.</p>
</dd>

### -param <i>FrameContextSize</i> [in]

<dd>
<p>Specifies the size, in bytes, required for the minidriver's frame-specific context structure. Use <b>NULL</b> if not needed.</p>
</dd>

### -param <i>ReceivePacket</i> [in]

<dd>
<p>Pointer to the minidriver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff554080">AdapterReceivePacket</a> function that handles adapter-based SRB requests.</p>
</dd>
</dl>

## -returns
<p><b>USBCAMD_DriverEntry </b>returns the status of the registration attempt. If a value other than STATUS_SUCCESS is returned, the minidriver is unloaded.</p>

## -remarks
<p>A camera minidriver must call <b>USBCAMD_DriverEntry</b> from the minidriver's <b>DriverEntry</b> routine. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558717">DriverEntry for Stream Class Minidrivers</a>
</p>

<p><i>FrameContextSize</i> is optional. A non-<b>NULL</b> value should be provided only with calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff557617">CamNewVideoFrame</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff557623">CamProcessRawVideoFrame</a>.</p>

<p>A camera minidriver must call <b>USBCAMD_DriverEntry</b> from the minidriver's <b>DriverEntry</b> routine. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558717">DriverEntry for Stream Class Minidrivers</a>
</p>

<p><i>FrameContextSize</i> is optional. A non-<b>NULL</b> value should be provided only with calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff557617">CamNewVideoFrame</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff557623">CamProcessRawVideoFrame</a>.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Usbcamdi.h (include Usbcamdi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Usbcamd2.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557617">CamNewVideoFrame</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557623">CamProcessRawVideoFrame</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554080">AdapterReceivePacket</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_DriverEntry function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>