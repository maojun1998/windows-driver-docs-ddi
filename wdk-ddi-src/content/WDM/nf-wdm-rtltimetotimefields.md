---
UID: NF.wdm.RtlTimeToTimeFields
title: RtlTimeToTimeFields
author: windows-driver-content
description: The RtlTimeToTimeFields routine converts system time into a TIME_FIELDS structure.
old-location: kernel\rtltimetotimefields.htm
ms.assetid: 128fe592-8dc1-46cf-8aa6-0f3de0896cc5
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlTimeToTimeFields
req.alt-loc: NtosKrnl.exe,Ntdll.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); 
Ntdll.dll (user mode)
req.irql: Any level (See Remarks section)
ms.keywords: RtlTimeToTimeFields
req.iface: 
req.product: Windows 10 or later.
---

# RtlTimeToTimeFields function



## -description
<p>The RtlTimeToTimeFields routine converts system time into a <b>TIME_FIELDS</b> structure.</p>


## -syntax

````
VOID RtlTimeToTimeFields(
  _In_  PLARGE_INTEGER Time,
  _Out_ PTIME_FIELDS   TimeFields
);
````


## -parameters
<dl>

### -param <i>Time</i> [in]

<dd>
<p>Pointer to a buffer containing the absolute system time as a large integer, accurate to 100-nanosecond resolution.</p>
</dd>

### -param <i>TimeFields</i> [out]

<dd>
<p>Pointer to a caller-allocated buffer, which must be at least <b>sizeof</b>(<b>TIME_FIELDS</b>), to contain the returned information. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>Callers of <b>RtlTimeToTimeFields</b> can be running at any IRQL if both input buffers are resident.</p>

<p>Callers of <b>RtlTimeToTimeFields</b> can be running at any IRQL if both input buffers are resident.</p>

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
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
<dt>NtosKrnl.exe (kernel mode); </dt>
<dt>Ntdll.dll (user mode)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545483">ExLocalTimeToSystemTime</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545622">ExSystemTimeToLocalTime</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553068">KeQuerySystemTime</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562879">RtlTimeFieldsToTime</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlTimeToTimeFields routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>