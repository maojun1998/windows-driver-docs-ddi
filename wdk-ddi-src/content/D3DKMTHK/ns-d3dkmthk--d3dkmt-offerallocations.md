---
UID: NS.d3dkmthk._D3DKMT_OFFERALLOCATIONS
title: D3DKMT_OFFERALLOCATIONS
author: windows-driver-content
description: Defines the video memory allocations that the driver offers for reuse. Used with the D3DKMTOfferAllocations function.
old-location: display\d3dkmt_offerallocations.htm
ms.assetid: 6f6df55d-bb23-4a70-97f4-32809d1a41a5
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_OFFERALLOCATIONS
req.alt-loc: D3dkmthk.h
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
ms.keywords: D3DKMT_OFFERALLOCATIONS, D3DKMT_OFFERALLOCATIONS
req.iface: 
---

# D3DKMT_OFFERALLOCATIONS structure



## -description
<p>Defines the video memory allocations that the driver offers for reuse. Used with the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439402">D3DKMTOfferAllocations</a>  function.</p>


## -syntax

````
typedef struct _D3DKMT_OFFERALLOCATIONS {
  D3DKMT_HANDLE         hDevice;
  D3DKMT_HANDLE         *pResources;
  const D3DKMT_HANDLE   *HandleList;
  UINT                  NumAllocations;
  D3DKMT_OFFER_PRIORITY Priority;
} D3DKMT_OFFERALLOCATIONS;
````


## -struct-fields
<dl>

### -field <b>hDevice</b>

<dd>
<p>[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the device that created the allocations.</p>
</dd>

### -field <b>pResources</b>

<dd>
<p>[in] An array of Direct3D runtime handles to resources to offer.</p>
<p>If the user-mode driver uses the array specified by <b>HandleList</b> to offer a list of allocations, it must set <b>pResources</b> to <b>NULL</b>. Conversely, if the driver uses the array specified by <b>pResources</b> to offer a list of resources, it must set <b>HandleList</b> to <b>NULL</b>.</p>
</dd>

### -field <b>HandleList</b>

<dd>
<p>[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to allocations to offer.</p>
<p>If resources were created with the <b>D3D10_DDI_BIND_PRESENT</b> flag value set in <i>pCreateResource</i>-&gt;<b>BindFlags</b>, offer the resources by their allocation handles, not by their resource handles.</p>
</dd>

### -field <b>NumAllocations</b>

<dd>
<p>[in] The number of items in the <b>pResources</b> or <b>HandleList</b> members, whichever is not <b>NULL</b>.</p>
</dd>

### -field <b>Priority</b>

<dd>
<p>[in] The priority, of type  <a href="https://msdn.microsoft.com/library/windows/hardware/hh406486">D3DKMT_OFFER_PRIORITY</a>, with which to offer the allocations for reuse.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406486">D3DKMT_OFFER_PRIORITY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439402">D3DKMTOfferAllocations</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_OFFERALLOCATIONS structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>