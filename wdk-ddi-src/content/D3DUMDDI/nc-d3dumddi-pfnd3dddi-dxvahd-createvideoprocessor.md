---
UID: NC.d3dumddi.PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR
title: PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR
author: windows-driver-content
description: The CreateVideoProcessor function creates a Microsoft DirectX Video Acceleration (DirectX VA) video processor that is used to process high-definition video.
old-location: display\createvideoprocessor.htm
ms.assetid: 68a7c394-4b0f-4446-a54b-5aee6cf8a913
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateVideoProcessor is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CreateVideoProcessor
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
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
req.iface: 
---

# PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR callback



## -description
<p>The <b>CreateVideoProcessor</b> function creates a Microsoft DirectX Video Acceleration (DirectX VA) video processor that is used to process high-definition video. </p>


## -prototype

````
PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR CreateVideoProcessor;

__checkReturn HRESULT APIENTRY CreateVideoProcessor(
  _In_    HANDLE                                hDevice,
  _Inout_ D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR *pData
)
{ ... }
````


## -parameters
<dl>

### -param <i>hDevice</i> [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param <i>pData</i> [in, out]

<dd>
<p> A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543077">D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR</a> structure. On input, contains information that the driver can use. On output, the driver specifies information that the Microsoft Direct3D runtime can use.</p>
</dd>
</dl>

## -returns
<p><b>CreateVideoProcessor</b> returns one of the following values:</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The video processor is successfully created. </p><dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><p>
<a href="https://msdn.microsoft.com/68a7c394-4b0f-4446-a54b-5aee6cf8a913">CreateVideoProcessor</a> could not allocate the required memory for it to complete.</p>

<p> </p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p><i>CreateVideoProcessor</i> is supported beginning with the Windows 7 operating system.</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543077">D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451638">DestroyVideoProcessor</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>