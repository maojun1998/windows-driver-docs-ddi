---
UID: NF.d3dkmthk.D3DKMTUpdateGpuVirtualAddress
title: D3DKMTUpdateGpuVirtualAddress
author: windows-driver-content
description: D3DKMTUpdateGpuVirtualAddress is a special operation used in the context of tile resources. It allows the driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates.
old-location: display\d3dkmtupdategpuvirtualaddress.htm
ms.assetid: 3390A01D-BD4B-4399-AA3E-91BB32264A13
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: display
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTUpdateGpuVirtualAddress
req.alt-loc: GDI32.dll,API-MS-Win-DX-D3DKMT-L1-1-1.dll,GDI32.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: GDI32.lib
req.dll: GDI32.dll
req.irql: 
ms.keywords: D3DKMTUpdateGpuVirtualAddress
req.iface: 
---

# D3DKMTUpdateGpuVirtualAddress function



## -description
<p><b>D3DKMTUpdateGpuVirtualAddress</b> is a special operation used in the context of tile resources. It allows the driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates. 
</p>


## -syntax

````
NTSTATUS APIENTRY D3DKMTUpdateGpuVirtualAddress(
  _In_ const D3DKMT_UPDATEGPUVIRTUALADDRESS *pData
);
````


## -parameters
<dl>

### -param <i>pData</i> [in]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906809">D3DKMT_UPDATEGPUVIRTUALADDRESS</a> structure that describes the operation.</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The device context was successfully created.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>Parameters were validated and determined to be incorrect.</p>

<p> </p>

<p>This function might also return other <b>NTSTATUS</b> values.</p>

## -remarks
<p>The range of graphics processing unit (GPU) virtual addresses in all operations (except the source of the copy operations) must belong to a single virtual address range which was obtained by calling <a href="https://msdn.microsoft.com/26A827F1-1094-4A7D-9C63-758925EE6273">ReserveGpuVirtualAddressRange</a>.   Similarly, the virtual address ranges of all sources in copy operations must belong to a single virtual address range, which was obtained by calling <i>ReserveGpuVirtualAddressRange</i>.</p>

<p>The page table updates are executed on a paging context, dedicated to the rendering context specified, and executed on the GPU only after the associated rendering context signaled <b>FenceValue</b> for the specified monitored fence object. When the page table updates are finished, the paging context signals the monitored fence object to <b>FenceValue</b>+1, allowing the rendering context to do tight interlocking with the page table updates.</p>

<p>The virtual address ranges in the update operations are allowed to intersect. The operations will be applied in the order they are submitted.</p>

<p>In a single <b>UpdateVirtualAddress</b> call:</p>

<p>Drivers can submit many <b>UpdateGpuVirtualAddress</b> calls, which will be queued behind the rendering fence. When the number of queued update operations exceeds 128, the calling thread will be blocked until the pervious operations are processed by the video memory manager.</p>

<p>The range of graphics processing unit (GPU) virtual addresses in all operations (except the source of the copy operations) must belong to a single virtual address range which was obtained by calling <a href="https://msdn.microsoft.com/26A827F1-1094-4A7D-9C63-758925EE6273">ReserveGpuVirtualAddressRange</a>.   Similarly, the virtual address ranges of all sources in copy operations must belong to a single virtual address range, which was obtained by calling <i>ReserveGpuVirtualAddressRange</i>.</p>

<p>The page table updates are executed on a paging context, dedicated to the rendering context specified, and executed on the GPU only after the associated rendering context signaled <b>FenceValue</b> for the specified monitored fence object. When the page table updates are finished, the paging context signals the monitored fence object to <b>FenceValue</b>+1, allowing the rendering context to do tight interlocking with the page table updates.</p>

<p>The virtual address ranges in the update operations are allowed to intersect. The operations will be applied in the order they are submitted.</p>

<p>In a single <b>UpdateVirtualAddress</b> call:</p>

<p>Drivers can submit many <b>UpdateGpuVirtualAddress</b> calls, which will be queued behind the rendering fence. When the number of queued update operations exceeds 128, the calling thread will be blocked until the pervious operations are processed by the video memory manager.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>GDI32.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>GDI32.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn906809">D3DKMT_UPDATEGPUVIRTUALADDRESS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/26A827F1-1094-4A7D-9C63-758925EE6273">ReserveGpuVirtualAddressRange</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTUpdateGpuVirtualAddress function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>