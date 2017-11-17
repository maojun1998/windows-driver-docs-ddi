---
UID: NS.d3dumddi._DXVAHDDDI_SURFACE
title: DXVAHDDDI_SURFACE
author: windows-driver-content
description: The DXVAHDDDI_SURFACE structure describes a surface.
old-location: display\dxvahdddi_surface.htm
ms.assetid: a0bfc9bf-777e-4da4-9414-856ec650375d
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_SURFACE is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_SURFACE
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
ms.keywords: DXVAHDDDI_SURFACE, DXVAHDDDI_SURFACE
req.iface: 
---

# DXVAHDDDI_SURFACE structure



## -description
<p>The DXVAHDDDI_SURFACE structure describes a surface. </p>


## -syntax

````
typedef struct _DXVAHDDDI_SURFACE {
  HANDLE hResource;
  UINT   SubResourceIndex;
} DXVAHDDDI_SURFACE;
````


## -struct-fields
<dl>

### -field <b>hResource</b>

<dd>
<p>[in] A handle to the resource that contains the surface. </p>
</dd>

### -field <b>SubResourceIndex</b>

<dd>
<p>[in] The zero-based index into the resource, which the handle in the <b>hResource</b> member specifies. The <b>SubResourceIndex</b> index indicates the surface. </p>
</dd>
</dl>

## -remarks
<p>DXVAHDDDI_SURFACE structures are used to describe surfaces in members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563066">DXVAHDDDI_STREAM_DATA</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543101">D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD</a> structures in a call to the driver's <a href="https://msdn.microsoft.com/62451fc4-92cc-4553-80cc-0843cf734a62">VideoProcessBltHD</a> function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>DXVAHDDDI_SURFACE is supported beginning with the Windows 7 operating system.</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543101">D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563066">DXVAHDDDI_STREAM_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/62451fc4-92cc-4553-80cc-0843cf734a62">VideoProcessBltHD</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_SURFACE structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>