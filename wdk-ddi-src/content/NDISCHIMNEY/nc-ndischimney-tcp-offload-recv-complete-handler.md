---
UID: NC.ndischimney.TCP_OFFLOAD_RECV_COMPLETE_HANDLER
title: TCP_OFFLOAD_RECV_COMPLETE_HANDLER
author: windows-driver-content
description: NDIS calls a protocol or intermediate driver's ProtocolTcpOffloadReceiveComplete function to complete a receive operation that the driver previously initiated by calling the NdisOffloadTcpReceive function.
old-location: netvista\protocoltcpoffloadreceivecomplete.htm
ms.assetid: 78201512-6b70-4b4b-9016-0f42fed41ac6
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolTcpOffloadReceiveComplete
req.alt-loc: Ndischimney.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
ms.keywords: BINARY_DATA, BINARY_DATA
req.iface: 
---

# TCP_OFFLOAD_RECV_COMPLETE_HANDLER callback



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]</p>
<p>NDIS calls a protocol or intermediate driver's 
  <i>ProtocolTcpOffloadReceiveComplete</i> function to complete a receive operation that the driver previously
  initiated by calling the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff563703">NdisOffloadTcpReceive</a> function.</p>


## -prototype

````
TCP_OFFLOAD_RECV_COMPLETE_HANDLER ProtocolTcpOffloadReceiveComplete;

VOID ProtocolTcpOffloadReceiveComplete(
  _In_ NDIS_HANDLE      ProtocolBindingContext,
  _In_ PNET_BUFFER_LIST NetBufferList
)
{ ... }
````


## -parameters
<dl>

### -param <i>ProtocolBindingContext</i> [in]

<dd>
<p>A handle to a context area allocated by the protocol driver. The driver maintains the per binding
     context information in this context area. The driver supplied this handle to NDIS when the driver called
     the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function.</p>
</dd>

### -param <i>NetBufferList</i> [in]

<dd>
<p>A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. This structure
     can be stand-alone or the first structure in a linked list of NET_BUFFER_LIST structures. The driver
     supplied this pointer as an input parameter in a previous call to the 
     <a href="https://msdn.microsoft.com/021f41c4-6ba9-418e-bc18-131ce6d90877">
     NdisOffloadTcpReceive</a> function.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>In response to an underlying driver's or offload target's call to the 
    <a href="https://msdn.microsoft.com/d5b1341b-cbe0-483c-9abb-b8706f2db2dd">
    NdisOffloadTcpReceiveComplete</a> function, NDIS calls the overlying protocol driver's or intermediate
    driver's 
    <i>ProtocolTcpOffloadReceiveComplete</i> function.</p>

<p>To propagate the completion of the I/O operation to the overlying driver, the intermediate driver
    itself calls the 
    <b>NdisOffloadTcpReceiveComplete</b> function, passing in the following:</p>

<p>A 
      <i>ProtocolBindingContext</i>, which is a handle that uniquely identifies the intermediate driver.</p>

<p>The PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>ProtocolTcpOffloadReceiveComplete</i> function.</p>

<p>In response, NDIS calls the overlying driver's 
    <i>ProtocolTcpOffloadReceiveComplete</i> function, passing a 
    <i>ProtocolBindingContext</i> handle and the PNET_BUFFER_LIST pointer supplied by the intermediate driver
    to the 
    <b>NdisOffloadTcpReceiveComplete</b> function.</p>

<p>In response to an underlying driver's or offload target's call to the 
    <a href="https://msdn.microsoft.com/d5b1341b-cbe0-483c-9abb-b8706f2db2dd">
    NdisOffloadTcpReceiveComplete</a> function, NDIS calls the overlying protocol driver's or intermediate
    driver's 
    <i>ProtocolTcpOffloadReceiveComplete</i> function.</p>

<p>To propagate the completion of the I/O operation to the overlying driver, the intermediate driver
    itself calls the 
    <b>NdisOffloadTcpReceiveComplete</b> function, passing in the following:</p>

<p>A 
      <i>ProtocolBindingContext</i>, which is a handle that uniquely identifies the intermediate driver.</p>

<p>The PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>ProtocolTcpOffloadReceiveComplete</i> function.</p>

<p>In response, NDIS calls the overlying driver's 
    <i>ProtocolTcpOffloadReceiveComplete</i> function, passing a 
    <i>ProtocolBindingContext</i> handle and the PNET_BUFFER_LIST pointer supplied by the intermediate driver
    to the 
    <b>NdisOffloadTcpReceiveComplete</b> function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndischimney.h (include Ndischimney.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/9c9c033d-e892-4d8a-8f12-4ca34cdc9ea1">MiniportTcpOffloadReceive</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563703">NdisOffloadTcpReceive</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/d5b1341b-cbe0-483c-9abb-b8706f2db2dd">
   NdisOffloadTcpReceiveComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20TCP_OFFLOAD_RECV_COMPLETE_HANDLER callback function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>