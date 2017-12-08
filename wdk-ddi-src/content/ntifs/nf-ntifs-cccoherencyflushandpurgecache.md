---
UID: NF.ntifs.CcCoherencyFlushAndPurgeCache
title: CcCoherencyFlushAndPurgeCache function
author: windows-driver-content
description: The CcCoherencyFlushAndPurgeCache routine flushes and/or purges the cache to ensure cache coherency.
old-location: ifsk\cccoherencyflushandpurgecache.htm
old-project: ifsk
ms.assetid: 61dfdd09-1e2b-4771-a2c2-62454adc7832
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: CcCoherencyFlushAndPurgeCache
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CcCoherencyFlushAndPurgeCache
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
req.irql: PASSIVE_LEVEL
---

# CcCoherencyFlushAndPurgeCache function



## -description
The <b>CcCoherencyFlushAndPurgeCache</b> routine flushes and/or purges the cache to ensure cache coherency. Use <b>CcCoherencyFlushAndPurgeCache</b> when possible instead of an explicit flush and purge call sequence as it will invalidate user mapped views to prevent data corruption.


## -syntax

````
VOID CcCoherencyFlushAndPurgeCache(
  _In_     PSECTION_OBJECT_POINTERS SectionObjectPointer,
  _In_opt_ PLARGE_INTEGER           FileOffset,
  _In_     ULONG                    Length,
  _Out_    PIO_STATUS_BLOCK         IoStatus,
  _In_opt_ ULONG                    Flags
);
````


## -parameters

### -param SectionObjectPointer [in]

A pointer to a structure that contains the section object pointers of the file object.

### -param FileOffset [in, optional]

A pointer to a variable that specifies the starting byte offset to flush, purge, or both.

### -param Length [in]

The length, in bytes of the data to flush and/or purge starting at <i>FileOffset</i>. This parameter is ignored if a <b>NULL</b> pointer is passed to <i>FileOffset</i>.

### -param IoStatus [out]

A pointer to a caller-allocated structure that receives the final completion status and information about the operation.

### -param Flags [in, optional]

A bitmask of flags that specify how the operation is to be performed. The one flag is defined in the following table. 
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
CC_FLUSH_AND_PURGE_NO_PURGE
</td>
<td>
Flush, but do not purge the cache. This is useful for read coherency flushes.
</td>
</tr>
</table>
 

## -returns
None

## -remarks
The file must be acquired exclusively before you call <b>CcCoherencyFlushAndPurgeCache</b>.

You can flush and/or purge any byte range within a file by using the <i>FileOffset</i> and <i>Length</i> parameters. Or you can flush, purge, or both an entire file if you pass a <b>NULL</b> pointer to the <i>FileOffset</i> parameter.

A call to <b>CcCoherencyFlushAndPurgeCache</b> is a synchronous (blocking) operation, not an asynchronous (non-blocking) operation.

An <i>IoStatus</i>-&gt;<i>Status </i>value of STATUS_CACHE_PAGE_LOCKED indicates that page invalidation failed. Be aware that page invalidation can fail even if you pass CC_FLUSH_AND_PURGE_NO_PURGE in the <i>Flags</i> parameter.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows 7 and later
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or FltKernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.ccflushcache">CcFlushCache</a>
</dt>
<dt>
<a href="ifsk.ccpurgecachesection">CcPurgeCacheSection</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcCoherencyFlushAndPurgeCache routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>