---
UID: NS.d3dumddi._D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
title: D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
author: windows-driver-content
description: The D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure describes a Microsoft DirectX Video Acceleration (VA) video processing high definition operation to perform.
old-location: display\d3dddiarg_dxvahd_videoprocessblthd.htm
ms.assetid: 16eb6131-89d5-48da-b5f8-f51b9c37e061
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
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
ms.keywords: D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD, D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
req.iface: 
---

# D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure



## -description
<p>The D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure describes a Microsoft DirectX Video Acceleration (VA) video processing high definition operation to perform.</p>


## -syntax

````
typedef struct _D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD {
  HANDLE                      hVideoProcessor;
  DXVAHDDDI_SURFACE           OutputSurface;
  UINT                        OutputFrame;
  UINT                        StreamCount;
  const DXVAHDDDI_STREAM_DATA *pStreams;
} D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD;
````


## -struct-fields
<dl>

### -field <b>hVideoProcessor</b>

<dd>
<p>[in] A handle to the DirectX VA video processing device. The user-mode display driver returns this handle in a call to its <a href="https://msdn.microsoft.com/68a7c394-4b0f-4446-a54b-5aee6cf8a913">CreateVideoProcessor</a> function.</p>
</dd>

### -field <b>OutputSurface</b>

<dd>
<p>[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563106">DXVAHDDDI_SURFACE</a> structure that describes the output surface to which the video processor composes. </p>
</dd>

### -field <b>OutputFrame</b>

<dd>
<p>[in] A zero-based frame number of the composed output frames. </p>
</dd>

### -field <b>StreamCount</b>

<dd>
<p>[in] The number of streams to process. This number must be less than the number that the driver set in the <b>MaxStreamStates</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a> structure. </p>
</dd>

### -field <b>pStreams</b>

<dd>
<p>[in] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563066">DXVAHDDDI_STREAM_DATA</a> structures that describe the input streams to process. </p>
</dd>
</dl>

## -remarks
<p>The output surface that the <b>OutputSurface</b> member specifies, which must be one of the following surface types:</p>

<p>A video surface that is created with the DXVAHD_SURFACE_TYPE_VIDEO_OUTPUT type. </p>

<p>A render target surface or a surface that is created with D3DUSAGE_RENDERTARGET usage. </p>

<p>A swap chain. </p>

<p>A swap chain with overlay swap effect. </p>

<p>If the frame that the <b>OutputFrame</b> member specifies remains unchanged at the next process time, the driver determines that the frame is unchanged (for example, paused) in the entire video processing and composition. Therefore, the driver can use cached data to optimize the frame.</p>

<p>The driver also uses the frame that the <b>OutputFrame</b> member specifies for tagging the command, which the driver submits to the graphics processing unit (GPU).</p>

<p>Input streams are indexed from zero to less than the number that the driver sets in the <b>MaxStreamStates</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a> structure. Each stream has its own stream states associated with the stream index number. The driver processes each stream from zero index and blends on the destination surface one after another. For example, if a video stream is at index zero and a graphics stream is at index one, the driver blends the video stream on the background color and then blends the graphics stream over them.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD is supported beginning with the Windows 7 operating system.</p>
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
<a href="https://msdn.microsoft.com/68a7c394-4b0f-4446-a54b-5aee6cf8a913">CreateVideoProcessor</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563066">DXVAHDDDI_STREAM_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563106">DXVAHDDDI_SURFACE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>