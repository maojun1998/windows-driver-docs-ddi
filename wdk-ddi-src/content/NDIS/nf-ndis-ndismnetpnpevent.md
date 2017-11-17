---
UID: NF.ndis.NdisMNetPnPEvent
title: NdisMNetPnPEvent
author: windows-driver-content
description: NDIS miniport drivers (and intermediate drivers that are registered as miniport drivers) call the NdisMNetPnPEvent function to originate a network Plug and Play event, an NDIS PnP event, or Power Management event or propagate it to overlying drivers.
old-location: netvista\ndismnetpnpevent.htm
ms.assetid: cbb097c1-dd20-4c6d-b23a-1e7683ac3e94
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMNetPnPEvent
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Protocol_Driver_Function, NdisMNetPnPEventInOIDRequest
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: NdisMNetPnPEvent
req.iface: 
---

# NdisMNetPnPEvent function



## -description
<p>NDIS miniport drivers (and intermediate drivers that are registered as miniport drivers) call the 
  <b>NdisMNetPnPEvent</b> function to originate a network Plug and Play event, an NDIS PnP event,
  or Power Management event or propagate it to overlying drivers.</p>


## -syntax

````
NDIS_STATUS NdisMNetPnPEvent(
  _In_ NDIS_HANDLE                 MiniportAdapterHandle,
  _In_ PNET_PNP_EVENT_NOTIFICATION NetPnPEvent
);
````


## -parameters
<dl>

### -param <i>MiniportAdapterHandle</i> [in]

<dd>
<p>An NDIS handle which NDIS provided at the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function.
     This handle identifies the miniport adapter that is affected by the event. If the caller is an
     intermediate driver, this is the handle of the virtual miniport.</p>
</dd>

### -param <i>NetPnPEvent</i> [in]

<dd>
<p>A pointer to a 
     <a href="https://msdn.microsoft.com/58d3baf3-a1fa-42ae-b795-2774a148aeda">
     NET_PNP_EVENT_NOTIFICATION</a> structure, which describes the network Plug and Play event, NDIS PnP
     event, or Power Management event.</p>
</dd>
</dl>

## -returns
<p><b>NdisMNetPnPEvent</b> can return the following:</p><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p>The overlying drivers successfully processed the Plug and Play or Power Management event.</p><dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><p>The overlying drivers could not obtain the necessary system resources to satisfy the indicated
       Plug and Play or Power Management event.</p><dl>
<dt><b>NDIS_STATUS_INVALID_PARAMETER</b></dt>
</dl><p>NDIS failed the call because some of the input parameters are invalid.</p><dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl><p>NDIS 6.0 and later protocol drivers must not return this status. An NDIS 5.<i>x</i> protocol driver that does
       not support Plug and Play can return this status in response to a 
       <b>NetEventSetPower</b> to indicate that NDIS should unbind it from the underlying adapter.</p><dl>
<dt><b>NDIS_STATUS_INVALID_PORT</b></dt>
</dl><p>NDIS failed the request because an invalid NDIS port was specified in a 
       <b>NetEventPortActivation</b> or 
       <b>NetEventPortDeactivation</b> PnP event.</p><dl>
<dt><b>NDIS_STATUS_INVALID_PORT_STATE</b></dt>
</dl><p>NDIS failed the request because an NDIS port was in an invalid port state. The ports are
       specified in a 
       <b>NetEventPortActivation</b> or 
       <b>NetEventPortDeactivation</b> PnP event.</p><dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl><p>The overlying drivers' attempts to process the propagated Plug and Play or Power Management
       event failed.</p>

<p> </p>

<p>The return value is significant only when the propagated event is a 
      <b>NetEventQueryPower</b> or 
      <b>NetEventQueryRemoveDevice</b> event. For all other propagated events, the return value is always
      NDIS_STATUS_SUCCESS.</p>

<p>If the event is 
      <b>NetEventPortActivation</b> and the call fails, the caller should not use the associated ports in
      receive indications or status indications.</p>

## -remarks
<p>Any miniport driver can call 
    <b>NdisMNetPnPEvent</b> to generate 
    <b>NetEventPortActivation</b> and 
    <b>NetEventPortDeactivation</b> events. Only intermediate drivers can make other event notifications.</p>

<p>To propagate notification of a network Plug and Play event, an NDIS PnP event, or Power Management
    event to overlying drivers, an NDIS intermediate driver calls 
    <b>NdisMNetPnPEvent</b> in the context of the driver's 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function.</p>

<p>If the propagated event is a 
    <b>NetEventQueryPower</b> or a 
    <b>NetEventQueryRemoveDevice</b>, the intermediate driver must check the NDIS_STATUS value that is
    returned by 
    <b>NdisMNetPnPEvent</b>. If the returned status is NDIS_STATUS_SUCCESS, the intermediate driver should
    handle the event and then return NDIS_STATUS_SUCCESS from its 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function. If the returned status is not NDIS_STATUS_SUCCESS, the intermediate
    driver should return the reported status from its 
    <i>ProtocolNetPnPEvent</i> function without further processing.</p>

