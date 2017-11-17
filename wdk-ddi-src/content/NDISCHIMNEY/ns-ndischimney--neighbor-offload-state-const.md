---
UID: NS.ndischimney._NEIGHBOR_OFFLOAD_STATE_CONST
title: NEIGHBOR_OFFLOAD_STATE_CONST
author: windows-driver-content
description: The NEIGHBOR_OFFLOAD_STATE_CONST structure contains the constant variables of a neighbor state object.
old-location: netvista\neighbor_offload_state_const.htm
ms.assetid: 1c79a3d6-c365-4740-a2e0-94333b70d8cc
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
req.alt-api: NEIGHBOR_OFFLOAD_STATE_CONST
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
ms.keywords: NEIGHBOR_OFFLOAD_STATE_CONST, NEIGHBOR_OFFLOAD_STATE_CONST, *PNEIGHBOR_OFFLOAD_STATE_CONST
req.iface: 
---

# NEIGHBOR_OFFLOAD_STATE_CONST structure



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]</p>
<p>The NEIGHBOR_OFFLOAD_STATE_CONST structure contains the constant variables of a neighbor state
  object.</p>


## -syntax

````
typedef struct _NEIGHBOR_OFFLOAD_STATE_CONST {
  OFFLOAD_STATE_HEADER Header;
  UCHAR                DlSourceAddress[32];
  ULONG                VlanId  :12;
} NEIGHBOR_OFFLOAD_STATE_CONST, *PNEIGHBOR_OFFLOAD_STATE_CONST;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569062">OFFLOAD_STATE_HEADER</a> structure. NDIS
     sets the 
     <b>Length</b> member of 
     <b>Header</b> to the size, in bytes, of the NEIGHBOR_OFFLOAD_STATE_CONST structure. The 
     <b>RecognizedOptions</b> member of 
     <b>Header</b> is reserved.</p>
</dd>

### -field <b>DlSourceAddress</b>

<dd>
<p>When non-<b>NULL</b>, a 32-byte source MAC address. The offload target must support software-configurable
     MAC addresses and it must set the source MAC address of all packets that it sends on the offloaded
     connection to 
     <b>DlSourceAddress</b> . 
     </p>
<p>When <b>NULL</b>, the offload target ignores this parameter and sets the source MAC address to the value
     that was configured for the network interface.</p>
<p>If the network interface has one or more multicast addresses enabled, the offloaded connection must
     allow receive traffic to arrive on either the configured MAC address or the multicast addresses. The
     configured MAC address is either 
     <b>DlSourceAddress</b> or, if 
     <b>DlSourceAddress</b> is zero, the MAC address for the network interface.</p>
</dd>

### -field <b>VlanId</b>

<dd>
<p>An unsigned 12-bit binary number that identifies the virtual LAN (VLAN) to which a packet belongs.
     The 
     <b>VlanId</b> ID pertains only to packets that are sent or received using the neighbor state object.
     </p>
<p>When <b>NULL</b>, the offload target should use any VLAN IDs that have been configured for its network
     interface. The offload target's 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function
     reads such VLAN IDs from the registry.</p>
</dd>
</dl>

## -remarks
<p>For a description of how an offload target uses the 
    <b>VlanId</b> member, see 
    <a href="netvista.802_1q_and_802_1p_processing_on_an_offloaded_tcp_connection">802.1Q
    and 802.1p Processing on an Offloaded TCP Connection</a>.</p>

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
<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568323">NEIGHBOR_OFFLOAD_STATE_CACHED</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/94a35d0f-3585-45d0-bba8-0b4a8ebbe883">
   NEIGHBOR_OFFLOAD_STATE_DELEGATED</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569062">OFFLOAD_STATE_HEADER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NEIGHBOR_OFFLOAD_STATE_CONST structure%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>