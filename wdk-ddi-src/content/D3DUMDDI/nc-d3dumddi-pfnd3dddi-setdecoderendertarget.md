---
UID: NC.d3dumddi.PFND3DDDI_SETDECODERENDERTARGET
title: PFND3DDDI_SETDECODERENDERTARGET
author: windows-driver-content
description: The SetDecodeRenderTarget function sets the render target surface for decoding operations.
old-location: display\setdecoderendertarget.htm
ms.assetid: d522b0f3-ca9c-4e79-96ad-ea9477858ef4
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SetDecodeRenderTarget
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

# PFND3DDDI_SETDECODERENDERTARGET callback



## -description
<p>The <i>SetDecodeRenderTarget</i> function sets the render target surface for decoding operations.</p>


## -prototype

````
PFND3DDDI_SETDECODERENDERTARGET SetDecodeRenderTarget;

__checkReturn HRESULT APIENTRY SetDecodeRenderTarget(
  _In_       HANDLE                          hDevice,
  _In_ const D3DDDIARG_SETDECODERENDERTARGET *pData
)
{ ... }
````


## -parameters
<dl>

### -param <i>hDevice</i> [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param <i>pData</i> [in]

<dd>
<p> A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543295">D3DDDIARG_SETDECODERENDERTARGET</a> structure that describes the decode render target surface.</p>
</dd>
</dl>

## -returns
<p><i>SetDecodeRenderTarget</i> returns one of the following values:</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The render target surface is successfully set.</p><dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><p><i>SetDecodeRenderTarget</i> could not allocate the required memory for it to complete.</p>

<p> </p>

## -remarks
<p>The <i>SetDecodeRenderTarget</i> function can be called only outside of a <a href="https://msdn.microsoft.com/3e6153aa-7b21-429d-8908-1ff3a4d25e17">DecodeBeginFrame</a>/<a href="https://msdn.microsoft.com/6e8d3280-6ddc-4593-9208-c4f0c9ff254c">DecodeEndFrame</a> block. </p>

<p>Decode render targets are always created atomically through calls to the <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> function, where all of the decode buffers are indexes within a single resource. All decode render targets are created by setting the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544644">D3DDDI_RESOURCEFLAGS</a>.<b>DecodeRenderTarget</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a> structure. </p>

<p>The <i>SetDecodeRenderTarget</i> function can be called only outside of a <a href="https://msdn.microsoft.com/3e6153aa-7b21-429d-8908-1ff3a4d25e17">DecodeBeginFrame</a>/<a href="https://msdn.microsoft.com/6e8d3280-6ddc-4593-9208-c4f0c9ff254c">DecodeEndFrame</a> block. </p>

<p>Decode render targets are always created atomically through calls to the <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> function, where all of the decode buffers are indexes within a single resource. All decode render targets are created by setting the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544644">D3DDDI_RESOURCEFLAGS</a>.<b>DecodeRenderTarget</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a> structure. </p>

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
<a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543295">D3DDDIARG_SETDECODERENDERTARGET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544644">D3DDDI_RESOURCEFLAGS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/3e6153aa-7b21-429d-8908-1ff3a4d25e17">DecodeBeginFrame</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/6e8d3280-6ddc-4593-9208-c4f0c9ff254c">DecodeEndFrame</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETDECODERENDERTARGET callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>