---
UID: NS.d3d12umddi.D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
title: D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
author: windows-driver-content
description: Write buffer immediate parameter.
old-location: display\d3d12ddi-writebufferimmediate-parameter-0032.htm
ms.assetid: 84b0f28d-2157-492e-bafa-ea97956d66f2
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
req.alt-loc: d3d12umddi.h
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
ms.keywords: D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032, D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
req.iface: 
---

# D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032 structure



## -description
<p>Write buffer immediate parameter.</p>


## -syntax

````
typedef struct _D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032 {
  D3D12DDI_GPU_VIRTUAL_ADDRESS  Dst;
  UINT32                        Value;
} D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032, D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032;
````


## -struct-fields
<dl>

### -field <b>Dst</b>

<dd>
<p>Destination.</p>
</dd>

### -field <b>Value</b>

<dd>
<p>Value.</p>
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
<dt>D3d12umddi.h</dt>
</dl>
</td>
</tr>
</table>