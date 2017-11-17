---
UID: NS.d3dumddi._D3DDDIARG_TEXTURESTAGESTATE
title: D3DDDIARG_TEXTURESTAGESTATE
author: windows-driver-content
description: The D3DDDIARG_TEXTURESTAGESTATE structure describes how to update a texture at a particular stage in a multiple-texture group.
old-location: display\d3dddiarg_texturestagestate.htm
ms.assetid: 4810ec13-ec58-4ed6-ae4f-6690bd72cd8a
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
req.alt-api: D3DDDIARG_TEXTURESTAGESTATE
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
ms.keywords: D3DDDIARG_TEXTURESTAGESTATE, D3DDDIARG_TEXTURESTAGESTATE
req.iface: 
---

# D3DDDIARG_TEXTURESTAGESTATE structure



## -description
<p>The D3DDDIARG_TEXTURESTAGESTATE structure describes how to update a texture at a particular stage in a multiple-texture group. </p>


## -syntax

````
typedef struct _D3DDDIARG_TEXTURESTAGESTATE {
  UINT                        Stage;
  D3DDDITEXTURESTAGESTATETYPE State;
  UINT                        Value;
} D3DDDIARG_TEXTURESTAGESTATE;
````


## -struct-fields
<dl>

### -field <b>Stage</b>

<dd>
<p>[in] The stage in a multiple-texture group that indicates the texture to be updated. This member can be an integer in the range from 0 through 7, with the highest numbered texture being closest to the frame buffer.</p>
</dd>

### -field <b>State</b>

<dd>
<p>[in] A D3DDDITEXTURESTAGESTATETYPE-typed value that indicates the texture state to be updated. </p>
<p>Microsoft DirectX 9.0 and later applications can use values in the D3DSAMPLERSTATETYPE enumeration type to control the characteristics of sampler texture-related render states. In DirectX 8.0 and earlier, these sampler states were included in the D3DTEXTURESTAGESTATETYPE enumeration. The runtime maps sampler states (D3DSAMP_<i>Xxx</i>) to D3DDDITSS_<i>Xxx</i> values so that drivers are not required to process sampler states. For more information about D3DTEXTURESTAGESTATETYPE and D3DSAMPLERSTATETYPE, see the DirectX SDK documentation.</p>
<p>For a definition of each value, see the corresponding value of D3DTEXTURESTAGESTATETYPE or D3DSAMPLERSTATETYPE.</p>
<p>The following texture states are used exclusively by user-mode display drivers for texture colorkeying:</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>D3DDDITSS_DISABLETEXTURECOLORKEY (33)</p>
</td>
<td>
<p>Disable the current texture's colorkey. The <b>Value</b> member is set to <b>TRUE</b> to disable.</p>
</td>
</tr>
<tr>
<td>
<p>D3DDDITSS_TEXTURECOLORKEYVAL (34)</p>
</td>
<td>
<p>Update the colorkey for the current texture. The <b>Value</b> member is set to the colorkey value.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field <b>Value</b>

<dd>
<p>[in] The value to which the driver should update the texture state that is identified by the <b>Stage</b> and <b>State</b> members. For more information about values that can be updated for each texture state, see the definitions of the corresponding texture state in the D3DTEXTURESTAGESTATETYPE or D3DSAMPLERSTATETYPE enumeration type in the DirectX SDK documentation.</p>
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
<a href="https://msdn.microsoft.com/56b9d7bf-1036-4ad1-a0fb-4d7154b50b27">SetTextureStageState</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_TEXTURESTAGESTATE structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>