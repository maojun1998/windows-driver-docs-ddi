---
UID: NE.ntddndis._NDIS_ARP_HEADER_FIELD
title: NDIS_ARP_HEADER_FIELD
author: windows-driver-content
description: The NDIS_ARP_HEADER_FIELD enumeration identifies the type of a field in an Address Resolution Protocol (ARP) header.
old-location: netvista\ndis_arp_header_field.htm
ms.assetid: 63DA6329-C673-48A0-8E36-67035E2DB4C9
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: netvista
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_ARP_HEADER_FIELD
req.alt-loc: Ntddndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: GET_CONFIGURATION_IOCTL_INPUT, GET_CONFIGURATION_IOCTL_INPUT, *PGET_CONFIGURATION_IOCTL_INPUT
req.iface: 
---

# NDIS_ARP_HEADER_FIELD enumeration



## -description
<p>The <b>NDIS_ARP_HEADER_FIELD</b> enumeration identifies the type of a field in an Address Resolution Protocol (ARP) header.</p>


## -syntax

````
typedef enum _NDIS_ARP_HEADER_FIELD { 
  NdisARPHeaderFieldUndefined,
  NdisARPHeaderFieldOperation,
  NdisARPHeaderFieldSPA,
  NdisARPHeaderFieldTPA,
  NdisARPHeaderFieldMaximum
} NDIS_ARP_HEADER_FIELD, *PNDIS_ARP_HEADER_FIELD;
````


## -enum-fields
<dl>

### -field <a id="NdisARPHeaderFieldUndefined"></a><a id="ndisarpheaderfieldundefined"></a><a id="NDISARPHEADERFIELDUNDEFINED"></a><b>NdisARPHeaderFieldUndefined</b>

<dd>
<p>An undefined ARP header field.</p>
</dd>

### -field <a id="NdisARPHeaderFieldOperation"></a><a id="ndisarpheaderfieldoperation"></a><a id="NDISARPHEADERFIELDOPERATION"></a><b>NdisARPHeaderFieldOperation</b>

<dd>
<p>The ARP operation field.</p>
</dd>

### -field <a id="NdisARPHeaderFieldSPA"></a><a id="ndisarpheaderfieldspa"></a><a id="NDISARPHEADERFIELDSPA"></a><b>NdisARPHeaderFieldSPA</b>

<dd>
<p>The ARP source protocol address (SPA) field.</p>
</dd>

### -field <a id="NdisARPHeaderFieldTPA"></a><a id="ndisarpheaderfieldtpa"></a><a id="NDISARPHEADERFIELDTPA"></a><b>NdisARPHeaderFieldTPA</b>

<dd>
<p>The ARP target protocol address (TPA) field.</p>
</dd>

### -field <a id="NdisARPHeaderFieldMaximum"></a><a id="ndisarpheaderfieldmaximum"></a><a id="NDISARPHEADERFIELDMAXIMUM"></a><b>NdisARPHeaderFieldMaximum</b>

<dd>
<p>The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.</p>
</dd>
</dl>

## -remarks
<p>The <b>NDIS_ARP_HEADER_FIELD</b> enumeration is used in the 
    <a href="https://msdn.microsoft.com/3d387fe9-a7cc-4034-b31e-ba1359db2ae1">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.</p>

<p>The <b>NDIS_ARP_HEADER_FIELD</b> enumeration is used in the 
    <a href="https://msdn.microsoft.com/3d387fe9-a7cc-4034-b31e-ba1359db2ae1">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.</p>

<p>The <b>NDIS_ARP_HEADER_FIELD</b> enumeration is used in the 
    <a href="https://msdn.microsoft.com/3d387fe9-a7cc-4034-b31e-ba1359db2ae1">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.30 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/3d387fe9-a7cc-4034-b31e-ba1359db2ae1">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_ARP_HEADER_FIELD enumeration%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>