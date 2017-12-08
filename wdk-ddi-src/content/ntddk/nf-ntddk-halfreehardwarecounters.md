---
UID: NF.ntddk.HalFreeHardwareCounters
title: HalFreeHardwareCounters function
author: windows-driver-content
description: The HalFreeHardwareCounters routine frees a set of hardware performance counters that was acquired in a previous call to HalAllocateHardwareCounters routine.
old-location: kernel\halfreehardwarecounters.htm
old-project: kernel
ms.assetid: 646a073b-e0c5-4d41-b60c-3935c129fb39
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: HalFreeHardwareCounters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HalFreeHardwareCounters
req.alt-loc: Hal.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib
req.dll: Hal.dll
req.irql: PASSIVE_LEVEL
---

# HalFreeHardwareCounters function



## -description
The <b>HalFreeHardwareCounters</b> routine frees a set of hardware performance counters that was acquired in a previous call to <a href="kernel.halallocatehardwarecounters">HalAllocateHardwareCounters</a> routine.


## -syntax

````
NTSTATUS HalFreeHardwareCounters(
  _In_ HANDLE CounterSetHandle
);
````


## -parameters

### -param CounterSetHandle [in]

A handle to the allocated counter resources. The caller acquired this handle in a previous call to <b>HalAllocateHardwareCounters</b>.

## -returns
<b>HalFreeHardwareCounters</b> returns STATUS_SUCCESS if the call was successful. Possible error return values include the following:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameter <i>CounterSetHandle</i> is not a valid counter resources handle.

 

## -remarks


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
Available in Windows 7 and later versions of Windows.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Hal.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>Hal.dll</dt>
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
<a href="kernel.halallocatehardwarecounters">HalAllocateHardwareCounters</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20HalFreeHardwareCounters routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>