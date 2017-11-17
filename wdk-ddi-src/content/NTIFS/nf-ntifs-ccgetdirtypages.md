---
UID: NF.ntifs.CcGetDirtyPages
title: CcGetDirtyPages
author: windows-driver-content
description: The CcGetDirtyPages routine searches for dirty pages in all files that match a given log handle.
old-location: ifsk\ccgetdirtypages.htm
ms.assetid: 8ca0d683-318b-465c-95a7-dc2b5e29c9e7
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available on Microsoft Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CcGetDirtyPages
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
req.irql: <= DISPATCH_LEVEL
ms.keywords: CcGetDirtyPages
req.iface: 
---

# CcGetDirtyPages function



## -description
<p>The <b>CcGetDirtyPages</b> routine searches for dirty pages in all files that match a given log handle. </p>


## -syntax

````
LARGE_INTEGER CcGetDirtyPages(
  _In_ PVOID               LogHandle,
  _In_ PDIRTY_PAGE_ROUTINE DirtyPageRoutine,
  _In_ PVOID               Context1,
  _In_ PVOID               Context2
);
````


## -parameters
<dl>

### -param <i>LogHandle</i> [in]

<dd>
<p>Log handle stored by a previous call to <b>CcSetLogHandleForFile</b>. </p>
</dd>

### -param <i>DirtyPageRoutine</i> [in]

<dd>
<p>Pointer to a callback routine that builds up a dirty page table from the pages found. This routine, which is called for each dirty page found, is declared as follows: </p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID (*PDIRTY_PAGE_ROUTINE) (
            IN PFILE_OBJECT FileObject,
            IN PLARGE_INTEGER FileOffset,
            IN ULONG Length,
            IN PLARGE_INTEGER OldestLsn,
            IN PLARGE_INTEGER NewestLsn,
            IN PVOID Context1,
            IN PVOID Context2
            );</pre>
</td>
</tr>
</table></span></div>
<p></p>
<dl>

### -param <a id="FileObject"></a><a id="fileobject"></a><a id="FILEOBJECT"></a><i>FileObject</i>

<dd>
<p>Pointer to the file object for the file containing the dirty page. </p>
</dd>

### -param <a id="FileOffset"></a><a id="fileoffset"></a><a id="FILEOFFSET"></a><i>FileOffset</i>

<dd>
<p>Pointer to a variable that specifies the starting byte offset of the dirty page within the cached file. </p>
</dd>

### -param <a id="Length"></a><a id="length"></a><a id="LENGTH"></a><i>Length</i>

<dd>
<p>Length, in bytes, of the dirty page. </p>
</dd>

### -param <a id="OldestLsn"></a><a id="oldestlsn"></a><a id="OLDESTLSN"></a><i>OldestLsn</i>

<dd>
<p>Oldest logical sequence number (LSN) found in the dirty page. </p>
</dd>

### -param <a id="NewestLsn"></a><a id="newestlsn"></a><a id="NEWESTLSN"></a><i>NewestLsn</i>

<dd>
<p>Newest LSN found in the dirty page. </p>
</dd>

### -param <a id="Context1"></a><a id="context1"></a><a id="CONTEXT1"></a><i>Context1</i>

<dd>
<p>First context parameter. </p>
</dd>

### -param <a id="Context2"></a><a id="context2"></a><a id="CONTEXT2"></a><i>Context2</i>

<dd>
<p>Second context parameter. </p>
</dd>
</dl>
</dd>

### -param <i>Context1</i> [in]

<dd>
<p>First context parameter to be passed to the <i>DirtyPageRoutine</i>. </p>
</dd>

### -param <i>Context2</i> [in]

<dd>
<p>Second context parameter to be passed to the <i>DirtyPageRoutine</i>. </p>
</dd>
</dl>

## -returns
<p><b>CcGetDirtyPages</b> returns the oldest LSN found in the set of dirty pages. If there are no dirty pages, <b>CcGetDirtyPages</b> returns zero. </p>

## -remarks
<p>File systems call <b>CcGetDirtyPages</b> to return dirty pages in all files that match a given log handle. <b>CcGetDirtyPages</b> searches for dirty pages in all files that match the given <i>LogHandle</i> and calls the <i>DirtyPageRoutine</i> for each page. </p>

<p>To set a log handle for a file, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539217">CcSetLogHandleForFile</a>. </p>

<p>File systems call <b>CcGetDirtyPages</b> to return dirty pages in all files that match a given log handle. <b>CcGetDirtyPages</b> searches for dirty pages in all files that match the given <i>LogHandle</i> and calls the <i>DirtyPageRoutine</i> for each page. </p>

<p>To set a log handle for a file, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539217">CcSetLogHandleForFile</a>. </p>

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
<p>Available on Microsoft Windows XP and later. </p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
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
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539211">CcSetDirtyPinnedData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539217">CcSetLogHandleForFile</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcGetDirtyPages routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>