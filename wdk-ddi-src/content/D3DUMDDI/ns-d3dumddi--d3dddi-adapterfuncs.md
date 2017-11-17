---
UID: NS.d3dumddi._D3DDDI_ADAPTERFUNCS
title: D3DDDI_ADAPTERFUNCS
author: windows-driver-content
description: The D3DDDI_ADAPTERFUNCS structure contains functions that the user-mode display driver can implement to communicate with a graphics adapter object.
old-location: display\d3dddi_adapterfuncs.htm
ms.assetid: bbf4852c-0fa5-47c0-a77e-7114b2a77549
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
req.alt-api: D3DDDI_ADAPTERFUNCS
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
ms.keywords: D3DDDI_ADAPTERFUNCS, D3DDDI_ADAPTERFUNCS
req.iface: 
---

# D3DDDI_ADAPTERFUNCS structure



## -description
<p>The D3DDDI_ADAPTERFUNCS structure contains functions that the user-mode display driver can implement to communicate with a graphics adapter object. </p>


## -syntax

````
typedef struct _D3DDDI_ADAPTERFUNCS {
  PFND3DDDI_GETCAPS      pfnGetCaps;
  PFND3DDDI_CREATEDEVICE pfnCreateDevice;
  PFND3DDDI_CLOSEADAPTER pfnCloseAdapter;
} D3DDDI_ADAPTERFUNCS;
````


## -struct-fields
<dl>

### -field <b>pfnGetCaps</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function that queries for capabilities of the graphics hardware.</p>
</dd>

### -field <b>pfnCreateDevice</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a> function that creates a representation of a display device that handles a collection of rendering state.</p>
</dd>

### -field <b>pfnCloseAdapter</b>

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/9dc7f71a-753d-41ca-8eaa-bff6536e834f">CloseAdapter</a> function that releases resources for a graphics adapter object.</p>
</dd>
</dl>

## -remarks
<p>Multiple graphics adapter objects can be created for a single physical graphics adapter.</p>

<p>The following code example demonstrates the function declarations for the functions that the members of D3DDDI_ADAPTERFUNCS point to.</p>

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
<a href="https://msdn.microsoft.com/9dc7f71a-753d-41ca-8eaa-bff6536e834f">CloseAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543226">D3DDDIARG_OPENADAPTER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/41dc9ee4-e9bc-4ebd-9b90-6446ded6ea16">OpenAdapter</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_ADAPTERFUNCS structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>