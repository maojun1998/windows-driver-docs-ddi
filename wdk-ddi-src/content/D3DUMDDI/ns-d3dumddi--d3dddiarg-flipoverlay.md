---
UID: NS.d3dumddi._D3DDDIARG_FLIPOVERLAY
title: D3DDDIARG_FLIPOVERLAY
author: windows-driver-content
description: The D3DDDIARG_FLIPOVERLAY structure describes a new resource to display on a given overlay.
old-location: display\d3dddiarg_flipoverlay.htm
ms.assetid: 36ea4547-e9a0-49c9-8b45-903a2de60923
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_FLIPOVERLAY
req.alt-loc: d3dumddi.h
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
ms.keywords: D3DDDIARG_FLIPOVERLAY, D3DDDIARG_FLIPOVERLAY
req.iface: 
---

# D3DDDIARG_FLIPOVERLAY structure



## -description
<p>The D3DDDIARG_FLIPOVERLAY structure describes a new resource to display on a given overlay. </p>


## -syntax

````
typedef struct _D3DDDIARG_FLIPOVERLAY {
  HANDLE                  hOverlay;
  HANDLE                  hSource;
  UINT                    SourceIndex;
  D3DDDI_FLIPOVERLAYFLAGS Flags;
} D3DDDIARG_FLIPOVERLAY;
````


## -struct-fields
<dl>

### -field <b>hOverlay</b>

<dd>
<p>[in] A handle to the overlay hardware to be flipped. </p>
</dd>

### -field <b>hSource</b>

<dd>
<p>[in] A handle to the new resource to be displayed. This resource might be the same as the resource that was previously displayed if deinterlacing interleaved data.</p>
</dd>

### -field <b>SourceIndex</b>

<dd>
<p>[in] The zero-based index of the subresource to be displayed.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544559">D3DDDI_FLIPOVERLAYFLAGS</a> structure that indicates, in bit-field flags, how to flip the resource.</p>
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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544559">D3DDDI_FLIPOVERLAYFLAGS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/8490ebdd-f993-4c77-b6da-d57ef5e5d05f">FlipOverlay</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_FLIPOVERLAY structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>