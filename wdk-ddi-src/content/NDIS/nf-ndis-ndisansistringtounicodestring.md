---
UID: NF.ndis.NdisAnsiStringToUnicodeString
title: NdisAnsiStringToUnicodeString
author: windows-driver-content
description: The NdisAnsiStringToUnicodeString function converts a given counted ANSI string into a counted Unicode string. The translation conforms to the current system locale information.
old-location: netvista\ndisansistringtounicodestring.htm
ms.assetid: 8efdcf9f-df8c-4b3b-8b21-11a10a885322
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlAnsiStringToUnicodeString instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisAnsiStringToUnicodeString
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: NdisAnsiStringToUnicodeString
req.iface: 
---

# NdisAnsiStringToUnicodeString function



## -description
<p>The 
  <b>NdisAnsiStringToUnicodeString</b> function converts a given counted ANSI string into a counted Unicode
  string. The translation conforms to the current system locale information.</p>


## -syntax

````
NDIS_STATUS NdisAnsiStringToUnicodeString(
  _Inout_ PUNICODE_STRING DestinationString,
  _In_    PANSI_STRING    SourceString
);
````


## -parameters
<dl>

### -param <i>DestinationString</i> [in, out]

<dd>
<p>A pointer to a caller-allocated buffer in which this function should return the converted Unicode
     string.</p>
</dd>

### -param <i>SourceString</i> [in]

<dd>
<p>A pointer to the ANSI string to be converted.</p>
</dd>
</dl>

## -returns
<p><b>NdisAnsiStringToUnicodeString</b> returns NDIS_STATUS_SUCCESS if the conversion succeeds. Otherwise,
     the contents of the buffer at 
     <i>DestinationString</i> are unaffected.</p>

## -remarks
<p>The caller must allocate storage for both the source and destination strings and release these buffers
    as soon as the strings are no longer needed. The buffer at 
    <i>DestinationString</i> must be at least twice the size of the buffer at 
    <i>SourceString</i> .</p>

<p>The caller must allocate storage for both the source and destination strings and release these buffers
    as soon as the strings are no longer needed. The buffer at 
    <i>DestinationString</i> must be at least twice the size of the buffer at 
    <i>SourceString</i> .</p>

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
<p>Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff561729">RtlAnsiStringToUnicodeString</a> instead.</p>
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
<p>PASSIVE_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547982">Irql_Miscellaneous_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/cd668a59-f74f-427b-880a-9352a7e09fa8">DriverEntry of NDIS Protocol
   Drivers</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561934">RtlInitUnicodeString</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562969">RtlUnicodeStringToAnsiString</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAnsiStringToUnicodeString function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>