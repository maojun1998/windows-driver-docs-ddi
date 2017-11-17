---
UID: NF.fwpsk.FwpsNetBufferListGetTagForContext0
title: FwpsNetBufferListGetTagForContext0
author: windows-driver-content
description: The FwpsNetBufferListGetTagForContext0 function gets a locally unique context tag that can be used to associate packets with the callout driver.Note  FwpsNetBufferListGetTagForContext0 is a specific version of FwpsNetBufferListGetTagForContext.
old-location: netvista\fwpsnetbufferlistgettagforcontext0.htm
ms.assetid: f4b9b6ab-2251-4b8a-baf5-16c845a1a4db
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpsNetBufferListGetTagForContext0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: FwpsNetBufferListGetTagForContext0
req.iface: 
---

# FwpsNetBufferListGetTagForContext0 function



## -description
<p>The <b>FwpsNetBufferListGetTagForContext0</b> function gets a locally unique context tag that can be used to
  associate packets with the callout driver.</p>


## -syntax

````
UINT64 NTAPI FwpsNetBufferListGetTagForContext0(void);
````


## -parameters


## -returns
<p>The 
     <b>FwpsNetBufferListGetTagForContext0</b> function returns a locally unique identifier.</p>

<p>The 
     <b>FwpsNetBufferListGetTagForContext0</b> function returns a locally unique identifier.</p>

<p>The 
     <b>FwpsNetBufferListGetTagForContext0</b> function returns a locally unique identifier.</p>

## -remarks
<p>The 
    <b>FwpsNetBufferListGetTagForContext0</b> function must be called before calling 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551191">FwpsNetBufferListAssociateContext0</a>.</p>

<p>The 
    <b>FwpsNetBufferListGetTagForContext0</b> function must be called before calling 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551191">FwpsNetBufferListAssociateContext0</a>.</p>

<p>The 
    <b>FwpsNetBufferListGetTagForContext0</b> function must be called before calling 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551191">FwpsNetBufferListAssociateContext0</a>.</p>

<p>The 
    <b>FwpsNetBufferListGetTagForContext0</b> function must be called before calling 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551191">FwpsNetBufferListAssociateContext0</a>.</p>

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
<p>Available starting with  Windows 7.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Fwpkclnt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/31135396-303b-4b94-8616-a4b7be207fa1">
   FwpsNetBufferListAssociateContext0</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/bd3aa1a2-3ff5-47e4-93f6-5cb2022ec630">
   FwpsNetBufferListRemoveContext0</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/482cec75-8a21-4988-b869-639d019f9460">
   FwpsNetBufferListRetrieveContext0</a>
</dt>
<dt>
<a href="NULL">Using Packet Tagging</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsNetBufferListGetTagForContext0 function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>