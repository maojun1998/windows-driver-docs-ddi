---
UID: NS.d3d10umddi.D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW
title: D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW
author: windows-driver-content
description: The D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW structure describes a one-dimensional texture (1-D) that is used to create an unordered access view in a call to the CreateUnorderedAccessView function.
old-location: display\d3d11ddiarg_tex1d_unorderedaccessview.htm
ms.assetid: aeee9194-2824-43ff-8225-4c0ef666e44f
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW
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
ms.keywords: D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW, D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW
req.iface: 
---

# D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW structure



## -description
<p>The D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW structure describes a one-dimensional texture (1-D) that is used to create an unordered access view in a call to the <a href="https://msdn.microsoft.com/c5a258e7-6645-46bb-ab2c-a1c8f5e593b7">CreateUnorderedAccessView</a> function. </p>


## -syntax

````
typedef struct D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW {
  UINT MipSlice;
  UINT FirstArraySlice;
  UINT ArraySize;
} D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW;
````


## -struct-fields
<dl>

### -field <b>MipSlice</b>

<dd>
<p>[in] The identifier of the MIP-map slice. </p>
</dd>

### -field <b>FirstArraySlice</b>

<dd>
<p>[in] The identifier of the first array slice. </p>
</dd>

### -field <b>ArraySize</b>

<dd>
<p>[in] The number of array slices for the texture. </p>
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
<p>D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW is supported beginning with the Windows 7 operating system. </p>
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
<a href="https://msdn.microsoft.com/6aca5d33-c8c6-4c6b-a66a-e28a958cbc2e">CalcPrivateUnorderedAccessViewSize</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/c5a258e7-6645-46bb-ab2c-a1c8f5e593b7">CreateUnorderedAccessView</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542086">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>