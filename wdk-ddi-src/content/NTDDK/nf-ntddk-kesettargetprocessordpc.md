---
UID: NF.ntddk.KeSetTargetProcessorDpc
title: KeSetTargetProcessorDpc
author: windows-driver-content
description: The KeSetTargetProcessorDpc routine specifies the processor that a DPC routine will be run on.
old-location: kernel\kesettargetprocessordpc.htm
ms.assetid: 9fd86250-a495-4628-a07b-f5c44df69c0e
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeSetTargetProcessorDpc
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
req.irql: Any level
ms.keywords: KeSetTargetProcessorDpc
req.iface: 
---

# KeSetTargetProcessorDpc function



## -description
<p>The <b>KeSetTargetProcessorDpc</b> routine specifies the processor that a DPC routine will be run on.</p>


## -syntax

````
VOID KeSetTargetProcessorDpc(
  _Inout_ PRKDPC Dpc,
  _In_    CCHAR  Number
);
````


## -parameters
<dl>

### -param <i>Dpc</i> [in, out]

<dd>
<p>Pointer to the caller's DPC object, which <a href="https://msdn.microsoft.com/library/windows/hardware/ff552130">KeInitializeDpc</a> already initialized.</p>
</dd>

### -param <i>Number</i> [in]

<dd>
<p>Specifies the zero-based number of the target processor on which the DPC should be queued and executed.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>On multiprocessor systems, each processor has its own DPC queue. The <b>KeSetTargetProcessorDpc</b> routine specifies which processor's queue the system should use when the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff552185">KeInsertQueueDpc</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549657">IoRequestDpc</a> to queue a DPC to be run later.</p>

<p>Starting with Windows Vista, you can also use <b>KeSetTargetProcessorDpc</b> to specify the target processor for <a href="https://msdn.microsoft.com/library/windows/hardware/ff564621">threaded DPCs</a>.</p>

<p>A call to <b>KeSetTargetProcessorDpcEx</b> that occurs after a DPC object has been queued has no effect on the selection of a processor for the DPC routine to run on. To control the selection of the target processor, a <b>KeSetTargetProcessorDpc</b> call must occur before the call to <b>KeInsertQueueDpc</b> or <b>IoRequestDpc</b> that queues the DPC object.</p>

<p>For more information about DPC queues, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558754">Organization of DPC Queues</a>.</p>

<p>Windows 7 and later versions of Windows support processor groups. Drivers that are designed to handle information about processor groups should use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553279">KeSetTargetProcessorDpcEx</a> routine, which specifies a processor group, instead of <b>KeSetTargetProcessorDpc</b>, which does not. However, the implementation of <b>KeSetTargetProcessorDpc</b> in Windows 7 and later versions of Windows provides compatibility for drivers that were written for earlier versions of Windows, which do not support processor groups. In this implementation, if <i>Number</i> is less than the number of active logical processors in group 0, <b>KeSetTargetProcessorDpc</b> sets the target for the DPC to the processor in group 0 that is specified by <i>Number</i>. Otherwise, the DPC target does not change.</p>

<p>On multiprocessor systems, each processor has its own DPC queue. The <b>KeSetTargetProcessorDpc</b> routine specifies which processor's queue the system should use when the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff552185">KeInsertQueueDpc</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549657">IoRequestDpc</a> to queue a DPC to be run later.</p>

<p>Starting with Windows Vista, you can also use <b>KeSetTargetProcessorDpc</b> to specify the target processor for <a href="https://msdn.microsoft.com/library/windows/hardware/ff564621">threaded DPCs</a>.</p>

<p>A call to <b>KeSetTargetProcessorDpcEx</b> that occurs after a DPC object has been queued has no effect on the selection of a processor for the DPC routine to run on. To control the selection of the target processor, a <b>KeSetTargetProcessorDpc</b> call must occur before the call to <b>KeInsertQueueDpc</b> or <b>IoRequestDpc</b> that queues the DPC object.</p>

<p>For more information about DPC queues, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558754">Organization of DPC Queues</a>.</p>

<p>Windows 7 and later versions of Windows support processor groups. Drivers that are designed to handle information about processor groups should use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553279">KeSetTargetProcessorDpcEx</a> routine, which specifies a processor group, instead of <b>KeSetTargetProcessorDpc</b>, which does not. However, the implementation of <b>KeSetTargetProcessorDpc</b> in Windows 7 and later versions of Windows provides compatibility for drivers that were written for earlier versions of Windows, which do not support processor groups. In this implementation, if <i>Number</i> is less than the number of active logical processors in group 0, <b>KeSetTargetProcessorDpc</b> sets the target for the DPC to the processor in group 0 that is specified by <i>Number</i>. Otherwise, the DPC target does not change.</p>

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
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549657">IoRequestDpc</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552063">KeGetCurrentProcessorNumber</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552130">KeInitializeDpc</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552185">KeInsertQueueDpc</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553259">KeSetImportanceDpc</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553279">KeSetTargetProcessorDpcEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeSetTargetProcessorDpc routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>