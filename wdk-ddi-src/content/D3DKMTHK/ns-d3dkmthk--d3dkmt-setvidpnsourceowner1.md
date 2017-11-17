---
UID: NS.d3dkmthk._D3DKMT_SETVIDPNSOURCEOWNER1
title: D3DKMT_SETVIDPNSOURCEOWNER1
author: windows-driver-content
description: Describes the information, including output duplication options, needed to set or release the video present source in the path of a video present network (VidPN) topology that owns the VidPN.
old-location: display\d3dkmt_setvidpnsourceowner1.htm
ms.assetid: 3148c628-60e3-47a8-bae1-e33390af7e33
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_SETVIDPNSOURCEOWNER1
req.alt-loc: D3dkmthk.h
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
ms.keywords: D3DKMT_SETVIDPNSOURCEOWNER1, D3DKMT_SETVIDPNSOURCEOWNER1
req.iface: 
---

# D3DKMT_SETVIDPNSOURCEOWNER1 structure



## -description
<p>Describes the information, including output duplication options, needed to set or release the video present source in the path of a video present network (VidPN) topology that owns the VidPN.</p>


## -syntax

````
typedef struct _D3DKMT_SETVIDPNSOURCEOWNER1 {
  D3DKMT_SETVIDPNSOURCEOWNER    Version0;
  D3DKMT_VIDPNSOURCEOWNER_FLAGS Flags;
} D3DKMT_SETVIDPNSOURCEOWNER1;
````


## -struct-fields
<dl>

### -field <b>Version0</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff548317">D3DKMT_SETVIDPNSOURCEOWNER</a> structure that contains information needed to set or release the video present source.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/hh406671">D3DKMT_VIDPNSOURCEOWNER_FLAGS</a> structure that specifies output duplication options.</p>
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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548317">D3DKMT_SETVIDPNSOURCEOWNER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406671">D3DKMT_VIDPNSOURCEOWNER_FLAGS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SETVIDPNSOURCEOWNER1 structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>