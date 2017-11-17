---
UID: NE.iscsicfg.PISCSI_NIC_LINKSTATE
title: PISCSI_NIC_LINKSTATE
author: windows-driver-content
description: The ISCSI_NIC_LINKSTATE enumeration indicates whether a port is connected to the network or not.
old-location: storage\iscsi_nic_linkstate.htm
ms.assetid: e373b1dd-54bd-429c-a5b9-9f8df546c185
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: Storage
req.header: iscsicfg.h
req.include-header: Iscsicfg.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ISCSI_NIC_LINKSTATE
req.alt-loc: iscsicfg.h
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
ms.keywords: IDEREGISTERS, IDEREGISTERS, *PIDEREGISTERS
req.iface: 
---

# PISCSI_NIC_LINKSTATE enumeration



## -description
<p>The ISCSI_NIC_LINKSTATE enumeration indicates whether a port is connected to the network or not.</p>


## -syntax

````
typedef enum  { 
  ISCSI_NIC_LINKSTATE_DISCONNECTED  = 0,
  ISCSI_NIC_LINKSTATE_CONNECTED     = 1
} ISCSI_NIC_LINKSTATE, *PISCSI_NIC_LINKSTATE;
````


## -enum-fields
<dl>

### -field <a id="ISCSI_NIC_LINKSTATE_DISCONNECTED"></a><a id="iscsi_nic_linkstate_disconnected"></a><b>ISCSI_NIC_LINKSTATE_DISCONNECTED</b>

<dd>
<p>A network port is disconnected from the network. </p>
</dd>

### -field <a id="ISCSI_NIC_LINKSTATE_CONNECTED"></a><a id="iscsi_nic_linkstate_connected"></a><b>ISCSI_NIC_LINKSTATE_CONNECTED</b>

<dd>
<p>A network port is connected to the network. </p>
</dd>
</dl>

## -remarks
<p>The ISCSI_NIC_LINKSTATE enumeration is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563083">MSiSCSI_NICConfig WMI Class</a>.</p>

<p>The ISCSI_NIC_LINKSTATE enumeration is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563083">MSiSCSI_NICConfig WMI Class</a>.</p>

<p>The ISCSI_NIC_LINKSTATE enumeration is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563083">MSiSCSI_NICConfig WMI Class</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Iscsicfg.h (include Iscsicfg.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563079">MSiSCSI_NICConfig</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563083">MSiSCSI_NICConfig WMI Class</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20ISCSI_NIC_LINKSTATE enumeration%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>