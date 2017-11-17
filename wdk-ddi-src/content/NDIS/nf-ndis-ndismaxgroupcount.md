---
UID: NF.ndis.NdisMaxGroupCount
title: NdisMaxGroupCount
author: windows-driver-content
description: The NdisMaxGroupCount function returns the maximum number of processor groups in the local computer system.
old-location: netvista\ndismaxgroupcount.htm
ms.assetid: 080707c5-cf46-4066-a241-684cdae37fee
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMaxGroupCount
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
ms.keywords: NdisMaxGroupCount
req.iface: 
---

# NdisMaxGroupCount function



## -description
<p>The
  <b>NdisMaxGroupCount</b> function returns the maximum number of processor groups in the local computer
  system.</p>


## -syntax

````
USHORT NdisMaxGroupCount(void);
````


## -parameters


## -returns
<p><b>NdisMaxGroupCount</b> returns a USHORT value for the maximum number of processor groups that are
     included in the local computer system. The number of groups is a zero-based value.</p>

<p><b>NdisMaxGroupCount</b> returns a USHORT value for the maximum number of processor groups that are
     included in the local computer system. The number of groups is a zero-based value.</p>

<p><b>NdisMaxGroupCount</b> returns a USHORT value for the maximum number of processor groups that are
     included in the local computer system. The number of groups is a zero-based value.</p>

## -remarks
<p>NDIS drivers call the 
    <b>NdisMaxGroupCount</b> function to obtain the maximum number of processor groups that are included in
    the local computer system.</p>

<p>To obtain the number of groups that are currently active, call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff560700">NdisActiveGroupCount</a> function.</p>

<p>NDIS drivers call the 
    <b>NdisMaxGroupCount</b> function to obtain the maximum number of processor groups that are included in
    the local computer system.</p>

<p>To obtain the number of groups that are currently active, call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff560700">NdisActiveGroupCount</a> function.</p>

<p>NDIS drivers call the 
    <b>NdisMaxGroupCount</b> function to obtain the maximum number of processor groups that are included in
    the local computer system.</p>

<p>To obtain the number of groups that are currently active, call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff560700">NdisActiveGroupCount</a> function.</p>

<p>NDIS drivers call the 
    <b>NdisMaxGroupCount</b> function to obtain the maximum number of processor groups that are included in
    the local computer system.</p>

<p>To obtain the number of groups that are currently active, call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff560700">NdisActiveGroupCount</a> function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.20 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560700">NdisActiveGroupCount</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMaxGroupCount function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>