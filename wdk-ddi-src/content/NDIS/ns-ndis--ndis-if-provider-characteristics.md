---
UID: NS.ndis._NDIS_IF_PROVIDER_CHARACTERISTICS
title: NDIS_IF_PROVIDER_CHARACTERISTICS
author: windows-driver-content
description: The NDIS_IF_PROVIDER_CHARACTERISTICS structure defines NDIS network interface provider entry points and other provider characteristics.
old-location: netvista\ndis_if_provider_characteristics.htm
ms.assetid: f295bea2-20d8-4c71-b78b-77d43840be2a
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_IF_PROVIDER_CHARACTERISTICS
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
ms.keywords: NDIS_IF_PROVIDER_CHARACTERISTICS, NDIS_IF_PROVIDER_CHARACTERISTICS, *PNDIS_IF_PROVIDER_CHARACTERISTICS
req.iface: 
---

# NDIS_IF_PROVIDER_CHARACTERISTICS structure



## -description
<p>The NDIS_IF_PROVIDER_CHARACTERISTICS structure defines NDIS network interface provider entry points
  and other provider characteristics.</p>


## -syntax

````
typedef struct _NDIS_IF_PROVIDER_CHARACTERISTICS {
  NDIS_OBJECT_HEADER Header;
  IFP_QUERY_OBJECT   QueryObjectHandler;
  IFP_SET_OBJECT     SetObjectHandler;
  PVOID              Reserved1;
  PVOID              Reserved2;
} NDIS_IF_PROVIDER_CHARACTERISTICS, *PNDIS_IF_PROVIDER_CHARACTERISTICS;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     interface provider characteristics structure (NDIS_IF_PROVIDER_CHARACTERISTICS). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_OBJECT_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_IF_PROVIDER_CHARACTERISTICS_REVISION_1.</p>
</dd>

### -field <b>QueryObjectHandler</b>

<dd>
<p>The entry point for the 
     <a href="https://msdn.microsoft.com/dea90ff0-7620-4364-90dc-2dc5d2e34ce1">
     ProviderQueryObject</a> function.</p>
</dd>

### -field <b>SetObjectHandler</b>

<dd>
<p>The entry point for the 
     <a href="https://msdn.microsoft.com/e5dcb46e-5a8a-45b7-b6aa-150a9cec0155">ProviderSetObject</a> function.</p>
</dd>

### -field <b>Reserved1</b>

<dd>
<p>Reserved for NDIS.</p>
</dd>

### -field <b>Reserved2</b>

<dd>
<p>Reserved for NDIS.</p>
</dd>
</dl>

## -remarks
<p>All NDIS network driver types can register as network interface providers. An NDIS interface provider
    initializes an NDIS_IF_PROVIDER_CHARACTERISTICS structure to define its provider entry points and other
    characteristics, if any.</p>

<p>To register as an interface provider, the driver passes a pointer to the initialized
    NDIS_IF_PROVIDER_CHARACTERISTICS structure to the 
    <a href="https://msdn.microsoft.com/1624426b-9e67-4aa2-83d8-f1e6fa484858">
    NdisIfRegisterProvider</a> function.</p>

## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562716">NdisIfRegisterProvider</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/dea90ff0-7620-4364-90dc-2dc5d2e34ce1">ProviderQueryObject</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/e5dcb46e-5a8a-45b7-b6aa-150a9cec0155">ProviderSetObject</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_IF_PROVIDER_CHARACTERISTICS structure%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>