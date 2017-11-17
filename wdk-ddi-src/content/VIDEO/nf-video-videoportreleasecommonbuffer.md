---
UID: NF.video.VideoPortReleaseCommonBuffer
title: VideoPortReleaseCommonBuffer
author: windows-driver-content
description: The VideoPortReleaseCommonBuffer function frees a common buffer that was previously allocated by VideoPortAllocateCommonBuffer.
old-location: display\videoportreleasecommonbuffer.htm
ms.assetid: b3733de1-63ef-43b8-b669-dbe7e573b499
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: display
req.header: video.h
req.include-header: Video.h, Ntdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VideoPortReleaseCommonBuffer
req.alt-loc: Videoprt.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
ms.keywords: VideoPortReleaseCommonBuffer
req.iface: 
req.product: Windows 10 or later.
---

# VideoPortReleaseCommonBuffer function



## -description
<p>The <b>VideoPortReleaseCommonBuffer</b> function frees a common buffer that was previously allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570178">VideoPortAllocateCommonBuffer</a>.</p>


## -syntax

````
VOID VideoPortReleaseCommonBuffer(
  _In_ PVOID            HwDeviceExtension,
  _In_ PVP_DMA_ADAPTER  VpDmaAdapter,
  _In_ ULONG            Length,
  _In_ PHYSICAL_ADDRESS LogicalAddress,
  _In_ PVOID            VirtualAddress,
  _In_ BOOLEAN          CacheEnabled
);
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> [in]

<dd>
<p>Pointer to the miniport driver's device extension.</p>
</dd>

### -param <i>VpDmaAdapter</i> [in]

<dd>
<p>Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a> structure that represents the bus-master adapter. This is the structure returned after a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570312">VideoPortGetDmaAdapter</a>.</p>
</dd>

### -param <i>Length</i> [in]

<dd>
<p>Specifies the number of bytes of memory to be freed.</p>
</dd>

### -param <i>LogicalAddress</i> [in]

<dd>
<p>Specifies the logical address of the buffer to be freed.</p>
</dd>

### -param <i>VirtualAddress</i> [in]

<dd>
<p>Pointer to the corresponding virtual address of the allocated memory range. This value was obtained in a prior call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570178">VideoPortAllocateCommonBuffer</a>.</p>
</dd>

### -param <i>CacheEnabled</i> [in]

<dd>
<p>Indicates whether the allocated memory is cached. A value of <b>TRUE</b> indicates that the allocated memory is cached.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The parameters passed to <b>VideoPortFreeCommonBuffer</b> must match exactly those passed to and returned from <b>VideoPortAllocateCommonBuffer</b>. A driver cannot free only part of an allocated common buffer. </p>

<p>The parameters passed to <b>VideoPortFreeCommonBuffer</b> must match exactly those passed to and returned from <b>VideoPortAllocateCommonBuffer</b>. A driver cannot free only part of an allocated common buffer. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows XP and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h or Ntdef.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570178">VideoPortAllocateCommonBuffer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570312">VideoPortGetDmaAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortReleaseCommonBuffer function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>