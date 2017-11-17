---
UID: NF.ks.KsAllocateDefaultClock
title: KsAllocateDefaultClock
author: windows-driver-content
description: The KsAllocateDefaultClock function allocates and initializes the default clock structure.
old-location: stream\ksallocatedefaultclock.htm
ms.assetid: 5ba14903-1519-4edd-bc3c-a05cb040652d
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: stream
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsAllocateDefaultClock
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: KsAllocateDefaultClock
req.iface: 
---

# KsAllocateDefaultClock function



## -description
<p>The <b>KsAllocateDefaultClock</b> function allocates and initializes the default clock structure.</p>


## -syntax

````
NTSTATUS KsAllocateDefaultClock(
  _Out_ PKSDEFAULTCLOCK *DefaultClock
);
````


## -parameters
<dl>

### -param <i>DefaultClock</i> [out]

<dd>
<p>Specifies the caller-allocated shared default clock structure. The current time is set to zero and the state is set to KSSTATE_STOP. Upon successful completion of this routine, the structure indicated by this pointer will contain a reference to the default clock. The data returned should be treated as opaque and reserved for system use.</p>
</dd>
</dl>

## -returns
<p>The <b>KsAllocateDefaultClock</b> function returns STATUS_SUCCESS if successful, or a memory error if unsuccessful.</p>

## -remarks
<p>The internal DefaultClock.ReferenceCount element is initialized to one by the <b>KsAllocateDefaultClock</b> function. The element is incremented and decremented as each notification DPC is queued and completed. When the structure is to be freed, the element is used to determine if the owner of the clock should free the structure or if a pending DPC should free it asynchronously.</p>

<p>When the clock is no longer needed, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff562559">KsFreeDefaultClock</a> to release any resources allocated for use with the clock.</p>

<p>The internal DefaultClock.ReferenceCount element is initialized to one by the <b>KsAllocateDefaultClock</b> function. The element is incremented and decremented as each notification DPC is queued and completed. When the structure is to be freed, the element is used to determine if the owner of the clock should free the structure or if a pending DPC should free it asynchronously.</p>

<p>When the clock is no longer needed, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff562559">KsFreeDefaultClock</a> to release any resources allocated for use with the clock.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562559">KsFreeDefaultClock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560955">KsAllocateDefaultClockEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsAllocateDefaultClock function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>