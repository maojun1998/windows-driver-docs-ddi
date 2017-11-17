---
UID: NE.iscsidef.PISCSIIPADDRESSTYPE
title: PISCSIIPADDRESSTYPE
author: windows-driver-content
description: The ISCSIIPADDRESSTYPE enumeration indicates formats for an IP address.
old-location: storage\iscsiipaddresstype.htm
ms.assetid: a92f7048-ca8a-450c-93ab-6ea040412198
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: Storage
req.header: iscsidef.h
req.include-header: Iscsidef.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ISCSIIPADDRESSTYPE
req.alt-loc: iscsidef.h
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
ms.keywords: MSiSCSI_TCPIPConfig, MSiSCSI_TCPIPConfig, *PMSiSCSI_TCPIPConfig
req.iface: 
---

# PISCSIIPADDRESSTYPE enumeration



## -description
<p>The ISCSIIPADDRESSTYPE enumeration indicates formats for an IP address.</p>


## -syntax

````
typedef enum  { 
  ISCSI_IP_ADDRESS_TEXT   = 0,
  ISCSI_IP_ADDRESS_IPV4   = 1,
  ISCSI_IP_ADDRESS_IPV6   = 2,
  ISCSI_IP_ADDRESS_EMPTY  = 3
} ISCSIIPADDRESSTYPE, *PISCSIIPADDRESSTYPE;
````


## -enum-fields
<dl>

### -field <a id="ISCSI_IP_ADDRESS_TEXT"></a><a id="iscsi_ip_address_text"></a><b>ISCSI_IP_ADDRESS_TEXT</b>

<dd>
<p>The IP address is in dotted decimal text format or in DNS format.</p>
</dd>

### -field <a id="ISCSI_IP_ADDRESS_IPV4"></a><a id="iscsi_ip_address_ipv4"></a><b>ISCSI_IP_ADDRESS_IPV4</b>

<dd>
<p>The IP address is a binary address that complies with version 4 of the IP protocol.</p>
</dd>

### -field <a id="ISCSI_IP_ADDRESS_IPV6"></a><a id="iscsi_ip_address_ipv6"></a><b>ISCSI_IP_ADDRESS_IPV6</b>

<dd>
<p>The IP address is a binary address that complies with version 6 of the IP protocol.</p>
</dd>

### -field <a id="ISCSI_IP_ADDRESS_EMPTY"></a><a id="iscsi_ip_address_empty"></a><b>ISCSI_IP_ADDRESS_EMPTY</b>

<dd>
<p>No address is specified.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Iscsidef.h (include Iscsidef.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20ISCSIIPADDRESSTYPE enumeration%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>