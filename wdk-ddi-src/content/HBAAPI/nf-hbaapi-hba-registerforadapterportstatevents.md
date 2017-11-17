---
UID: NF.hbaapi.HBA_RegisterForAdapterPortStatEvents
title: HBA_RegisterForAdapterPortStatEvents
author: windows-driver-content
description: The HBA_RegisterForAdapterPortStatEvents routine registers the indicated user callback routine to call when a port statistics event occurs.
old-location: storage\hba_registerforadapterportstatevents.htm
ms.assetid: 82598ba4-6e01-44eb-9359-4b85e8f7980c
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: Storage
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_RegisterForAdapterPortStatEvents
req.alt-loc: Hbaapi.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
ms.keywords: HBA_RegisterForAdapterPortStatEvents
req.iface: 
---

# HBA_RegisterForAdapterPortStatEvents function



## -description
<p>The <b>HBA_RegisterForAdapterPortStatEvents</b> routine registers the indicated user callback routine to call when a port statistics event occurs. </p>


## -syntax

````
HBA_STATUS HBA_API HBA_RegisterForAdapterPortStatEvents(
   HBA_PORTSTAT_CALLBACK callback,
   void                  *userData,
   HBA_HANDLE            handle,
   HBA_WWN               PortWWN,
   PHBA_PORTSTATISTICS   stats,
   HBA_UINT32            statType,
   HBA_CALLBACKHANDLE    *callbackHandle
);
````


## -parameters
<dl>

### -param <i>callback</i> 

<dd>
<p>Pointer to a callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557117">HBA_PORTSTAT_CALLBACK</a> that is called when an adapter is added to the system.</p>
</dd>

### -param <i>userData</i> 

<dd>
<p>Pointer to a buffer that is passed to the callback routine with each event. This data correlates the event with the source of the event registration. </p>
</dd>

### -param <i>handle</i> 

<dd>
<p>Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA for which the adapter events are generated. </p>
</dd>

### -param <i>PortWWN</i> 

<dd>
<p>Contains a 64-bit worldwide name (WWN) that uniquely identifies the HBA port from which port events are reported. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.</p>
</dd>

### -param <i>stats</i> 

<dd>
<p>Pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557110">HBA_PortStatistics</a> that, on input, holds the statistical levels that determine when port statistics events are generated. On output, this member holds statistical data gathered for the port referenced by <i>PortWWN. </i></p>
</dd>

### -param <i>statType</i> 

<dd>
<p>Holds a value that indicates the mechanism used to trigger port statistics events. If the value is HBA_EVENT_PORT_STAT_THRESHOLD, then each non-NULL member of the HBA_PortStatistics structure pointed to by <i>stats </i>will indicate the threshold at which an event is generated for that particular statistical parameter. For example, if the <b>TxWords</b> member of the HBA_PortStatistics structure holds a value of 1,000,000, then an event will be generated once 1,000,000 words have been transmitted.</p>
<p>If the value of <i>statType </i>is HBA_EVENT_PORT_STAT_GROWTH, then the values in the HBA_PortStatistics structure will be interpreted as growth-rate numbers. The T11 committee's <i>Fibre Channel HBA API</i> specification recommends that port statistics be checked once a minute, and if the value or a given statistics parameter has grown by more than the number indicated for that parameter in HBA_PortStatistics, an event is generated, but the actual frequency with which growth is monitored is hardware-specific.</p>
</dd>

### -param <i>callbackHandle</i> 

<dd>
<p>Pointer to an opaque identifier that the user must pass to <a href="https://msdn.microsoft.com/library/windows/hardware/ff557175">HBA_RemoveCallback</a> to de-register the callback routine.</p>
</dd>
</dl>

## -returns
<p>The <b>HBA_RegisterForAdapterPortStatEvents</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, this member should have one of the following values.</p><dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl><p>Returned if the callback routine was successfully registered. </p><dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl><p>Returned if the HBA referenced by <i>handle</i> does not have a port with a name that matches the value in <i>PortWWN</i>.</p><dl>
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl><p>Returned if the hardware does not support statistic events. </p><dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl><p>Returned if an unspecified error occurred that prevented the registration of the callback routine. </p>

<p> </p>

## -remarks


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
<dt>Hbaapi.h (include Hbaapi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Hbaapi.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Hbaapi.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557117">HBA_PORTSTAT_CALLBACK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557110">HBA_PortStatistics</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20HBA_RegisterForAdapterPortStatEvents routine%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>