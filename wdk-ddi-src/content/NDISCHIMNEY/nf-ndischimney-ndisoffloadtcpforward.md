---
UID: NF.ndischimney.NdisOffloadTcpForward
title: NdisOffloadTcpForward
author: windows-driver-content
description: A protocol driver or an intermediate driver calls the NdisOffloadTcpForward function to forward unacknowledged received TCP segments to an underlying driver or offload target.
old-location: netvista\ndisoffloadtcpforward.htm
ms.assetid: ca4e26c5-5fea-42ab-aee6-3ecf4cce3798
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisOffloadTcpForward
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: 
ms.keywords: NdisOffloadTcpForward
req.iface: 
---

# NdisOffloadTcpForward function



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]</p>
<p>A protocol driver or an intermediate driver calls the 
  <b>NdisOffloadTcpForward</b> function to forward unacknowledged received TCP segments to an underlying
  driver or offload target.</p>


## -syntax

````
NDIS_STATUS NdisOffloadTcpForward(
  _In_ PNDIS_OFFLOAD_HANDLE NdisOffloadHandle,
  _In_ PNET_BUFFER_LIST     NetBufferList
);
````


## -parameters
<dl>

### -param <i>NdisOffloadHandle</i> [in]

<dd>
<p>A handle to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566705">NDIS_OFFLOAD_HANDLE</a> structure in the
     caller's context for the offloaded TCP connection. For more information, see 
     <a href="netvista.referencing_offloaded_state_through_an_intermediate_driver">
     Referencing Offloaded State Through an Intermediate Driver</a>.</p>
</dd>

### -param <i>NetBufferList</i> [in]

<dd>
<p>A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     Each NET_BUFFER_LIST structure in the list describes one 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure. Each NET_BUFFER structure
     points to a chain of memory descriptor lists (MDLs). The MDLs associated with a NET_BUFFER structure
     contain one and only one TCP segment that is being forwarded to the offload target. The first byte of
     the first MDL is the first byte of the TCP header. The NET_BUFFER_LIST and associated structures are
     locked so that they remain resident in physical memory. However, they are not mapped into system
     memory.</p>
</dd>
</dl>

## -returns
<p>The 
     <b>NdisOffloadTcpForward</b> function always returns NDIS_STATUS_PENDING. The forward operation is always
     completed asynchronously.</p>

## -remarks
<p>In response to a call to its 
    <i>MiniportTcpOffloadForward</i> function, an intermediate driver calls the 
    <b>NdisOffloadTcpForward</b> function to propagate the forward operation to the underlying driver or
    offload target. For more information, see 
    <a href="NULL">Propagating I/O Operations</a>.</p>

<p>To the 
    <b>NdisOffloadTcpForward</b> function, the intermediate driver passes the following:</p>

<p>An 
      <i>NdisOffloadHandle</i> function that references the NDIS_OFFLOAD_HANDLE structure stored in the
      intermediate driver's context for the offloaded TCP connection. For more information, see 
      <a href="netvista.referencing_offloaded_state_through_an_intermediate_driver">
      Referencing Offloaded State Through an Intermediate Driver</a>.</p>

<p>The same PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <a href="https://msdn.microsoft.com/e5702476-60a3-4bfc-b959-198e98f0f9ba">
      MiniportTcpOffloadForward</a> function.</p>

<p>When the underlying driver or offload target subsequently completes the forward operation by calling
    the 
    <b>NdisTcpOffloadForwardComplete</b> function, NDIS calls the intermediate driver's 
    <i>ProtocolOffloadForwardComplete</i> function. The intermediate driver then calls the 
    <b>NdisTcpOffloadForwardComplete</b> function to propagate the completion of the forward operation.</p>

<p>In response to a call to its 
    <i>MiniportTcpOffloadForward</i> function, an intermediate driver calls the 
    <b>NdisOffloadTcpForward</b> function to propagate the forward operation to the underlying driver or
    offload target. For more information, see 
    <a href="NULL">Propagating I/O Operations</a>.</p>

<p>To the 
    <b>NdisOffloadTcpForward</b> function, the intermediate driver passes the following:</p>

<p>An 
      <i>NdisOffloadHandle</i> function that references the NDIS_OFFLOAD_HANDLE structure stored in the
      intermediate driver's context for the offloaded TCP connection. For more information, see 
      <a href="netvista.referencing_offloaded_state_through_an_intermediate_driver">
      Referencing Offloaded State Through an Intermediate Driver</a>.</p>

<p>The same PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <a href="https://msdn.microsoft.com/e5702476-60a3-4bfc-b959-198e98f0f9ba">
      MiniportTcpOffloadForward</a> function.</p>

<p>When the underlying driver or offload target subsequently completes the forward operation by calling
    the 
    <b>NdisTcpOffloadForwardComplete</b> function, NDIS calls the intermediate driver's 
    <i>ProtocolOffloadForwardComplete</i> function. The intermediate driver then calls the 
    <b>NdisTcpOffloadForwardComplete</b> function to propagate the completion of the forward operation.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndischimney.h (include Ndischimney.h)</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/e5702476-60a3-4bfc-b959-198e98f0f9ba">MiniportTcpOffloadForward</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566705">NDIS_OFFLOAD_HANDLE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/080949ab-8a27-4d13-992e-597210d4882c">
   NdisTcpOffloadForwardComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/02a11841-d98a-4c74-8922-458826e2911e">
   ProtocolTcpOffloadForwardComplete</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisOffloadTcpForward function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>