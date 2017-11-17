---
UID: NS.ndischimney._TCP_OFFLOAD_STATS
title: TCP_OFFLOAD_STATS
author: windows-driver-content
description: The TCP_OFFLOAD_STATS structure contains statistics that an offload target supplies in response to a query of OID_TCP4_OFFLOAD_STATS or OID_TCP6_OFFLOAD_STATS.
old-location: netvista\tcp_offload_stats.htm
ms.assetid: 959bc46a-c574-4130-a83d-22a695d0d891
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TCP_OFFLOAD_STATS
req.alt-loc: ndischimney.h
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
ms.keywords: TCP_OFFLOAD_STATS, TCP_OFFLOAD_STATS, *PTCP_OFFLOAD_STATS
req.iface: 
---

# TCP_OFFLOAD_STATS structure



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]</p>
<p>The TCP_OFFLOAD_STATS structure contains statistics that an offload target supplies in response to a
  query of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569800">OID_TCP4_OFFLOAD_STATS</a> or 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569801">OID_TCP6_OFFLOAD_STATS</a>.</p>


## -syntax

````
typedef struct _TCP_OFFLOAD_STATS {
  ULONG64 InSegments;
  ULONG64 OutSegments;
  ULONG   CurrentlyEstablished;
  ULONG   ResetEstablished;
  ULONG   RetransmittedSegments;
  ULONG   InErrors;
  ULONG   OutResets;
} TCP_OFFLOAD_STATS, *PTCP_OFFLOAD_STATS;
````


## -struct-fields
<dl>

### -field <b>InSegments</b>

<dd>
<p>The total number of segments received on offloaded TCP connections, including those received in
     error (
     <b>InErrors</b> ). This count includes segments received on currently established connections. See 
     <i>tcpInSegs</i> in RFC 1156.</p>
</dd>

### -field <b>OutSegments</b>

<dd>
<p>The total number of segments sent on offloaded TCP connections, including those on current
     connections but excluding those containing only retransmitted octets. See 
     <i>tcpOutSegs</i> in RFC 1156.</p>
</dd>

### -field <b>CurrentlyEstablished</b>

<dd>
<p>The number of TCP connections for which the current state is either ESTABLISHED or CLOSE-WAIT. See
     
     <i>tcpCurrEstab</i> in RFC 1156.</p>
</dd>

### -field <b>ResetEstablished</b>

<dd>
<p>The number of times that offloaded TCP connections have made a direct transition to the CLOSED
     state from either the ESTABLISHED state or the CLOSE-WAIT state.</p>
</dd>

### -field <b>RetransmittedSegments</b>

<dd>
<p>The total number of segments retransmitted on offloaded TCP connections--that is, the number of
     TCP segments transmitted that contain one or more previously transmitted octets. See 
     <i>tcpRetransSegs</i> in RFC 1156.</p>
</dd>

### -field <b>InErrors</b>

<dd>
<p>The number of packets received on offloaded TCP connections that contained one or more
     TCP-specific errors that prevented the offload target from delivering the packets. See 
     <i>ifInErrors</i> in RFC 1156.</p>
</dd>

### -field <b>OutResets</b>

<dd>
<p>The number of segments transmitted on offloaded TCP connections with the RST bit set in the TCP
     header.</p>
</dd>
</dl>

## -remarks
<p>The statistics in the TCP_OFFLOAD_STATS structure pertain only to offloaded TCP connections. The
    offload target must not include counts for TCP segments on connections that haven't been offloaded. The
    statistics in the TCP_OFFLOAD_STATS structure pertain to a single network interface.</p>

<p>If an offload target has more than one network interface, it must maintain a separate set of TCP
    statistics counters for each network interface. If the offload target supports both IPv4 and IPv6
    connections on a network interface, it must, for that interface, maintain a separate set of TCP
    statistics counters for TCP/IPv4 traffic and a separate set of TCP statistics counters for TCP/IPv6
    traffic.</p>

<p>If an offload target's TCP chimney capabilities are enabled (see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff558995">NDIS_TASK_OFFLOAD</a>) and if at least one
    offloaded path state object has been offloaded to the offload target, the offload target can process a
    received packet that has a corrupted TCP header (but a valid IP header) in one of two ways:</p>

<p>The offload target can indicate the packet through the non-offload interface by calling the 
      <a href="https://msdn.microsoft.com/b87dba3e-c18f-4ea2-8bd5-ec3cdafc534b">
      NdisMIndicateReceiveNetBufferLists</a> function. In this case, the offload target must not increment
      the 
      <b>InErrors</b> counter. This is the recommended approach.</p>

<p>Alternatively, the offload target can drop the corrupted packet and increment the 
      <b>InErrors</b> counter.</p>

<p>If the offload target's TCP chimney capabilities are not enabled or if there is not at least one
    offloaded path state object, the offload target must indicate the corrupted packet and must not increment
    the 
    <b>InErrors</b> counter.</p>

<p>The host stack integrates the statistics returned by an offload target with the statistics that the
    host stack maintains for non-offloaded TCP connections.</p>

<p>Note that the host stack supplies a TCP_OFFLOAD_STATS structure when setting OID_TCP4_OFFLOAD_STATS or
    OID_TCP6_OFFLOAD_STATS. In this case, however, the offload target does not have to examine the values in
    the TCP_OFFLOAD_STATS structure. Instead, when OID_TCP4_OFFLOAD_STATS is set, the offload target should
    reset to zero its TCP statistics counters for offloaded TCP connections that convey IPv4 datagrams. When
    OID_TCP6_OFFLOAD_STATS is set, the offload target should reset to zero its TCP statistics counters for
    offloaded TCP connections that convey IPv6 datagrams.</p>

<p>All of the counters that supply the values for the TCP_OFFLOAD_STATS structure wrap (restart from
    zero) when incremented beyond their maximum counts.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569800">OID_TCP4_OFFLOAD_STATS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569801">OID_TCP6_OFFLOAD_STATS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20TCP_OFFLOAD_STATS structure%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>