---
UID: NF.ndis.NdisGetProcessorInformationEx
title: NdisGetProcessorInformationEx
author: windows-driver-content
description: The NdisGetProcessorInformationEx function retrieves information about the CPU topology of the local computer.
old-location: netvista\ndisgetprocessorinformationex.htm
ms.assetid: 9af21f56-d93d-4130-888c-c7009dc2854d
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
req.alt-api: NdisGetProcessorInformationEx
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
req.irql: <= DISPATCH_LEVEL
ms.keywords: NdisGetProcessorInformationEx
req.iface: 
---

# NdisGetProcessorInformationEx function



## -description
<p>The 
  <b>NdisGetProcessorInformationEx</b> function retrieves information about the CPU topology of the local
  computer.</p>


## -syntax

````
NDIS_STATUS NdisGetProcessorInformationEx(
  _In_opt_  NDIS_HANDLE                    NdisHandle,
  _Out_opt_ PNDIS_SYSTEM_PROCESSOR_INFO_EX SystemProcessorInfo,
  _Inout_   PSIZE_T                        Size
);
````


## -parameters
<dl>

### -param <i>NdisHandle</i> [in, optional]

<dd>
<p>An NDIS driver or instance handle that was obtained during caller initialization. For example, a
     miniport driver can use the NDIS handle that it obtained from the 
     <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
     NdisMRegisterMiniportDriver</a> or 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> functions.
     Other NDIS drivers can use the handles from the following functions:
     </p>
<dl>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>
</p>
</dd>
</dl>
</dd>

### -param <i>SystemProcessorInfo</i> [out, optional]

<dd>
<p>A pointer to a caller-allocated buffer where NDIS puts the 
     <a href="https://msdn.microsoft.com/ba3c6641-98bc-4c44-9889-7583c4cf61f0">
     NDIS_SYSTEM_PROCESSOR_INFO_EX</a> structure and an array of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566811">NDIS_PROCESSOR_INFO_EX</a> structures
     that contain information about the CPU topology of the local computer. The caller provides the length of
     the buffer in the 
     <i>Size</i> parameter.</p>
</dd>

### -param <i>Size</i> [in, out]

<dd>
<p>A pointer to a value that is the size, in bytes, of the buffer that the caller provided. When the
     function returns, this value contains either the amount of data that NDIS put in the buffer or the
     required size of the buffer if the buffer was too short.</p>
</dd>
</dl>

## -returns
<p><b>NdisGetProcessorInformationEx</b> can return one of the following status values:</p><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p>The operation completed successfully.</p><dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl><p>The size of the buffer at the 
       <i>Size</i> parameter was too small. In this case, NDIS provides the required buffer size in the 
       <i>Size</i> member.</p>

<p> </p>

## -remarks
<p>NDIS drivers call the 
    <b>NdisGetProcessorInformationEx</b> function to retrieve information about the processors on the local
    computer.</p>

<p>NDIS drivers call the 
    <b>NdisGetProcessorInformationEx</b> function to retrieve information about the processors on the local
    computer.</p>

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
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567872">NDIS_SYSTEM_PROCESSOR_INFO_EX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetProcessorInformationEx function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>