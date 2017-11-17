---
UID: NS.d3d10umddi.D3D10_DDI_DEPTH_STENCILOP_DESC
title: D3D10_DDI_DEPTH_STENCILOP_DESC
author: windows-driver-content
description: The D3D10_DDI_DEPTH_STENCILOP_DESC structure describes a depth stencil operation.
old-location: display\d3d10_ddi_depth_stencilop_desc.htm
ms.assetid: 3f0f3f1d-5b38-4815-9732-3b4079481c58
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D10_DDI_DEPTH_STENCILOP_DESC
req.alt-loc: d3d10umddi.h
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
ms.keywords: D3D10_DDI_DEPTH_STENCILOP_DESC, D3D10_DDI_DEPTH_STENCILOP_DESC
req.iface: 
---

# D3D10_DDI_DEPTH_STENCILOP_DESC structure



## -description
<p>The D3D10_DDI_DEPTH_STENCILOP_DESC structure describes a depth stencil operation.</p>


## -syntax

````
typedef struct D3D10_DDI_DEPTH_STENCILOP_DESC {
  D3D10_DDI_STENCIL_OP      StencilFailOp;
  D3D10_DDI_STENCIL_OP      StencilDepthFailOp;
  D3D10_DDI_STENCIL_OP      StencilPassOp;
  D3D10_DDI_COMPARISON_FUNC StencilFunc;
} D3D10_DDI_DEPTH_STENCILOP_DESC;
````


## -struct-fields
<dl>

### -field <b>StencilFailOp</b>

<dd>
<p>[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff542013">D3D10_DDI_STENCIL_OP</a>-typed value that indicates the operation to perform if the stencil test fails.</p>
</dd>

### -field <b>StencilDepthFailOp</b>

<dd>
<p>[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff542013">D3D10_DDI_STENCIL_OP</a>-typed value that indicates the operation to perform if the stencil test passes and the depth test fails.</p>
</dd>

### -field <b>StencilPassOp</b>

<dd>
<p>[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff542013">D3D10_DDI_STENCIL_OP</a>-typed value that indicates the operation to perform if both stencil and depth tests pass.</p>
</dd>

### -field <b>StencilFunc</b>

<dd>
<p>[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541933">D3D10_DDI_COMPARISON_FUNC</a>-typed value that indicates the stencil-comparison function to perform.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/dcc02e1e-97e0-4ccd-8329-8219cad5d09a">CalcPrivateDepthStencilStateSize</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/ed2da104-c4e8-43eb-80e0-10273b575020">CreateDepthStencilState</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541933">D3D10_DDI_COMPARISON_FUNC</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542013">D3D10_DDI_STENCIL_OP</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_DEPTH_STENCILOP_DESC structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>