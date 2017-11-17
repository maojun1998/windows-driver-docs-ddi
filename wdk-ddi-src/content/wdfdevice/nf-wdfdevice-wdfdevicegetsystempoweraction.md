---
UID: NF.wdfdevice.WdfDeviceGetSystemPowerAction
title: WdfDeviceGetSystemPowerAction
author: windows-driver-content
description: The WdfDeviceGetSystemPowerAction method returns the system power action, if any, that is currently occurring for the computer.
old-location: wdf\wdfdevicegetsystempoweraction.htm
ms.assetid: 5c4e44cd-94a3-4265-b195-7a5711d8035d
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
req.kmdf-ver: 1.9
req.umdf-ver: 2.0
req.alt-api: WdfDeviceGetSystemPowerAction
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
ms.keywords: WdfDeviceGetSystemPowerAction
req.iface: 
req.product: Windows 10 or later.
---

# WdfDeviceGetSystemPowerAction function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WdfDeviceGetSystemPowerAction</b> method returns the <a href="https://msdn.microsoft.com/e8ab99d4-c18d-4ba8-bfe8-8eebb881c384">system power action</a>, if any, that is currently occurring for the computer. </p>


## -syntax

````
POWER_ACTION WdfDeviceGetSystemPowerAction(
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
<p><b>WdfDeviceGetSystemPowerAction</b> returns a POWER_ACTION-typed enumerator value. The value indicates the <a href="https://msdn.microsoft.com/e8ab99d4-c18d-4ba8-bfe8-8eebb881c384">system power action</a> that is currently occurring for the computer. For more information, see the following Remarks section. The POWER_ACTION enumeration is defined in <i>wdm.h</i>.</p>

<p>A bug check occurs if the driver supplies an invalid object handle.</p>

## -remarks
<p>The <b>WdfDeviceGetSystemPowerAction</b> method enables a driver to determine whether a device's power transition is occurring because the device is idle (or waking up), or because the entire computer is entering (or leaving) a low-power state. </p>

<p>The driver must call <b>WdfDeviceGetSystemPowerAction</b> only from the event callback functions that the framework calls when the device is <a href="wdf.a_device_enters_a_low_power_state">entering a low-power state</a> or <a href="wdf.a_device_returns_to_its_working_state">returning to its working state</a>. </p>

<p>The value that <b>WdfDeviceGetSystemPowerAction</b> returns depends on the following situations:</p>

<p>If the computer is entering a low-power state when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns the reason that the computer is entering the low-power state. For example, the method returns <b>PowerActionSleep</b> if the computer is entering its S1, S2, or S3 low-power state.</p>

<p>If the computer is returning to its working (S0) state from a low-power state when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns the reason that the computer entered the low-power state. For example, the method returns <b>PowerActionSleep</b> if the computer is leaving its S1, S2, or S3 low-power state.</p>

<p>If the computer is powering up (after having been turned off) when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns <b>PowerActionNone</b>.</p>

<p>If the device is entering a low-power idle state or returning to its working (D0) state when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, while the rest of the system remains at its working (S0) state, the method returns <b>PowerActionNone</b>.</p>

<p>If the computer and the device are both in their working states when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns <b>PowerActionNone</b>.</p>

<p>For more information about low-power states, see <a href="wdf.a_device_enters_a_low_power_state">A Device Enters a Low-Power State</a>.</p>

<p>The following code example obtains the power transition activity that is currently occurring for the computer.</p>

<p>The <b>WdfDeviceGetSystemPowerAction</b> method enables a driver to determine whether a device's power transition is occurring because the device is idle (or waking up), or because the entire computer is entering (or leaving) a low-power state. </p>

<p>The driver must call <b>WdfDeviceGetSystemPowerAction</b> only from the event callback functions that the framework calls when the device is <a href="wdf.a_device_enters_a_low_power_state">entering a low-power state</a> or <a href="wdf.a_device_returns_to_its_working_state">returning to its working state</a>. </p>

<p>The value that <b>WdfDeviceGetSystemPowerAction</b> returns depends on the following situations:</p>

<p>If the computer is entering a low-power state when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns the reason that the computer is entering the low-power state. For example, the method returns <b>PowerActionSleep</b> if the computer is entering its S1, S2, or S3 low-power state.</p>

<p>If the computer is returning to its working (S0) state from a low-power state when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns the reason that the computer entered the low-power state. For example, the method returns <b>PowerActionSleep</b> if the computer is leaving its S1, S2, or S3 low-power state.</p>

<p>If the computer is powering up (after having been turned off) when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns <b>PowerActionNone</b>.</p>

<p>If the device is entering a low-power idle state or returning to its working (D0) state when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, while the rest of the system remains at its working (S0) state, the method returns <b>PowerActionNone</b>.</p>

<p>If the computer and the device are both in their working states when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns <b>PowerActionNone</b>.</p>

<p>For more information about low-power states, see <a href="wdf.a_device_enters_a_low_power_state">A Device Enters a Low-Power State</a>.</p>

<p>The following code example obtains the power transition activity that is currently occurring for the computer.</p>

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
<p>1.9</p>
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