---
UID: NE.d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS
author: windows-driver-content
description: Defines stereo 3-D capabilities for a Microsoft Direct3D 11 video processor.
old-location: display\d3d11_1ddi_video_processor_stereo_caps.htm
ms.assetid: 02b096be-0f9e-4ea3-a13f-1c6ad7c802c9
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: display
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS
req.alt-loc: D3d10umddi.h
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
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
req.iface: 
---

# D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS enumeration



## -description
<p>Defines stereo 3-D capabilities for a Microsoft Direct3D 11 video processor.</p>


## -syntax

````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS { 
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_MONO_OFFSET         = 0x1,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_ROW_INTERLEAVED     = 0x2,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_COLUMN_INTERLEAVED  = 0x4,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_CHECKERBOARD        = 0x8,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_FLIP_MODE           = 0x10
} D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS;
````


## -enum-fields
<dl>

### -field <a id="D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_MONO_OFFSET"></a><a id="d3d11_1ddi_video_processor_stereo_caps_mono_offset"></a><b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_MONO_OFFSET</b>

<dd>
<p>The video processor supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET</b> format defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451029">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT</a> enumeration.</p>
</dd>

### -field <a id="D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_ROW_INTERLEAVED"></a><a id="d3d11_1ddi_video_processor_stereo_caps_row_interleaved"></a><b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_ROW_INTERLEAVED</b>

<dd>
<p>The video processor supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_ROW_INTERLEAVED</b> format.</p>
</dd>

### -field <a id="D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_COLUMN_INTERLEAVED"></a><a id="d3d11_1ddi_video_processor_stereo_caps_column_interleaved"></a><b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_COLUMN_INTERLEAVED</b>

<dd>
<p>The video processor supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_COLUMN_INTERLEAVED</b> 
 format.</p>
</dd>

### -field <a id="D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_CHECKERBOARD"></a><a id="d3d11_1ddi_video_processor_stereo_caps_checkerboard"></a><b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_CHECKERBOARD</b>

<dd>
<p>The video processor supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_CHECKERBOARD</b> 
format.</p>
</dd>

### -field <a id="D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_FLIP_MODE"></a><a id="d3d11_1ddi_video_processor_stereo_caps_flip_mode"></a><b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS_FLIP_MODE</b>

<dd>
<p>The video processor can flip one or both views. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451025">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE</a>.</p>
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
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451025">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451029">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS enumeration%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>