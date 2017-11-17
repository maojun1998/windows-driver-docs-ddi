---
UID: NE.d3d12umddi.D3D12DDI_RESOURCE_BARRIER_FLAGS
title: D3D12DDI_RESOURCE_BARRIER_FLAGS
author: windows-driver-content
description: Contains resource barrier flags.
old-location: display\d3d12ddi_resource_barrier_flags.htm
ms.assetid: 876ABC9C-F9BE-480F-8641-AE132840F8D5
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: display
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_RESOURCE_BARRIER_FLAGS
req.alt-loc: D3d12umddi.h
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
ms.keywords: D3DWDDM2_2DDI_SWIZZLE_PATTERN_DESC, D3DWDDM2_2DDI_SWIZZLE_PATTERN_DESC
req.iface: 
---

# D3D12DDI_RESOURCE_BARRIER_FLAGS enumeration



## -description
<p>Contains resource barrier flags.</p>


## -syntax

````
typedef enum D3D12DDI_RESOURCE_BARRIER_FLAGS { 
  D3D12DDI_RESOURCE_BARRIER_FLAG_NONE              = 0x0,
  D3D12DDI_RESOURCE_BARRIER_FLAG_BEGIN_ONLY        = 0x1,
  D3D12DDI_RESOURCE_BARRIER_FLAG_END_ONLY          = 0x2,
  D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ATOMIC_COPY  = 0x4,
  D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ALIASING     = 0x8
} D3D12DDI_RESOURCE_BARRIER_FLAGS;
````


## -enum-fields
<dl>

### -field <a id="D3D12DDI_RESOURCE_BARRIER_FLAG_NONE"></a><a id="d3d12ddi_resource_barrier_flag_none"></a><b>D3D12DDI_RESOURCE_BARRIER_FLAG_NONE</b>

<dd>
<p>No flag value.</p>
</dd>

### -field <a id="D3D12DDI_RESOURCE_BARRIER_FLAG_BEGIN_ONLY"></a><a id="d3d12ddi_resource_barrier_flag_begin_only"></a><b>D3D12DDI_RESOURCE_BARRIER_FLAG_BEGIN_ONLY</b>

<dd>
<p>Indicates a release. This flag is relevant only for ranged barriers.</p>
</dd>

### -field <a id="D3D12DDI_RESOURCE_BARRIER_FLAG_END_ONLY"></a><a id="d3d12ddi_resource_barrier_flag_end_only"></a><b>D3D12DDI_RESOURCE_BARRIER_FLAG_END_ONLY</b>

<dd>
<p>Indicates an acquire. This flag is relevant only for ranged barriers.</p>
</dd>

### -field <a id="D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ATOMIC_COPY"></a><a id="d3d12ddi_resource_barrier_flag_0022_atomic_copy"></a><b>D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ATOMIC_COPY</b>

<dd>
<p>Indicates that ranged barriers are associated with a parameter of an atomic copy operation. </p>
</dd>

### -field <a id="D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ALIASING"></a><a id="d3d12ddi_resource_barrier_flag_0022_aliasing"></a><b>D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ALIASING</b>

<dd>
<p>Indicates that an aliasing barrier has been converted to a ranged barrier.</p>
</dd>
</dl>

## -remarks
<p>The absence of both <b>D3D12DDI_RESOURCE_BARRIER_FLAG_BEGIN_ONLY</b> and <b>D3D12DDI_RESOURCE_BARRIER_FLAG_END_ONLY</b> denotes both an acquire and release.</p>

<p>During an acquire, GPU caches may need to be explicitly invalidated. During a release, GPU caches may need to be explicitly flushed. </p>

<p>The absence of both <b>D3D12DDI_RESOURCE_BARRIER_FLAG_BEGIN_ONLY</b> and <b>D3D12DDI_RESOURCE_BARRIER_FLAG_END_ONLY</b> denotes both an acquire and release.</p>

<p>During an acquire, GPU caches may need to be explicitly invalidated. During a release, GPU caches may need to be explicitly flushed. </p>

<p>The absence of both <b>D3D12DDI_RESOURCE_BARRIER_FLAG_BEGIN_ONLY</b> and <b>D3D12DDI_RESOURCE_BARRIER_FLAG_END_ONLY</b> denotes both an acquire and release.</p>

<p>During an acquire, GPU caches may need to be explicitly invalidated. During a release, GPU caches may need to be explicitly flushed. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>