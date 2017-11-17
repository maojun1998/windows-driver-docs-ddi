---
UID: NF.wdfdevice.WdfDeviceGetDevicePowerPolicyState
title: WdfDeviceGetDevicePowerPolicyState
author: windows-driver-content
description: The WdfDeviceGetDevicePowerPolicyState method returns the current state of the framework's power policy state machine, for a specified device.
old-location: wdf\wdfdevicegetdevicepowerpolicystate.htm
ms.assetid: 3a4aab60-6568-4017-acad-ca643cb4d661
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
req.umdf-ver: 
req.alt-api: WdfDeviceGetDevicePowerPolicyState
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: WdfDeviceGetDevicePowerPolicyState
req.iface: 
req.product: Windows 10 or later.
---

# WdfDeviceGetDevicePowerPolicyState function



## -description
<p class="CCE_Message">[Applies to KMDF only]</p>
<p>The <b>WdfDeviceGetDevicePowerPolicyState</b> method returns the current state of the framework's power policy state machine, for a specified device.</p>


## -syntax

````
WDF_DEVICE_POWER_POLICY_STATE WdfDeviceGetDevicePowerPolicyState(
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
<p><b>WdfDeviceGetDevicePowerPolicyState</b> returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551275">WDF_DEVICE_POWER_POLICY_STATE</a>-typed enumerator that identifies the current state of the framework's power policy state machine for the specified device. </p>

<p>A bug check occurs if the driver supplies an invalid object handle.</p>

## -remarks
<p>Most drivers do not need to be aware of the state of the framework's power policy state machine. For more information about the framework's state machines, see <a href="wdf.state_machines_in_the_framework">State Machines in the Framework</a>.</p>

<p>The <b>WdfDeviceGetDevicePowerPolicyState</b> method returns a meaningful value only if it is called from within the callback functions that the driver registers when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff546774">WdfDeviceInitSetPowerPolicyEventCallbacks</a>.</p>

<p>The following code example obtains the current state of the framework's power policy state machine for a specified device.</p>

<p>Most drivers do not need to be aware of the state of the framework's power policy state machine. For more information about the framework's state machines, see <a href="wdf.state_machines_in_the_framework">State Machines in the Framework</a>.</p>

<p>The <b>WdfDeviceGetDevicePowerPolicyState</b> method returns a meaningful value only if it is called from within the callback functions that the driver registers when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff546774">WdfDeviceInitSetPowerPolicyEventCallbacks</a>.</p>

<p>The following code example obtains the current state of the framework's power policy state machine for a specified device.</p>

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
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545985">WdfDeviceGetDevicePowerState</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545969">WdfDeviceGetDevicePnpState</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546966">WdfDevStateNormalize</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceGetDevicePowerPolicyState method%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>