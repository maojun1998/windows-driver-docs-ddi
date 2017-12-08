---
UID: NF.wdm.MmAllocatePagesForMdlEx
title: MmAllocatePagesForMdlEx function
author: windows-driver-content
description: The MmAllocatePagesForMdlEx routine allocates nonpaged, physical memory pages to an MDL.
old-location: kernel\mmallocatepagesformdlex.htm
old-project: kernel
ms.assetid: f860c230-01ca-4c7f-8b67-5d92a80ff906
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: MmAllocatePagesForMdlEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 with Service Pack 1 (SP1) and later versions of Windows. You should use this routine instead of MmAllocatePagesForMdl on these operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MmAllocatePagesForMdlEx
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IrqlMmApcLte
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
req.product: Windows 10 or later.
---

# MmAllocatePagesForMdlEx function



## -description
The <b>MmAllocatePagesForMdlEx</b> routine allocates nonpaged, physical memory pages to an MDL.


## -syntax

````
PMDL MmAllocatePagesForMdlEx(
  _In_ PHYSICAL_ADDRESS    LowAddress,
  _In_ PHYSICAL_ADDRESS    HighAddress,
  _In_ PHYSICAL_ADDRESS    SkipBytes,
  _In_ SIZE_T              TotalBytes,
  _In_ MEMORY_CACHING_TYPE CacheType,
  _In_ ULONG               Flags
);
````


## -parameters

### -param LowAddress [in]

Specifies the physical address of the start of the first address range from which the allocated pages can come. If <b>MmAllocatePagesForMdlEx</b> cannot allocate the requested number of bytes in the first address range, it iterates through additional address ranges to get more pages. At each iteration, <b>MmAllocatePagesForMdlEx</b> adds the value of <i>SkipBytes</i> to the previous start address to obtain the start of the next address range.

### -param HighAddress [in]

Specifies the physical address of the end of the first address range that the allocated pages can come from.

### -param SkipBytes [in]

Specifies the number of bytes to skip from the start of the previous address range that the allocated pages can come from. <i>SkipBytes</i> must be an integer multiple of the virtual memory page size, in bytes.

### -param TotalBytes [in]

Specifies the total number of bytes to allocate for the MDL.

### -param CacheType [in]

Specifies a <a href="kernel.memory_caching_type">MEMORY_CACHING_TYPE</a> value, which indicates the type of caching that is allowed for the requested memory.

### -param Flags [in]

Specifies flags for this operation. Set this parameter to zero or to the bitwise OR of one or more of the following <b>MM_ALLOCATE_<i>XXX</i></b> flag bits:
The last four items in the preceding list are supported only in Windows 7 and later versions of Windows.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param MM_DONT_ZERO_ALLOCATION
### -param 0x00000001

</td>
<td width="60%">
Do not fill the allocated pages with zeros. By default, <b>MmAllocatePagesForMdlEx</b> zeros the pages that it allocates. By skipping this operation, you can potentially improve the performance of the <b>MmAllocatePagesForMdlEx</b> call. However, you must not use this flag unless either you never expose the allocated pages to user-mode programs, or you always overwrite the original contents of the pages before you expose the allocated pages to user-mode programs.
</td>
</tr>
<tr>

### -param MM_ALLOCATE_FROM_LOCAL_NODE_ONLY
### -param 0x00000002

</td>
<td width="60%">
Allocate pages only from the ideal node. This flag applies only to multiprocessor systems that have non-uniform memory access (NUMA) architectures. Starting with Windows Vista, this flag indicates that all pages must be allocated from the ideal node of the current thread. No pages are to be allocated from other nodes. In versions of Windows earlier than Windows Vista, this flag indicates that all pages must be allocated from the local node; that is, from the node that the current processor belongs to. For more information about NUMA multiprocessor systems, see <a href="http://go.microsoft.com/fwlink/p/?linkid=155041">NUMA Support</a>.
</td>
</tr>
<tr>

### -param MM_ALLOCATE_FULLY_REQUIRED
### -param 0x00000004

</td>
<td width="60%">
A full allocation is required. Starting with Windows 7, this flag requires <b>MmAllocatePagesForMdlEx</b> to return <b>NULL</b> if it cannot allocate all the requested pages. The routine returns a non-<b>NULL</b> value only if it successfully obtains the entire requested allocation. This flag enables the memory manager to perform the allocation more efficiently in cases in which the caller requires a full allocation.
</td>
</tr>
<tr>

### -param MM_ALLOCATE_NO_WAIT
### -param 0x00000008

</td>
<td width="60%">
Do not wait. Starting with Windows 7, this flag indicates that the <b>MmAllocatePagesForMdlEx</b> call must not block the calling thread. Typically, the caller is a kernel-mode driver that is running at IRQL &lt; DISPATCH_LEVEL but cannot allow its execution to be blocked. For example, the driver might be assisting with paging or power-management operations. Regardless of whether this flag is set, <b>MmAllocatePagesForMdlEx</b> never blocks callers that are running at IRQL = DISPATCH_LEVEL.
</td>
</tr>
<tr>

### -param MM_ALLOCATE_PREFER_CONTIGUOUS
### -param 0x00000010

