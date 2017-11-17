---
UID: NS.dxgiddi._DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS
title: DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS
author: windows-driver-content
description: Used in a call to the pfnGetMultiPlaneOverlayCaps function to get overlay plane capabilities.
old-location: display\dxgi_ddi_arg_getmultiplaneoverlaycaps.htm
ms.assetid: 7e4f9610-52f4-4807-94f0-c408ecb0673c
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS
req.alt-loc: Dxgiddi.h
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
ms.keywords: DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS, DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS
req.iface: 
---

# DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS structure



## -description
<p>Used in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265493">pfnGetMultiPlaneOverlayCaps</a> function to get overlay plane capabilities.</p>


## -syntax

````
typedef struct _DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS {
  DXGI_DDI_HDEVICE                 hDevice;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID   VidPnSourceId;
  DXGI_DDI_MULTIPLANE_OVERLAY_CAPS MultiPlaneOverlayCaps;
} DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS;
````


## -struct-fields
<dl>

### -field <b>hDevice</b>

<dd>
<p>[in] A handle to the display device (graphics context) for which overlay plane capabilities are needed.</p>
<p>The Direct3D runtime passed this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a> structure when it created the device by calling the <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> routine.</p>
</dd>

### -field <b>VidPnSourceId</b>

<dd>
<p>[in] The zero-based video present network (VidPN) source identification number of the input for which the capabilities are queried.</p>
</dd>

### -field <b>MultiPlaneOverlayCaps</b>

<dd>
<p>[out] The overlay plane capabilities, given as a <a href="https://msdn.microsoft.com/library/windows/hardware/hh780285">DXGI_DDI_MULTIPLANE_OVERLAY_CAPS</a> structure.</p>
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
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dxgiddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh780285">DXGI_DDI_MULTIPLANE_OVERLAY_CAPS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265493">pfnGetMultiPlaneOverlayCaps</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>