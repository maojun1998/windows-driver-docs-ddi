---
UID: NC.d3d10umddi.PFND3D11_1DDI_RESOURCECOPYREGION
title: PFND3D11_1DDI_RESOURCECOPYREGION
author: windows-driver-content
description: Copies a source subresource region to a location on a destination subresource.
old-location: display\resourcecopyregion_d3d11_1_.htm
ms.assetid: CA26FB37-1A4C-4057-90A5-64FFBE289E39
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ResourceCopyRegion(D3D11_1)
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

# PFND3D11_1DDI_RESOURCECOPYREGION callback



## -description
<p>Copies a source subresource region to a location on a destination subresource.</p>


## -prototype

````
PFND3D11_1DDI_RESOURCECOPYREGION ResourceCopyRegion(D3D11_1);

VOID APIENTRY* ResourceCopyRegion(D3D11_1)(
  _In_           D3D10DDI_HDEVICE   hDevice,
  _In_           D3D10DDI_HRESOURCE hDstResource,
  _In_           UINT               DstSubresource,
  _In_           UINT               DstX,
  _In_           UINT               DstY,
  _In_           UINT               DstZ,
  _In_           D3D10DDI_HRESOURCE hSrcResource,
  _In_           UINT               SrcSubresource,
  _In_opt_ const D3D10_DDI_BOX      *pSrcBox,
                 UINT               	copyFlags
)
{ ... }
````


## -parameters
<dl>

### -param <i>hDevice</i> [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param <i>hDstResource</i> [in]

<dd>
<p> A handle to the destination resource to copy to.</p>
</dd>

### -param <i>DstSubresource</i> [in]

<dd>
<p> An index that indicates the destination subresource to copy to. </p>
</dd>

### -param <i>DstX</i> [in]

<dd>
<p> The x-coordinate of the destination subresource. </p>
</dd>

### -param <i>DstY</i> [in]

<dd>
<p> The y-coordinate of the destination subresource. For one-dimensional (1-D) subresources, <i>DstY</i> is set to zero.</p>
</dd>

### -param <i>DstZ</i> [in]

<dd>
<p> The z-coordinate of the destination subresource. For one-dimensional (1-D) and two-dimensional (2-D) subresources, <i>DstZ</i> is set to zero.</p>
</dd>

### -param <i>hSrcResource</i> [in]

<dd>
<p> A handle to the source resource to copy from.</p>
</dd>

### -param <i>SrcSubresource</i> [in]

<dd>
<p> An index that indicates the source subresource to copy from. </p>
</dd>

### -param <i>pSrcBox</i> [in, optional]

<dd>
<p> A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541925">D3D10_DDI_BOX</a> structure that specifies a box that fits on either the source or destination subresource. If <i>pSrcBox</i> is <b>NULL</b>, the driver should copy the entire source subresouce to the destination.</p>
<p>If the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541925">D3D10_DDI_BOX</a> structure are such that <b>left</b>&gt;=<b>right</b>, <b>top</b>&gt;=<b>bottom</b>, or <b>front</b>&gt;=<b>back</b>, then <i>pSrcBox</i> is considered empty, and <i>ResourceCopyRegion(D3D11_1)</i> must not perform any copy operation.</p>
</dd>

### -param <i>	copyFlags</i> 

<dd>
<p>[in] A value that specifies characteristics of copy operation as a bitwise <b>OR</b> of the values in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451047">D3D11_1_DDI_COPY_FLAGS</a> enumeration type.</p>
</dd>
</dl>

## -returns
<p>None</p>

<p>The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section. </p>

## -remarks
<p>The Microsoft Direct3D runtime calls the user-mode display driver's <i>ResourceCopyRegion(D3D11_1)</i> function to inform the driver to copy from the specified source subresource region to a location on the specified destination subresource. The source and destination subresources can be the same subresource of the same resource. Both source and destination resources must be the same type of resource and must have format types (DXGI_FORMAT-typed values) that are convertible to each other. </p>

<p>For buffers, all the coordinates must be in bytes; whereas for textures, all the coordinates must be in pixels. The box that the <i>pSrcBox</i> parameter points to must not extend over the edges of the source subresource region or the destination subresource. The source and the destination resource must not be currently mapped. In addition, the resource creation flags restrict whether the resource can participate in the copy operation. </p>

