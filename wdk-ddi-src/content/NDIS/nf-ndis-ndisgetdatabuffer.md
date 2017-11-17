---
UID: NF.ndis.NdisGetDataBuffer
title: NdisGetDataBuffer
author: windows-driver-content
description: Call the NdisGetDataBuffer function to gain access to a contiguous block of data from a NET_BUFFER structure.
old-location: netvista\ndisgetdatabuffer.htm
ms.assetid: 784d4c32-a517-4219-8e22-a998e0e66d69
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisGetDataBuffer
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: NdisGetDataBuffer
req.iface: 
---

# NdisGetDataBuffer function



## -description
<p>Call the 
  <b>NdisGetDataBuffer</b> function to gain access to a contiguous block of data from a 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure.</p>


## -syntax

````
PVOID NdisGetDataBuffer(
  _In_     PNET_BUFFER NetBuffer,
  _In_     ULONG       BytesNeeded,
  _In_opt_ PVOID       Storage,
  _In_     UINT        AlignMultiple,
  _In_     UINT        AlignOffset
);
````


## -parameters
<dl>

### -param <i>NetBuffer</i> [in]

<dd>
<p>A pointer to a NET_BUFFER structure.</p>
</dd>

### -param <i>BytesNeeded</i> [in]

<dd>
<p>The number of contiguous bytes of data requested.</p>
</dd>

### -param <i>Storage</i> [in, optional]

<dd>
<p>A pointer to a buffer, or <b>NULL</b> if no buffer is provided by the caller. The buffer must be greater
     than or equal in size to the number of bytes specified in 
     <i>BytesNeeded</i> . If this value is non-<b>NULL</b>, and the data requested is not contiguous, NDIS copies the
     requested data to the area indicated by 
     <i>Storage</i> .</p>
</dd>

### -param <i>AlignMultiple</i> [in]

<dd>
<p>The alignment multiple expressed in power of two. For example, 2, 4, 8, 16, and so forth. If 
     <i>AlignMultiple</i> is 1, then there is no alignment requirement.</p>
</dd>

### -param <i>AlignOffset</i> [in]

<dd>
<p>The offset, in bytes, from the alignment multiple.</p>
</dd>
</dl>

## -returns
<p><b>NdisGetDataBuffer</b> returns a pointer to the start of the contiguous data or it returns <b>NULL</b>.</p>

<p>If the 
      <b>DataLength</b> member of the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568381">NET_BUFFER_DATA</a> structure in the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure that the <i>NetBuffer</i>
      parameter points to is less than the value in the 
      <i>BytesNeeded</i> parameter, the return value is <b>NULL</b>.</p>

<p>If the requested data in the buffer is contiguous, this return value is a pointer to a location that
      NDIS provides. If the data is not contiguous, NDIS uses the 
      <i>Storage</i> parameter as follows:</p>

<p>The return value can also be <b>NULL</b> due to a low resource condition where a data buffer cannot be mapped. This may occur even if the data is contiguous or the <i>Storage</i> parameter is non-<b>NULL</b>.</p>

## -remarks
<p>Call this function to get a pointer to a network data header contained in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure. You can easily parse the
    header stored in the contiguous data block that this function returns.</p>

<p>The requested alignment requirement is expressed as a power-of-two multiple plus an offset. For
    example, if 
    <i>AlignMultiple</i> is 4 and 
    <i>AlignOffset</i> is 3 then the data address should be a multiple of 4 plus 3. If necessary, NDIS will
    allocate memory to satisfy the alignment requirement.</p>

<p>Call this function to get a pointer to a network data header contained in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure. You can easily parse the
    header stored in the contiguous data block that this function returns.</p>

<p>The requested alignment requirement is expressed as a power-of-two multiple plus an offset. For
    example, if 
    <i>AlignMultiple</i> is 4 and 
    <i>AlignOffset</i> is 3 then the data address should be a multiple of 4 plus 3. If necessary, NDIS will
    allocate memory to satisfy the alignment requirement.</p>

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
<p>Supported in NDIS 6.0 and later.</p>
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
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547985">Irql_NetBuffer_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568381">NET_BUFFER_DATA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetDataBuffer function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>