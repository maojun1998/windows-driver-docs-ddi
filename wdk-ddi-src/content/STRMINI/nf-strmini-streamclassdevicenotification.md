---
UID: NF.strmini.StreamClassDeviceNotification
title: StreamClassDeviceNotification
author: windows-driver-content
description: Minidrivers use the StreamClassDeviceNotification routine to notify the class driver that it has completed a stream request, or that an event has occurred.
old-location: stream\streamclassdevicenotification.htm
ms.assetid: 80383159-c2c3-4d05-92e8-9245408e5243
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: stream
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StreamClassDeviceNotification
req.alt-loc: Stream.lib,Stream.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Stream.lib
req.dll: 
req.irql: 
ms.keywords: StreamClassDeviceNotification
req.iface: 
req.product: Windows 10 or later.
---

# StreamClassDeviceNotification function



## -description
<p>Minidrivers use the <b>StreamClassDeviceNotification</b> routine to notify the class driver that it has completed a stream request, or that an event has occurred.</p>


## -syntax

````
VOID  StreamClassDeviceNotification(
  _In_ STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE NotificationType,
  _In_ PVOID                                      HwDeviceExtension,
       PHW_STREAM_REQUEST_BLOCK                   pSrb,
       PKSEVENT_ENTRY                             EventEntry,
       GUID                                       *EventSet,
       ULONG                                      EventId
);
````


## -parameters
<dl>

### -param <i>NotificationType</i> [in]

<dd>
<p>This is an enumeration value that contains the type of notification that the minidriver is sending.</p>
<p></p>
<dl>

### -param <a id="DeviceRequestComplete"></a><a id="devicerequestcomplete"></a><a id="DEVICEREQUESTCOMPLETE"></a><b>DeviceRequestComplete</b>

<dd>
<p>Indicates that the minidriver has completed its handling of the device stream request block pointed to by the optional third argument of this routine, <i>pSrb</i>. Once the minidriver calls <b>StreamClassDeviceNotification</b> with this value, the relevant SRB is owned by the class driver, which is free to deallocate it.</p>
</dd>

### -param <a id="ReadyForNextDeviceRequest"></a><a id="readyfornextdevicerequest"></a><a id="READYFORNEXTDEVICEREQUEST"></a><b>ReadyForNextDeviceRequest</b>

<dd>
<p>Indicates that the minidriver is ready to receive another device request. </p>
</dd>

### -param <a id="SignalDeviceEvent"></a><a id="signaldeviceevent"></a><a id="SIGNALDEVICEEVENT"></a><b>SignalDeviceEvent</b>

<dd>
<p>Signals that the event specified by the <i>EventEntry</i> parameter has occurred.</p>
</dd>

### -param <a id="SignalMultipleDeviceEvents"></a><a id="signalmultipledeviceevents"></a><a id="SIGNALMULTIPLEDEVICEEVENTS"></a><b>SignalMultipleDeviceEvents</b>

<dd>
<p>Signals all events that match the criteria specified in the <i>EventSet</i> and <i>EventId</i> parameters.</p>
</dd>

### -param <a id="DeleteDeviceEvent"></a><a id="deletedeviceevent"></a><a id="DELETEDEVICEEVENT"></a><b>DeleteDeviceEvent</b>

<dd>
<p>Deletes the event specified by the <i>EventEntry</i> parameter. </p>
</dd>
</dl>
</dd>

### -param <i>HwDeviceExtension</i> [in]

<dd>
<p>Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559682">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>. The class driver then passes pointers to the buffer in the <b>HwDeviceExtension</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559702">HW_STREAM_REQUEST_BLOCK</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff559697">HW_STREAM_OBJECT</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff559706">HW_TIME_CONTEXT</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567785">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.</p>
</dd>

### -param <i>pSrb</i> 

<dd>
<p>Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff559702">HW_STREAM_REQUEST_BLOCK</a> structure. If <i>NotificationType</i> equals <b>DeviceRequestComplete</b>, this parameter points to the stream request block that the minidriver has completed processing. After <b>StreamClassDeviceNotification</b> completes, this address is no longer valid.</p>
</dd>

### -param <i>EventEntry</i> 

<dd>
<p>If <i>NotificationType</i> equals either SignalDeviceEvent or DeleteDeviceEvent, points to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff561853">KSEVENT_ENTRY</a> that specifies the event to be signaled or deleted. </p>
</dd>

### -param <i>EventSet</i> 

<dd>
<p>Specifies the event set to match against in the device event queue if <i>NotificationType</i> equals <b>SignalMultipleDeviceEvents</b>. </p>
</dd>

### -param <i>EventId</i> 

<dd>
<p>Specifies the event ID to match against in the device event queue if <i>NotificationType</i> equals <b>SignalMultipleDeviceEvents</b>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The minidriver uses this routine for requests or events that apply to the minidriver as a whole. Stream-specific requests or events use <a href="https://msdn.microsoft.com/library/windows/hardware/ff568266">StreamClassStreamNotification</a>.</p>

<p>The minidriver uses this routine for requests or events that apply to the minidriver as a whole. Stream-specific requests or events use <a href="https://msdn.microsoft.com/library/windows/hardware/ff568266">StreamClassStreamNotification</a>.</p>

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
<dt>Strmini.h (include Strmini.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Stream.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568266">StreamClassStreamNotification</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20StreamClassDeviceNotification routine%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>