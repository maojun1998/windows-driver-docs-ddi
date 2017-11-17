---
UID: NF.vmbuskernelmodeclientlibapi.VmbChannelCleanup
title: VmbChannelCleanup
author: windows-driver-content
description: The VmbChannelCleanup function disposes of a channel that was allocated by using the VmbChannelAllocate function or initialized by using a VMBus channel initialization function.
old-location: netvista\vmbchannelcleanup.htm
ms.assetid: E079527D-1687-4A12-B86E-96C89CE458CE
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.alt-api: VmbChannelCleanup
req.alt-loc: vmbkmcl.lib,vmbkmcl.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Vmbkmcl.lib
req.dll: 
req.irql: 
ms.keywords: VmbChannelCleanup
req.iface: 
req.product: Windows 10 or later.
---

# VmbChannelCleanup function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>
<p>The <b>VmbChannelCleanup</b> function disposes of a channel that was allocated by using the <a href="https://msdn.microsoft.com/97169CF5-566E-4EF6-88AD-7B68E9FE46EC">VmbChannelAllocate</a> function  or initialized by using a  VMBus channel initialization function. </p>


## -syntax

````
VOID VmbChannelCleanup(
  _In_ __drv_freesMem(Mem) VMBCHANNEL Channel
    
);
````


## -parameters
<dl>

### -param <i>Channel
    </i> [in]

<dd>
<p>The channel to clean up. </p>
</dd>
</dl>

## -returns
<p>This function does not return a value.</p>

## -remarks
<p>If the channel was allocated by <a href="https://msdn.microsoft.com/97169CF5-566E-4EF6-88AD-7B68E9FE46EC">VmbChannelAllocate</a>, <b>VmbChannelCleanup</b> also releases the channel. </p>

<p>Before you call this function, the channel must be disabled.</p>

<p>If the channel was allocated by <a href="https://msdn.microsoft.com/97169CF5-566E-4EF6-88AD-7B68E9FE46EC">VmbChannelAllocate</a>, <b>VmbChannelCleanup</b> also releases the channel. </p>

<p>Before you call this function, the channel must be disabled.</p>

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
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.13</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>VmbusKernelModeClientLibApi.h (include VmbusKernelModeClientLibApi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Vmbkmcl.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/97169CF5-566E-4EF6-88AD-7B68E9FE46EC">VmbChannelAllocate</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelCleanup function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>