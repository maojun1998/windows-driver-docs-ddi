---
UID: NF.ntddk.RtlGetElementGenericTableAvl
title: RtlGetElementGenericTableAvl
author: windows-driver-content
description: The RtlGetElementGenericTableAvl routine returns a pointer to the caller-supplied data for a particular generic Adelson-Velsky/Landis (AVL) table element.
old-location: ifsk\rtlgetelementgenerictableavl.htm
ms.assetid: c836dd4b-5c66-4302-9b2a-115cec418533
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlGetElementGenericTableAvl
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
req.irql: Any level (See Remarks)
ms.keywords: RtlGetElementGenericTableAvl
req.iface: 
---

# RtlGetElementGenericTableAvl function



## -description
<p>The <b>RtlGetElementGenericTableAvl</b> routine returns a pointer to the caller-supplied data for a particular generic Adelson-Velsky/Landis (AVL) table element. </p>


## -syntax

````
PVOID RtlGetElementGenericTableAvl(
  _In_ PRTL_AVL_TABLE Table,
  _In_ ULONG          I
);
````


## -parameters
<dl>

### -param <i>Table</i> [in]

<dd>
<p>Pointer to the generic AVL table (<a href="https://msdn.microsoft.com/library/windows/hardware/ff553327">RTL_AVL_TABLE</a>) from which the <i>I</i>th element is to be retrieved. The table must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh406465">RtlInitializeGenericTableAvl</a>.</p>
</dd>

### -param <i>I</i> [in]

<dd>
<p>Index of the element selected. This value is zero-based, so the index of the last-inserted element currently in <i>Table</i> is always one less than the value returned by <a href="https://msdn.microsoft.com/library/windows/hardware/hh406522">RtlNumberGenericTableElementsAvl</a>. </p>
</dd>
</dl>

## -returns
<p><b>RtlGetElementGenericTableAvl</b> returns a pointer to the caller-supplied data for the <i>I</i>th element in the generic AVL table. It returns <b>NULL</b> if the given <i>I</i> is too large or if the generic AVL table currently has no elements. </p>

## -remarks
<p><b>RtlGetElementGenericTableAvl</b> returns the <i>I</i>th element inserted in the generic AVL table. To retrieve the first element, set <i>I</i> to zero. To retrieve the last element, set <i>I</i> to (<a href="https://msdn.microsoft.com/library/windows/hardware/hh406522">RtlNumberGenericTableElementsAvl</a>(<i>Table</i>)-1). Note that if an element is deleted from the generic table, the indexes of all elements inserted after the deleted element are decremented. Thus an element's index might change over time. </p>

<p><b>RtlGetElementGenericTableAvl</b> is more efficient than <a href="https://msdn.microsoft.com/library/windows/hardware/hh406476">RtlLookupElementGenericTableAvl</a> if the caller can supply the index of a particular element for which the caller needs access to the associated data. However, calling <b>RtlGetElementGenericTableAvl</b> repeatedly to test for such an element is less efficient than calling <b>RtlLookupElementGenericTableAvl</b> to locate it. </p>

<p>Callers of the Rtl..GenericTable routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. </p>

<p>By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:</p>

<p>#define RTL_USE_AVL_TABLES 0</p>

<p>If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlGetElementGenericTableAvl</b> routine instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552297">RtlGetElementGenericTable</a>. In the call to <b>RtlGetElementGenericTableAvl</b>, the caller must pass a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553327">RTL_AVL_TABLE</a> table structure rather than <a href="https://msdn.microsoft.com/library/windows/hardware/ff553345">RTL_GENERIC_TABLE</a>.</p>

<p>Callers of <b>RtlGetElementGenericTableAvl</b> must be running at IRQL &lt; DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable. </p>

<p><b>RtlGetElementGenericTableAvl</b> returns the <i>I</i>th element inserted in the generic AVL table. To retrieve the first element, set <i>I</i> to zero. To retrieve the last element, set <i>I</i> to (<a href="https://msdn.microsoft.com/library/windows/hardware/hh406522">RtlNumberGenericTableElementsAvl</a>(<i>Table</i>)-1). Note that if an element is deleted from the generic table, the indexes of all elements inserted after the deleted element are decremented. Thus an element's index might change over time. </p>

<p><b>RtlGetElementGenericTableAvl</b> is more efficient than <a href="https://msdn.microsoft.com/library/windows/hardware/hh406476">RtlLookupElementGenericTableAvl</a> if the caller can supply the index of a particular element for which the caller needs access to the associated data. However, calling <b>RtlGetElementGenericTableAvl</b> repeatedly to test for such an element is less efficient than calling <b>RtlLookupElementGenericTableAvl</b> to locate it. </p>

<p>Callers of the Rtl..GenericTable routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. </p>

<p>By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:</p>

<p>#define RTL_USE_AVL_TABLES 0</p>

<p>If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlGetElementGenericTableAvl</b> routine instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552297">RtlGetElementGenericTable</a>. In the call to <b>RtlGetElementGenericTableAvl</b>, the caller must pass a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553327">RTL_AVL_TABLE</a> table structure rather than <a href="https://msdn.microsoft.com/library/windows/hardware/ff553345">RTL_GENERIC_TABLE</a>.</p>

<p>Callers of <b>RtlGetElementGenericTableAvl</b> must be running at IRQL &lt; DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable. </p>

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
<p>Available with Windows XP.</p>
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
<p>Any level (See Remarks)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439514">RtlDeleteElementGenericTableAvl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406462">RtlEnumerateGenericTableWithoutSplayingAvl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406465">RtlInitializeGenericTableAvl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406468">RtlInsertElementGenericTableAvl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406476">RtlLookupElementGenericTableAvl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406522">RtlNumberGenericTableElementsAvl</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlGetElementGenericTableAvl routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>