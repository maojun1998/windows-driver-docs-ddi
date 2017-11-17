---
UID: NS.d3dkmddi._DXGK_GDIARG_ALPHABLEND
title: DXGK_GDIARG_ALPHABLEND
author: windows-driver-content
description: The DXGK_GDIARG_ALPHABLEND structure describes the characteristics of a GDI hardware-accelerated alpha blend operation.
old-location: display\dxgk_gdiarg_alphablend.htm
ms.assetid: 8bb9321c-00a0-4360-9a38-fcef2209028c
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_GDIARG_ALPHABLEND
req.alt-loc: d3dkmddi.h
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
ms.keywords: DXGK_GDIARG_ALPHABLEND, DXGK_GDIARG_ALPHABLEND
req.iface: 
---

# DXGK_GDIARG_ALPHABLEND structure



## -description
<p>The DXGK_GDIARG_ALPHABLEND structure describes the characteristics of a GDI hardware-accelerated alpha blend operation.</p>


## -syntax

````
typedef struct _DXGK_GDIARG_ALPHABLEND {
  RECT    SrcRect;
  RECT    DstRect;
  UINT    SrcAllocationIndex;
  UINT    DstAllocationIndex;
  UINT    NumSubRects;
  RECT    *pSubRects;
  BYTE    SourceConstantAlpha;
  BOOLEAN SourceHasAlpha;
  UINT    SrcPitch;
} DXGK_GDIARG_ALPHABLEND;
````


## -struct-fields
<dl>

### -field <b>SrcRect</b>

<dd>
<p>[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that defines the rectangular area to be copied. This rectangle is specified in the coordinate system of the source surface and is defined by two points: upper left and lower right. The two points that define the rectangle are always well ordered. </p>
<p>The source rectangle will never exceed the bounds of the source surface, so it will never overhang the source surface.</p>
<p>This rectangle is mapped to the destination rectangle defined by <b>DstRect</b>.</p>
<p>For more information, see the Remarks section.</p>
</dd>

### -field <b>DstRect</b>

<dd>
<p>[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that defines the rectangular area to be modified. This rectangle is specified in the coordinate system of the destination surface and is defined by two points: upper left and lower right. The rectangle is lower-right exclusive; that is, its lower and right edges are not a part of the bit-block transfer. The two points that define the rectangle are always well ordered. </p>
<p>The destination rectangle defined by <b>DstRect</b> can exceed the bounds of the destination surface, but sub-rectangles cannot. Additionally, all sub-rectangles are guaranteed to fit inside the destination surface. Sub-rectangles can be constrained further by a bounding rectangle that is smaller than the destination rectangle.</p>
<p>For more information, see the Remarks section.</p>
</dd>

### -field <b>SrcAllocationIndex</b>

<dd>
<p>[in] An index of the element in the allocation list that specifies the allocation that is referenced by the <b>SrcRect</b> source rectangle.</p>
</dd>

### -field <b>DstAllocationIndex</b>

<dd>
<p>[in] An index of the element in the allocation list that specifies the allocation that is referenced by the <b>DstRect</b> destination rectangle.</p>
</dd>

### -field <b>NumSubRects</b>

<dd>
<p>[in] The number of sub-rectangles in the destination surface space that is bounded by the <b>DstRect</b> destination rectangle.</p>
</dd>

### -field <b>pSubRects</b>

<dd>
<p>[in] A pointer to the sub-rectangles in the destination surface space.</p>
</dd>

### -field <b>SourceConstantAlpha</b>

<dd>
<p>[in] The constant blend factor to apply to the entire source surface. This value is in the range of [0,255], where 0 is completely transparent and 255 is completely opaque.</p>
</dd>

### -field <b>SourceHasAlpha</b>

<dd>
<p>[in] Defines whether the surface is assumed to have an alpha channel. If <b>TRUE</b>, the surface is assumed to have an alpha channel; otherwise the value is <b>FALSE</b>.</p>
</dd>

### -field <b>SrcPitch</b>

<dd>
<p>[in] The pitch of the source surface, in bytes.</p>
</dd>
</dl>

## -remarks
<p>If a stretch bit-block transfer (bitblt) operation is required, the x and y stretch ratios are computed respectively as the ratios of the x and y sizes of the <b>DstRect</b> and <b>SrcRect</b> members, and the stretch operation will proceed as if the COLORONCOLOR value in <i>Wingdi.h</i> is set. On a shrinking bit-block transfer, enough pixels should be ignored so that pixels do not need to be combined. On a stretching bit-block transfer, pixels should be replicated.</p>

<p>When sub-rectangles are transformed to the source surface space, the result is guaranteed to be within the source surface. The transformation of a sub-rectangle's coordinates in the destination surface to coordinates  in the source surface is defined by the following formulas, where</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 7 and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_GDIARG_ALPHABLEND structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>