<p>The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of  (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.</p>

<p>The driver can implement a <i>ResourceCopyRegion(D3D11_1)</i> function that can contain a <b>switch</b> statement to process copying and conversion. That is, the driver can implement one <i>ResourceCopyRegion(D3D11_1)</i> and can set the <b>pfnResourceConvertRegion</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406443">D3D11_1DDI_DEVICEFUNCS</a> structure to point to <i>ResourceCopyRegion(D3D11_1)</i> along with the <b>pfnResourceCopyRegion</b> member of <b>D3D11_1DDI_DEVICEFUNCS</b>. However, to improve performance, the driver can implement separate <i>ResourceCopyRegion(D3D11_1)</i> and <i>ResourceConvertRegion(D3D11_1)</i> functions.</p>

<p>The following sections list conditions for copying and converting:</p>

<p><b>Copying</b></p>

<p>For copying, <i>ResourceCopyRegion(D3D11_1)</i> ensures that the source and destination resources were created through the driver's <a href="https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67">CreateResource(D3D11)</a> function with the following conditions: </p>

<p>The destination resource was not created with the D3D10_DDI_USAGE_IMMUTABLE value set in the <b>Usage</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a> structure. </p>

<p>If either the source or destination resource has the D3D10_DDI_BIND_DEPTH_STENCIL bit set in the <b>BindFlags</b> member of the D3D10DDIARG_CREATERESOURCE or is a multi-sampled resource, <i>ResourceCopyRegion(D3D11_1)</i> verifies that the <b>pSrcBox</b> parameter is <b>NULL</b>, while the <i>DstX</i>, <i>DstY</i>, and <i>DstZ</i> parameters are 0.</p>

<p>The subresource indices are in range.</p>

<p>Alignment restrictions apply to coordinates.</p>

<p>The source and destination resources are not part of the exact same subresource. </p>

<p>Each source and destination resource format that is specified in the <b>Format</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a> is in the same typeless group. </p>

<p>The source and destination resources must have the same number of samples and quality levels; except for single-sampled resources, which must only have the same number of samples. </p>

<p><i>ResourceCopyRegion(D3D11_1)</i> does not ensure that the source box that is offset by the destination offsets fits entirely on the resource. <i>ResourceCopyRegion(D3D11_1)</i> also does not ensure that no subresources are currently mapped. </p>

<p><b>Converting</b></p>

<p>For conversion, <i>ResourceCopyRegion(D3D11_1)</i> ensures that the source and destination resources were created through the driver's <a href="https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67">CreateResource(D3D11)</a> function with the following conditions:</p>

<p>The destination resource was not created with the D3D10_DDI_USAGE_IMMUTABLE value set in the <b>Usage</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a> structure. </p>

<p>If either the source or destination resource has the D3D10_DDI_BIND_DEPTH_STENCIL bit set in the <b>BindFlags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a> or is a multi-sampled resource, <i>ResourceCopyRegion(D3D11_1)</i> verifies that the <i>pSrcBox</i> parameter is <b>NULL</b>, while the <i>DstX</i>, <i>DstY</i>, and <i>DstZ</i> parameters are 0.</p>

<p>The subresource indices are in range.</p>

<p>Alignment restrictions apply to coordinates.</p>

<p>The source and destination resources are not part of the exact same subresource. </p>

<p>Each source and destination resource format that is specified in the <b>Format</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a> is in the same typeless group. </p>

<p>Each source and destination resource format that is specified in the <b>Format</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a> supports the appropriate conversion operation. </p>

<p>The source and destination resources must have the same number of samples and quality levels; except for single-sampled resources, which must only have the same number of samples. </p>

<p><i>ResourceCopyRegion(D3D11_1)</i>
      does not ensure that no subresources are currently mapped. <i>ResourceCopyRegion(D3D11_1)</i> also does not ensure that the source box that is offset by the destination offsets fits entirely on the resource.</p>

<p>The Microsoft Direct3D runtime calls the user-mode display driver's <i>ResourceCopyRegion(D3D11_1)</i> function to inform the driver to copy from the specified source subresource region to a location on the specified destination subresource. The source and destination subresources can be the same subresource of the same resource. Both source and destination resources must be the same type of resource and must have format types (DXGI_FORMAT-typed values) that are convertible to each other. </p>

<p>For buffers, all the coordinates must be in bytes; whereas for textures, all the coordinates must be in pixels. The box that the <i>pSrcBox</i> parameter points to must not extend over the edges of the source subresource region or the destination subresource. The source and the destination resource must not be currently mapped. In addition, the resource creation flags restrict whether the resource can participate in the copy operation. </p>

<p>The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of  (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.</p>

<p>The driver can implement a <i>ResourceCopyRegion(D3D11_1)</i> function that can contain a <b>switch</b> statement to process copying and conversion. That is, the driver can implement one <i>ResourceCopyRegion(D3D11_1)</i> and can set the <b>pfnResourceConvertRegion</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406443">D3D11_1DDI_DEVICEFUNCS</a> structure to point to <i>ResourceCopyRegion(D3D11_1)</i> along with the <b>pfnResourceCopyRegion</b> member of <b>D3D11_1DDI_DEVICEFUNCS</b>. However, to improve performance, the driver can implement separate <i>ResourceCopyRegion(D3D11_1)</i> and <i>ResourceConvertRegion(D3D11_1)</i> functions.</p>

<p>The following sections list conditions for copying and converting:</p>

<p><b>Copying</b></p>

<p>For copying, <i>ResourceCopyRegion(D3D11_1)</i> ensures that the source and destination resources were created through the driver's <a href="https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67">CreateResource(D3D11)</a> function with the following conditions: </p>

<p>The destination resource was not created with the D3D10_DDI_USAGE_IMMUTABLE value set in the <b>Usage</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a> structure. </p>

<p>If either the source or destination resource has the D3D10_DDI_BIND_DEPTH_STENCIL bit set in the <b>BindFlags</b> member of the D3D10DDIARG_CREATERESOURCE or is a multi-sampled resource, <i>ResourceCopyRegion(D3D11_1)</i> verifies that the <b>pSrcBox</b> parameter is <b>NULL</b>, while the <i>DstX</i>, <i>DstY</i>, and <i>DstZ</i> parameters are 0.</p>

<p>The subresource indices are in range.</p>

<p>Alignment restrictions apply to coordinates.</p>

<p>The source and destination resources are not part of the exact same subresource. </p>

<p>Each source and destination resource format that is specified in the <b>Format</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a> is in the same typeless group. </p>

<p>The source and destination resources must have the same number of samples and quality levels; except for single-sampled resources, which must only have the same number of samples. </p>

<p><i>ResourceCopyRegion(D3D11_1)</i> does not ensure that the source box that is offset by the destination offsets fits entirely on the resource. <i>ResourceCopyRegion(D3D11_1)</i> also does not ensure that no subresources are currently mapped. </p>

<p><b>Converting</b></p>

<p>For conversion, <i>ResourceCopyRegion(D3D11_1)</i> ensures that the source and destination resources were created through the driver's <a href="https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67">CreateResource(D3D11)</a> function with the following conditions:</p>

<p>The destination resource was not created with the D3D10_DDI_USAGE_IMMUTABLE value set in the <b>Usage</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a> structure. </p>

<p>If either the source or destination resource has the D3D10_DDI_BIND_DEPTH_STENCIL bit set in the <b>BindFlags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a> or is a multi-sampled resource, <i>ResourceCopyRegion(D3D11_1)</i> verifies that the <i>pSrcBox</i> parameter is <b>NULL</b>, while the <i>DstX</i>, <i>DstY</i>, and <i>DstZ</i> parameters are 0.</p>

<p>The subresource indices are in range.</p>

<p>Alignment restrictions apply to coordinates.</p>

<p>The source and destination resources are not part of the exact same subresource. </p>

<p>Each source and destination resource format that is specified in the <b>Format</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a> is in the same typeless group. </p>

<p>Each source and destination resource format that is specified in the <b>Format</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a> supports the appropriate conversion operation. </p>

<p>The source and destination resources must have the same number of samples and quality levels; except for single-sampled resources, which must only have the same number of samples. </p>

<p><i>ResourceCopyRegion(D3D11_1)</i>
      does not ensure that no subresources are currently mapped. <i>ResourceCopyRegion(D3D11_1)</i> also does not ensure that the source box that is offset by the destination offsets fits entirely on the resource.</p>

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
<a href="https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67">CreateResource(D3D11)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541925">D3D10_DDI_BOX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451047">D3D11_1_DDI_COPY_FLAGS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406443">D3D11_1DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542062">D3D11DDIARG_CREATERESOURCE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_RESOURCECOPYREGION callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>