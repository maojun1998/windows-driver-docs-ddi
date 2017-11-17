---
UID: NC.ufxclient.EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE
title: EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE
author: windows-driver-content
description: The client driver's implementation to set or clear the specified power feature on the function controller.
old-location: buses\evt_ufx_device_super_speed_power_feature.htm
ms.assetid: 5A2B787B-13B8-48E9-B53E-7F6409820B88
ms.author: windowsdriverdev
ms.date: 11/3/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: usbref
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: PFN_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE
req.alt-loc: Ufxclient.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
ms.keywords: UFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.iface: 
req.product: Windows 10 or later.
---

# EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE callback



## -description
<p>The client driver's implementation to set or clear the specified power feature on the function controller. </p>


## -prototype

````
EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE EvtUfxDeviceSuperSpeedPowerFeature;

void EvtUfxDeviceSuperSpeedPowerFeature(
  _In_ UFXDEVICE UfxDevice,
  _In_ USHORT    Feature,
  _In_ BOOLEAN   Set
)
{ ... }

typedef EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE PFN_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE;
````


## -parameters
<dl>

### -param <i>UfxDevice</i> [in]

<dd>
<p>The handle to a  USB device object that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.</p>
</dd>

### -param <i>Feature</i> [in]

<dd>
<p>Feature selector for the power feature that is set or cleared, as defined in section 9.4 of the USB 3.0 Specification.  The feature selector can be one of these values: </p>
<ul>
<li>U1_ENABLE</li>
<li>U2_ENABLE
</li>
</ul>
</dd>

### -param <i>Set</i> [in]

<dd>
<p>If TRUE, set the feature.</p>
<p>If FALSE, clear the feature.</p>
</dd>
</dl>

## -returns
<p>This callback function does not return a value.</p>

## -remarks
<p>The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE</i> implementation with the USB function class extension (UFX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a> method.</p>

<p>This event callback is only required for controllers that support SuperSpeed operation.</p>

<p>The client driver indicates completion of this event by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a> method.</p>

<p>The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE</i> implementation with the USB function class extension (UFX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a> method.</p>

<p>This event callback is only required for controllers that support SuperSpeed operation.</p>

<p>The client driver indicates completion of this event by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a> method.</p>

## -requirements
<table>
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
<dt>Ufxclient.h</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE callback function%20 RELEASE:%20(11/3/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>