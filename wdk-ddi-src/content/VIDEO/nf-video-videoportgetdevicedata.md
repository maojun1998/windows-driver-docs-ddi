---
UID: NF.video.VideoPortGetDeviceData
title: VideoPortGetDeviceData
author: windows-driver-content
description: The VideoPortGetDeviceData function retrieves system-detected configuration information from the ..\Machine\Hardware\Description tree in the registry.
old-location: display\videoportgetdevicedata.htm
ms.assetid: 95df7ed6-ac9e-4620-bc3c-54e45a123fdc
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: display
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VideoPortGetDeviceData
req.alt-loc: Videoprt.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
ms.keywords: VideoPortGetDeviceData
req.iface: 
req.product: Windows 10 or later.
---

# VideoPortGetDeviceData function



## -description
<p>The <b>VideoPortGetDeviceData</b> function retrieves system-detected configuration information from the <b>..\Machine\Hardware\Description</b> tree in the registry. This information is bus-specific or adapter-specific and stored in the registry by the system loader or the HAL.</p>


## -syntax

````
VP_STATUS VideoPortGetDeviceData(
   PVOID                          HwDeviceExtension,
   VIDEO_DEVICE_DATA_TYPE         DeviceDataType,
   PMINIPORT_QUERY_DEVICE_ROUTINE CallbackRoutine,
   PVOID                          Context
);
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> 

<dd>
<p>Pointer to the miniport driver's device extension.</p>
</dd>

### -param <i>DeviceDataType</i> 

<dd>
<p>Specifies the type of data being requested as a VIDEO_DEVICE_DATA_TYPE value, typically one of <b>VpBusData</b>, <b>VpControllerData</b>, or <b>VpMonitorData.</b></p>
<p>The <b>VpControllerData</b> and <b>VpMonitorData</b> values are relevant only on ARC-compliant platforms. Miniport drivers of x86-type video adapters generally specify <b>VpBusData</b>, particularly for adapters on EISA buses. The <b>VpMachineData</b> value is reserved for future use.</p>
</dd>

### -param <i>CallbackRoutine</i> 

<dd>
<p>Pointer to a driver-supplied <a href="https://msdn.microsoft.com/81c3f484-427e-43b8-b7dd-12017533560b">HwVidQueryDeviceCallback</a> function to be called with the requested information.</p>
</dd>

### -param <i>Context</i> 

<dd>
<p>Pointer to a caller-determined context parameter to be passed to the <i>CallbackRoutine</i>. It typically points to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a> buffer.</p>
</dd>
</dl>

## -returns
<p><b>VideoPortGetDeviceData</b> returns NO_ERROR if it successfully called the miniport driver's <i>HwVidQueryDeviceCallback</i> function with configuration information.</p>

## -remarks
<p><b>VideoPortGetDeviceData</b> cannot be called from a miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/bd41bbbf-4ec8-4e6c-8620-d8a9fe0b8bad">HwVidTimer</a> functions, or from <a href="https://msdn.microsoft.com/library/windows/hardware/ff570339">VideoPortQueueDpc</a>, or from a callback to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570372">VideoPortSynchronizeExecution</a>.</p>

<p>The registry tree from which <b>VideoPortGetDeviceData</b> retrieves configuration information is <i>volatile</i>; that is, it is re-created by the system loader or HAL every time the system is loaded. Because this information is collected and stored early in the boot process, the bus-relative configuration information returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570306">VideoPortGetBusData</a> can be more complete. </p>

<p><b>VideoPortGetDeviceData</b> cannot be called from a miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/bd41bbbf-4ec8-4e6c-8620-d8a9fe0b8bad">HwVidTimer</a> functions, or from <a href="https://msdn.microsoft.com/library/windows/hardware/ff570339">VideoPortQueueDpc</a>, or from a callback to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570372">VideoPortSynchronizeExecution</a>.</p>

<p>The registry tree from which <b>VideoPortGetDeviceData</b> retrieves configuration information is <i>volatile</i>; that is, it is re-created by the system loader or HAL every time the system is loaded. Because this information is collected and stored early in the boot process, the bus-relative configuration information returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570306">VideoPortGetBusData</a> can be more complete. </p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 2000 and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
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
<a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/81c3f484-427e-43b8-b7dd-12017533560b">HwVidQueryDeviceCallback</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570316">VideoPortGetRegistryParameters</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortGetDeviceData function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>