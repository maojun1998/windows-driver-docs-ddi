---
UID: NS.wdfdevice._WDF_DEVICE_PNP_NOTIFICATION_DATA
title: WDF_DEVICE_PNP_NOTIFICATION_DATA
author: windows-driver-content
description: The WDF_DEVICE_PNP_NOTIFICATION_DATA structure describes a state change within a device's Plug and Play state machine.
old-location: wdf\wdf_device_pnp_notification_data.htm
ms.assetid: b49431bf-4b44-4d7b-b3a6-c3d7416bcb53
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WDF_DEVICE_PNP_NOTIFICATION_DATA
req.alt-loc: wdfdevice.h
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
ms.keywords: WDF_DEVICE_PNP_NOTIFICATION_DATA, WDF_DEVICE_PNP_NOTIFICATION_DATA
req.iface: 
req.product: Windows 10 or later.
---

# WDF_DEVICE_PNP_NOTIFICATION_DATA structure



## -description
<p class="CCE_Message">[Applies to KMDF only]</p>
<p>The WDF_DEVICE_PNP_NOTIFICATION_DATA structure describes a state change within a device's Plug and Play state machine.</p>


## -syntax

````
typedef struct _WDF_DEVICE_PNP_NOTIFICATION_DATA {
  WDF_STATE_NOTIFICATION_TYPE Type;
  union {
    struct {
      WDF_DEVICE_PNP_STATE CurrentState;
      WDF_DEVICE_PNP_STATE NewState;
    } EnterState;
    struct {
      WDF_DEVICE_PNP_STATE CurrentState;
    } PostProcessState;
    struct {
      WDF_DEVICE_PNP_STATE CurrentState;
      WDF_DEVICE_PNP_STATE NewState;
    } LeaveState;
  } Data;
} WDF_DEVICE_PNP_NOTIFICATION_DATA;
````


## -struct-fields
<dl>

### -field <b>Type</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552513">WDF_STATE_NOTIFICATION_TYPE</a>-typed enumerator that identifies the type of state change that is being reported.</p>
</dd>

### -field <b>Data</b>

<dd>
<dl>

### -field <b>EnterState</b>

<dd>
<dl>


</dl>
<dl>

### -field <b>CurrentState</b>

<dd>
<p>If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="https://msdn.microsoft.com/library/windows/hardware/ff551262">WDF_DEVICE_PNP_STATE</a>-typed enumerator identifies the state machine's current state.</p>
</dd>

### -field <b>NewState</b>

<dd>
<p>If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="https://msdn.microsoft.com/library/windows/hardware/ff551262">WDF_DEVICE_PNP_STATE</a>-typed enumerator identifies the state machine's next state.</p>
</dd>
</dl>
</dd>

### -field <b>PostProcessState</b>

<dd>
<dl>


</dl>
<dl>

### -field <b>CurrentState</b>

<dd>
<p>If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="https://msdn.microsoft.com/library/windows/hardware/ff551262">WDF_DEVICE_PNP_STATE</a>-typed enumerator identifies the state machine's current state.</p>
</dd>
</dl>
</dd>

### -field <b>LeaveState</b>

<dd>
<dl>


</dl>
<dl>

### -field <b>CurrentState</b>

<dd>
<p>If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="https://msdn.microsoft.com/library/windows/hardware/ff551262">WDF_DEVICE_PNP_STATE</a>-typed enumerator identifies the state machine's current state.</p>
</dd>

### -field <b>NewState</b>

<dd>
<p>If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="https://msdn.microsoft.com/library/windows/hardware/ff551262">WDF_DEVICE_PNP_STATE</a>-typed enumerator identifies the state machine's next state.</p>
</dd>
</dl>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>The WDF_DEVICE_PNP_NOTIFICATION_DATA structure is an input argument to a driver's <a href="https://msdn.microsoft.com/5f08d331-0e58-45a3-93a3-b5e9a40b5af3">EvtDevicePnpStateChange</a> callback function.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546057">WdfDeviceInitRegisterPnpStateChangeCallback</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_PNP_NOTIFICATION_DATA structure%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>