<p>How the intermediate driver processes a 
    <b>NetEventSetPower</b> received by its 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function depends on the specified device power state. If the specified device
    power state is 
    <b>NdisDeviceStateD0</b>, the intermediate driver should handle the event and then call 
    <b>NdisMNetPnPEvent</b>. For any other specified device power state, the intermediate driver should first
    call 
    <b>NdisMNetPnPEvent</b> and then handle the event.</p>

<p>An intermediate driver should call 
    <b>NdisMNetPnPEvent</b> to propagate a 
    <b>NetEventReconfigure</b> or 
    <b>NetEventBindList</b> only if the 
    <b>NetEventReconfigure</b> or 
    <b>NetEventBindList</b> is indicated on a non-<b>NULL</b>
<i>ProtocolBindingContext</i>. If a 
    <b>NetEventReconfigure</b> or 
    <b>NetEventBindList</b> is indicated on a <b>NULL</b>
<i>ProtocolBindingContext</i>, the intermediate driver should not call 
    <b>NdisMNetPnPEvent</b> to propagate the event.</p>

<p>If an intermediate driver handles a 
    <b>NetEventReconfigure</b> or a 
    <b>NetEventBindList</b>, it should validate any data associated with the event.</p>

<p>An intermediate driver should not propagate the 
    <b>NetEventBindsComplete</b>, 
    <b>NetEventPause</b>, 
    <b>NetEventRestart</b>, 
    <b>NetEventPortActivation</b>, or 
    <b>NetEventPortDeactivation</b> events by calling 
    <b>NdisMNetPnPEvent</b>.</p>

<p>An NDIS intermediate driver can generate its own NDIS port events for virtual miniports as
    appropriate for the 
    <b>NetEventPortActivation</b> or 
    <b>NetEventPortDeactivation</b> events that it receives at its 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function.</p>

<p>For all other propagated events, the intermediate driver's 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function should propagate the status value that is returned by 
    <b>NdisMNetPnPEvent</b>.</p>

<p>Any miniport driver can call 
    <b>NdisMNetPnPEvent</b> to generate 
    <b>NetEventPortActivation</b> and 
    <b>NetEventPortDeactivation</b> events. Only intermediate drivers can make other event notifications.</p>

<p>To propagate notification of a network Plug and Play event, an NDIS PnP event, or Power Management
    event to overlying drivers, an NDIS intermediate driver calls 
    <b>NdisMNetPnPEvent</b> in the context of the driver's 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function.</p>

<p>If the propagated event is a 
    <b>NetEventQueryPower</b> or a 
    <b>NetEventQueryRemoveDevice</b>, the intermediate driver must check the NDIS_STATUS value that is
    returned by 
    <b>NdisMNetPnPEvent</b>. If the returned status is NDIS_STATUS_SUCCESS, the intermediate driver should
    handle the event and then return NDIS_STATUS_SUCCESS from its 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function. If the returned status is not NDIS_STATUS_SUCCESS, the intermediate
    driver should return the reported status from its 
    <i>ProtocolNetPnPEvent</i> function without further processing.</p>

<p>How the intermediate driver processes a 
    <b>NetEventSetPower</b> received by its 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function depends on the specified device power state. If the specified device
    power state is 
    <b>NdisDeviceStateD0</b>, the intermediate driver should handle the event and then call 
    <b>NdisMNetPnPEvent</b>. For any other specified device power state, the intermediate driver should first
    call 
    <b>NdisMNetPnPEvent</b> and then handle the event.</p>

<p>An intermediate driver should call 
    <b>NdisMNetPnPEvent</b> to propagate a 
    <b>NetEventReconfigure</b> or 
    <b>NetEventBindList</b> only if the 
    <b>NetEventReconfigure</b> or 
    <b>NetEventBindList</b> is indicated on a non-<b>NULL</b>
<i>ProtocolBindingContext</i>. If a 
    <b>NetEventReconfigure</b> or 
    <b>NetEventBindList</b> is indicated on a <b>NULL</b>
<i>ProtocolBindingContext</i>, the intermediate driver should not call 
    <b>NdisMNetPnPEvent</b> to propagate the event.</p>

<p>If an intermediate driver handles a 
    <b>NetEventReconfigure</b> or a 
    <b>NetEventBindList</b>, it should validate any data associated with the event.</p>

<p>An intermediate driver should not propagate the 
    <b>NetEventBindsComplete</b>, 
    <b>NetEventPause</b>, 
    <b>NetEventRestart</b>, 
    <b>NetEventPortActivation</b>, or 
    <b>NetEventPortDeactivation</b> events by calling 
    <b>NdisMNetPnPEvent</b>.</p>

<p>An NDIS intermediate driver can generate its own NDIS port events for virtual miniports as
    appropriate for the 
    <b>NetEventPortActivation</b> or 
    <b>NetEventPortDeactivation</b> events that it receives at its 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function.</p>

<p>For all other propagated events, the intermediate driver's 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function should propagate the status value that is returned by 
    <b>NdisMNetPnPEvent</b>.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
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
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547996">Irql_Protocol_Driver_Function</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975120">NdisMNetPnPEventInOIDRequest</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/733d84f5-c1d4-42a0-a59b-4ba50247f165">MiniportOidRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568752">NET_PNP_EVENT_NOTIFICATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMNetPnPEvent function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>