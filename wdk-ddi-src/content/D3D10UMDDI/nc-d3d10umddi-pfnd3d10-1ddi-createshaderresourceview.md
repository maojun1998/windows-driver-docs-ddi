---
UID: NC.d3d10umddi.PFND3D10_1DDI_CREATESHADERRESOURCEVIEW
title: PFND3D10_1DDI_CREATESHADERRESOURCEVIEW
author: windows-driver-content
description: The CreateShaderResourceView(D3D10_1) function creates a shader resource view.
old-location: display\createshaderresourceview_d3d10_1_.htm
ms.assetid: 7a0a92d2-a5df-4bee-a950-8a89aeb3dbb8
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateShaderResourceView(D3D10_1) is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CreateShaderResourceView_d3d10_1_
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
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
req.iface: 
---

# PFND3D10_1DDI_CREATESHADERRESOURCEVIEW callback



## -description
<p>The <b>CreateShaderResourceView(D3D10_1)</b> function creates a shader resource view.</p>


## -prototype

````
PFND3D10_1DDI_CREATESHADERRESOURCEVIEW CreateShaderResourceView_d3d10_1_;

VOID APIENTRY CreateShaderResourceView_d3d10_1_(
  _In_       D3D10DDI_HDEVICE                       hDevice,
  _In_ const D3D10_1DDIARG_CREATESHADERRESOURCEVIEW pCreateShaderResourceView,
  _In_       D3D10DDI_HSHADERRESOURCEVIEW           hShaderResourceView,
  _In_       D3D10DDI_HRTSHADERRESOURCEVIEW         hRTShaderResourceView
)
{ ... }
````


## -parameters
<dl>

### -param <i>hDevice</i> [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param <i>pCreateShaderResourceView</i> [in]

<dd>
<p> A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541861">D3D10_1DDIARG_CREATESHADERRESOURCEVIEW</a> structure that describes the parameters that the user-mode display driver uses to create a shader resource view. </p>
</dd>

### -param <i>hShaderResourceView</i> [in]

<dd>
<p> A handle to the driver's private data for the shader resource view. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/310adb3e-1af4-430e-ba50-bd145ffda361">CalcPrivateShaderResourceViewSize(D3D10_1)</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its shader resource view object. </p>
</dd>

### -param <i>hRTShaderResourceView</i> [in]

<dd>
<p> A handle to the shader resource view that the driver should use anytime it calls back into the Direct3D runtime. </p>
</dd>
</dl>

## -returns
<p>None</p>

<p>The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section.</p>

## -remarks
<p>The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://msdn.microsoft.com/dcdfe76e-a392-4a76-91fe-03648fec1278">DestroyShaderResourceView</a> function to destroy the handle that the <i>hShaderResourceView</i> parameter specifies.</p>

<p>The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://msdn.microsoft.com/dcdfe76e-a392-4a76-91fe-03648fec1278">DestroyShaderResourceView</a> function to destroy the handle that the <i>hShaderResourceView</i> parameter specifies.</p>

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
<p><i>CreateShaderResourceView(D3D10_1)</i> is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions. </p>
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
<a href="https://msdn.microsoft.com/310adb3e-1af4-430e-ba50-bd145ffda361">CalcPrivateShaderResourceViewSize(D3D10_1)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541873">D3D10_1DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541861">D3D10_1DDIARG_CREATESHADERRESOURCEVIEW</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/dcdfe76e-a392-4a76-91fe-03648fec1278">DestroyShaderResourceView</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10_1DDI_CREATESHADERRESOURCEVIEW callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>