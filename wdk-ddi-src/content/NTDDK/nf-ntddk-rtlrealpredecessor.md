---
UID: NF.ntddk.RtlRealPredecessor
title: RtlRealPredecessor
author: windows-driver-content
description: The RtlRealPredecessor routine returns a pointer to the predecessor of the specified node in the splay link tree.
old-location: ifsk\rtlrealpredecessor.htm
ms.assetid: 8cb981a4-7dea-4d42-bbde-35cf5494494b
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlRealPredecessor
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
ms.keywords: RtlRealPredecessor
req.iface: 
---

# RtlRealPredecessor function



## -description
<p>The <b>RtlRealPredecessor</b> routine returns a pointer to the predecessor of the specified node in the splay link tree. </p>


## -syntax

````
PRTL_SPLAY_LINKS RtlRealPredecessor(
  _In_ PRTL_SPLAY_LINKS Links
);
````


## -parameters
<dl>

### -param <i>Links</i> [in]

<dd>
<p>Pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. </p>
</dd>
</dl>

## -returns
<p><b>RtlRealPredecessor</b> returns a pointer to the predecessor of the node at <i>Links</i>, or <b>NULL</b> if the node has no predecessor. </p>

## -remarks
<p>The predecessor of a given node is determined as follows:</p>

<p>If the given node has a left subtree, the rightmost node in the left subtree of the node at <i>Links</i> is the predecessor. Note that <b>RtlSubtreePredecessor</b> returns the same result for this case. </p>

<p>Otherwise, the nearest ancestor node, of which the given node is a right-subtree descendant, is the predecessor. </p>

<p>Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. </p>

<p>Callers of <b>RtlRealPredecessor</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. </p>

<p>The predecessor of a given node is determined as follows:</p>

<p>If the given node has a left subtree, the rightmost node in the left subtree of the node at <i>Links</i> is the predecessor. Note that <b>RtlSubtreePredecessor</b> returns the same result for this case. </p>

<p>Otherwise, the nearest ancestor node, of which the given node is a right-subtree descendant, is the predecessor. </p>

<p>Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. </p>

<p>Callers of <b>RtlRealPredecessor</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. </p>

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
<p>This routine is available on Microsoft Windows 2000 and later. </p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>See Remarks section.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553188">RtlRealSuccessor</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553237">RtlSubtreePredecessor</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553226">RtlSplay</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlRealPredecessor routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>