</td>
<td width="60%">
Allocation is performed in a way that minimizes system memory fragmentation. Starting with Windows 7, this flag indicates that the caller wants to avoid fragmenting physical memory to make more contiguous memory available to other callers. The allocated pages are not guaranteed to be (and usually are not) physically contiguous, even if plenty of contiguous memory is available. Callers that require contiguous memory should specify MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS instead of MM_ALLOCATE_PREFER_CONTIGUOUS.
</td>
</tr>
<tr>

### -param MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS
### -param 0x00000020

</td>
<td width="60%">
Contiguous memory is required. Starting with Windows 7, this flag indicates that the requested pages must be allocated as contiguous blocks of physical memory. If the <i>SkipBytes</i> parameter is zero, <b>MmAllocatePagesForMdlEx</b> either succeeds and returns a single, contiguous block, or it fails and returns <b>NULL</b>. It never returns a partial allocation. For <i>SkipBytes</i> = 0, the allocated pages satisfy the address range requirements that are specified by the <i>LowAddress</i> and <i>HighAddress</i> parameters, but the pages are subject to no special alignment restrictions. If <i>SkipBytes</i> is nonzero, <i>SkipBytes</i> must be a power of two and must be greater than or equal to PAGE_SIZE, and the <i>TotalBytes</i> parameter value must be a multiple of <i>SkipBytes</i>. In this case, the returned MDL can contain multiple blocks of contiguous pages. That is, each block is internally contiguous but the blocks are not necessarily contiguous with each other. Each block of contiguous pages is guaranteed to be exactly <i>SkipBytes</i> long and to be aligned on a <i>SkipBytes</i> boundary. Partial allocations can occur if <i>SkipBytes</i> is nonzero, but each contiguous block in a partial allocation is guaranteed to be <i>SkipBytes</i> long.
</td>
</tr>
</table>
 

## -returns
<b>MmAllocatePagesForMdlEx</b> returns one of the following:
<dl>
<dt><b>MDL pointer</b></dt>
</dl>A non-<b>NULL</b> return value is a pointer to an MDL that describes a set of physical pages in the specified address range. If the requested number of bytes is not available, the MDL describes as much physical memory as is available.
<dl>
<dt><b><b>NULL</b></b></dt>
</dl>Indicates that no physical memory pages are available in the specified address ranges, or that there is not enough memory pool for the MDL itself.

 

## -remarks
By default, the physical memory pages that <b>MmAllocatePagesForMdlEx</b> returns are not contiguous pages. Starting with Windows 7, callers can override the default behavior of this routine by setting the MM_ALLOCATE_PREFER_CONTIGUOUS or MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS flag bit in the <i>Flags</i> parameter.

<b>MmAllocatePagesForMdlEx</b> is designed for kernel-mode drivers that do not need corresponding virtual addresses (that is, they need physical pages and do not need them to be physically contiguous), and for kernel-mode drivers that can achieve substantial performance gains if physical memory for a device is allocated in a specific physical address range (for example, an AGP graphics card).

Depending on how much physical memory is currently available in the requested ranges, <b>MmAllocatePagesForMdlEx</b> might return an MDL that describes less memory than was requested. The routine also might return <b>NULL</b> if no memory was allocated. The caller should check the amount of memory that is actually allocated to the MDL.

The caller must use <a href="kernel.mmfreepagesfrommdl">MmFreePagesFromMdl</a> to release the memory pages that are described by an MDL that was created by <b>MmAllocatePagesForMdlEx</b>. After calling <b>MmFreePagesFromMdl</b>, the caller must also call <a href="kernel.exfreepool">ExFreePool</a> to release the memory that is allocated for the MDL structure.

By default, <b>MmAllocatePagesForMdlEx</b> fills the pages that it allocates with zeros. The caller can specify the MM_DONT_ZERO_ALLOCATION flag to override this default and to possibly improve performance.

The maximum amount of memory that <b>MmAllocatePagesForMdlEx</b> can allocate in a single call is (4 gigabytes - PAGE_SIZE). The routine can satisfy an allocation request for this amount only if enough pages are available.

<b>MmAllocatePagesForMdlEx</b> runs at IRQL &lt;= APC_LEVEL. In Windows Server 2008 and later versions of Windows, callers of <b>MmAllocatePagesForMdlEx </b>are allowed to be at DISPATCH_LEVEL. However, you can improve driver performance by calling at APC_LEVEL or below.

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
Available in Windows Server 2003 with Service Pack 1 (SP1) and later versions of Windows. You should use this routine instead of <a href="kernel.mmallocatepagesformdl">MmAllocatePagesForMdl</a> on these operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
See Remarks section.
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.wdm_irqlmmapclte">IrqlMmApcLte</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.exfreepool">ExFreePool</a>
</dt>
<dt>
<a href="kernel.memory_caching_type">MEMORY_CACHING_TYPE</a>
</dt>
<dt>
<a href="kernel.mmallocatepagesformdl">MmAllocatePagesForMdl</a>
</dt>
<dt>
<a href="kernel.mmfreepagesfrommdl">MmFreePagesFromMdl</a>
</dt>
<dt>
<a href="kernel.mmmaplockedpages">MmMapLockedPages</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmAllocatePagesForMdlEx routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>