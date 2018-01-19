---
UID : NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING
title : PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING
author : windows-driver-content
description : Indicates that decoder down-sampling will be used and that the driver should allocate the appropriate reference frames. Optional for Windows Display Driver Model (WDDM) 2.0 or later drivers.
old-location : display\videodecoderenabledownsampling.htm
old-project : display
ms.assetid : 0817C977-1113-4953-B60C-A69185443335
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Desktop
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : pfnVideoDecoderEnableDownsampling
req.alt-loc : D3d10umddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING callback function
Indicates that decoder down-sampling will be used and that the driver should allocate the appropriate reference frames.  Optional for Windows Display Driver Model (WDDM) 2.0 or later drivers.

## Syntax

```
PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING Pfnd3dwddm20DdiVideodecoderenabledownsampling;

HRESULT Pfnd3dwddm20DdiVideodecoderenabledownsampling(
  D3D10DDI_HDEVICE hDevice,
  D3D11_1DDI_HDECODE hDecoder,
  D3DDDI_COLOR_SPACE_TYPE InputColorSpace,
  CONST D3D11_1DDI_VIDEO_DECODER_DESC *pOutputDesc,
  D3DDDI_COLOR_SPACE_TYPE OutputColorSpace,
  UINT ReferenceFrameCount
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a> structure at device creation.

`hDecoder`

A handle to the decoder object.

`InputColorSpace`

A <a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_color_space_type.md">D3DDDI_COLOR_SPACE_TYPE</a> value that indicates the color space information of the reference frame data.

`*pOutputDesc`



`OutputColorSpace`

A <a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_color_space_type.md">D3DDDI_COLOR_SPACE_TYPE</a> value that indicates the color space information of the output/display frames.

`ReferenceFrameCount`

Indicates the number of reference frame used.


## Return Value

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

This function can only be called once, prior to the first <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe.md">VideoDecoderBeginFrame</a> call.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_color_space_type.md">D3DDDI_COLOR_SPACE_TYPE</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe.md">VideoDecoderBeginFrame</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>