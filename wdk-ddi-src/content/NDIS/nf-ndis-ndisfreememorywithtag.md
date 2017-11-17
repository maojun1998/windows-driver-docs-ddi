---
UID: NF.ndis.NdisFreeMemoryWithTag
title: NdisFreeMemoryWithTag
author: windows-driver-content
description: The NdisFreeMemoryWithTag function is deprecated for all NDIS versions. Use NdisAllocateMemoryWithTagPriority instead.
old-location: netvista\ndisfreememorywithtag.htm
ms.assetid: c9010a08-3c62-481a-8545-253d7b24b1ac
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
req.alt-api: NdisFreeMemoryWithTag
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
req.irql: See Remarks section.
ms.keywords: NdisFreeMemoryWithTag
req.iface: 
---

# NdisFreeMemoryWithTag function



## -description
<p>The 
  <b>NdisFreeMemoryWithTag</b> function is deprecated for all NDIS versions.  Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff561606">NdisAllocateMemoryWithTagPriority</a> instead.</p>


## -syntax

````
VOID NdisFreeMemoryWithTag(
  _In_ PVOID VirtualAddress,
  _In_ ULONG Tag
);
````


## -parameters
<dl>

### -param <i>VirtualAddress</i> [in]

<dd>
<p>A pointer to the base virtual address of the allocated memory. This address was returned by the 
     <a href="https://msdn.microsoft.com/0dae26f7-0c00-4a5c-a447-825290ab6570">
     NdisAllocateMemoryWithTag</a> function.</p>
</dd>

### -param <i>Tag</i> [in]

<dd>
<p>A string, delimited by single quotation marks, with up to four characters, usually specified in
     reversed order. The NDIS-supplied default tag for this call is 'maDN', but the caller can override this
     default by supplying an explicit value.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>Because noncached memory and contiguous memory are seldom released until the allocating miniport
    driver is unloading, a caller of 
    <b>NdisFreeMemoryWithTag</b> usually is running at IRQL = PASSIVE_LEVEL for these types of de-allocations.
    In any case:</p>

<p>When a caller of 
      <b>NdisFreeMemoryWithTag</b> releases contiguous memory, it must be running at IRQL = PASSIVE_LEVEL.</p>

<p>When a caller of 
      <b>NdisFreeMemoryWithTag</b> releases noncached memory, it must be running at IRQL &lt;
      DISPATCH_LEVEL.</p>

<p>When a caller of 
      <b>NdisFreeMemoryWithTag</b> releases memory that is neither contiguous nor noncached, it must be
      running at IRQL &lt;= DISPATCH_LEVEL.</p>

<p>Because noncached memory and contiguous memory are seldom released until the allocating miniport
    driver is unloading, a caller of 
    <b>NdisFreeMemoryWithTag</b> usually is running at IRQL = PASSIVE_LEVEL for these types of de-allocations.
    In any case:</p>

<p>When a caller of 
      <b>NdisFreeMemoryWithTag</b> releases contiguous memory, it must be running at IRQL = PASSIVE_LEVEL.</p>

<p>When a caller of 
      <b>NdisFreeMemoryWithTag</b> releases noncached memory, it must be running at IRQL &lt;
      DISPATCH_LEVEL.</p>

<p>When a caller of 
      <b>NdisFreeMemoryWithTag</b> releases memory that is neither contiguous nor noncached, it must be
      running at IRQL &lt;= DISPATCH_LEVEL.</p>

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
<p>See Remarks section.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550767">NdisAllocateMemoryWithTag</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeMemoryWithTag function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>