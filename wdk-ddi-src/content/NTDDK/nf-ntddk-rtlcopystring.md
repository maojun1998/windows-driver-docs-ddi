---
UID: NF.ntddk.RtlCopyString
title: RtlCopyString
author: windows-driver-content
description: The RtlCopyString routine copies a source string to a destination string.
old-location: kernel\rtlcopystring.htm
ms.assetid: 5295be15-b42e-4e5b-8257-434fb9ed6c83
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlCopyString
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
req.irql: Any level (See Remarks section)
ms.keywords: RtlCopyString
req.iface: 
---

# RtlCopyString function



## -description
<p>The <b>RtlCopyString</b> routine copies a source string to a destination string.</p>


## -syntax

````
VOID RtlCopyString(
  _Out_          PSTRING DestinationString,
  _In_opt_ const STRING  *SourceString
);
````


## -parameters
<dl>

### -param <i>DestinationString</i> [out]

<dd>
<p>A pointer to the destination string buffer. </p>
</dd>

### -param <i>SourceString</i> [in, optional]

<dd>
<p>A pointer to the source string buffer. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The<i> DestinationString </i><b>Length</b> is set to zero if no source string is supplied. The <b>MaximumLength</b> and <b>Buffer</b> members of the <i>DestinationString</i> are not modified by this routine.</p>

<p>The number of bytes copied from the <i>SourceString</i> is either the length of <i>SourceString</i> or the maximum length of <i>DestinationString</i>, whichever is smaller. </p>

<p>The <i>DestinationString</i> and <i>SourceString</i> buffers must be resident if the caller is running at IRQL &gt;= DISPATCH_LEVEL.</p>

<p>The<i> DestinationString </i><b>Length</b> is set to zero if no source string is supplied. The <b>MaximumLength</b> and <b>Buffer</b> members of the <i>DestinationString</i> are not modified by this routine.</p>

<p>The number of bytes copied from the <i>SourceString</i> is either the length of <i>SourceString</i> or the maximum length of <i>DestinationString</i>, whichever is smaller. </p>

<p>The <i>DestinationString</i> and <i>SourceString</i> buffers must be resident if the caller is running at IRQL &gt;= DISPATCH_LEVEL.</p>

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
<p>Available starting with Windows 2000.</p>
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
<p>Any level (See Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561817">RtlCopyUnicodeString</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlCopyString routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>