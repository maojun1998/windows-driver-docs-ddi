---
UID: NF.storport.StorPortQueryPerformanceCounter
title: StorPortQueryPerformanceCounter
author: windows-driver-content
description: The current system performance counter value is queried is returned by the StorPortQueryPerformanceCounter routine.
old-location: storage\storportqueryperformancecounter.htm
ms.assetid: 6502E3AE-5841-41C9-BEB7-B00620DBF02D
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: Storage
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortQueryPerformanceCounter
req.alt-loc: Storport.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any
ms.keywords: StorPortQueryPerformanceCounter
req.iface: 
req.product: Windows 10 or later.
---

# StorPortQueryPerformanceCounter function



## -description
<p>The current system performance counter value is queried is returned by the <b>StorPortQueryPerformanceCounter</b> routine.. The performance frequency is also returned as an optional parameter.</p>


## -syntax

````
ULONG StorPortQueryPerformanceCounter(
  _In_      PVOID          HwDeviceExtension,
  _Out_opt_ PLARGE_INTEGER PerformanceFrequency,
  _Out_     PLARGE_INTEGER PerformanceCounter
);
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> [in]

<dd>
<p>A pointer to the hardware device extension for the host bus adapter (HBA).</p>
</dd>

### -param <i>PerformanceFrequency</i> [out, optional]

<dd>
<p> A pointer to a large integer to receive the current system performance frequency value. This parameter is optional and can be NULL.</p>
</dd>

### -param <i>PerformanceCounter</i> [out]

<dd>
<p>A pointer to a large integer to receive the current system performance counter value.</p>
</dd>
</dl>

## -returns
<p><b>StorPortQueryPerformanceCounter</b> returns one of the following status codes:</p><dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl><p>The performance counter value is returned in the large integer pointed to by <i>PerformanceCounter</i>.</p><dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl><p>The <i>PerformanceCounter</i> parameter is <b>NULL</b>.</p>

<p> </p>

## -remarks


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
<p>Available starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567465">StorPortQuerySystemTime</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20StorPortQueryPerformanceCounter routine%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>