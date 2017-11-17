---
UID: NF.wdfdevice.WdfDeviceResumeIdle
title: WdfDeviceResumeIdle
author: windows-driver-content
description: The WdfDeviceResumeIdle method informs the framework that the specified device is not in use and can be placed in a device low-power state if it remains idle.
old-location: wdf\wdfdeviceresumeidle.htm
ms.assetid: d63848e8-0e6a-4ad7-a147-8804869b9c9b
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfDeviceResumeIdle
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); 
WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: WdfDeviceResumeIdle
req.iface: 
req.product: Windows 10 or later.
---

# WdfDeviceResumeIdle function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WdfDeviceResumeIdle</b> method informs the framework that the specified device is not in use and can be placed in a device low-power state if it remains idle.</p>


## -syntax

````
VOID WdfDeviceResumeIdle(
  _In_ WDFDEVICE Device
);
````


## -parameters
<dl>

### -param <i>Device</i> [in]

<dd>
<p>A handle to a framework device object.</p>
</dd>
</dl>

## -returns
<p>None.</p>

<p>A bug check occurs if the driver supplies an invalid object handle.</p>

## -remarks
<p>Every call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546921">WdfDeviceStopIdle</a> must eventually be followed by a call to <b>WdfDeviceResumeIdle</b>, or else the device will never return to a low-power state if it again becomes idle.</p>

<p>Calling <a href="https://msdn.microsoft.com/library/windows/hardware/dn932459">WdfDeviceResumeIdleWithTag</a> instead of <b>WdfDeviceResumeIdle</b> provides additional information (tag value, line number, and file name) that you can view in Microsoft debuggers.</p>

<p>The following code example informs the framework that the specified device is not in use and can be placed in a device low-power state if it remains idle.</p>

<p>Every call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546921">WdfDeviceStopIdle</a> must eventually be followed by a call to <b>WdfDeviceResumeIdle</b>, or else the device will never return to a low-power state if it again becomes idle.</p>

<p>Calling <a href="https://msdn.microsoft.com/library/windows/hardware/dn932459">WdfDeviceResumeIdleWithTag</a> instead of <b>WdfDeviceResumeIdle</b> provides additional information (tag value, line number, and file name) that you can view in Microsoft debuggers.</p>

<p>The following code example informs the framework that the specified device is not in use and can be placed in a device low-power state if it remains idle.</p>

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
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.debugging_power_reference_leaks_in_wdf">Debugging Power Reference Leaks in WDF</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn932459">WdfDeviceResumeIdleWithTag</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546921">WdfDeviceStopIdle</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn932460">WdfDeviceStopIdleWithTag</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceResumeIdle method%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>