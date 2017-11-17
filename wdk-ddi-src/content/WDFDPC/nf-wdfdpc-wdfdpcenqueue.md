---
UID: NF.wdfdpc.WdfDpcEnqueue
title: WdfDpcEnqueue
author: windows-driver-content
description: The WdfDpcEnqueue method schedules the execution of a DPC object's EvtDpcFunc callback function.
old-location: wdf\wdfdpcenqueue.htm
ms.assetid: 08bc78de-ba04-4845-9d22-c06cd5684f7f
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdfdpc.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDpcEnqueue
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: Any level
ms.keywords: WdfDpcEnqueue
req.iface: 
req.product: Windows 10 or later.
---

# WdfDpcEnqueue function



## -description
<p class="CCE_Message">[Applies to KMDF only]</p>
<p>The <b>WdfDpcEnqueue</b> method schedules the execution of a DPC object's <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function.</p>


## -syntax

````
BOOLEAN WdfDpcEnqueue(
  _In_ WDFDPC Dpc
);
````


## -parameters
<dl>

### -param <i>Dpc</i> [in]

<dd>
<p>A handle to a framework DPC object.</p>
</dd>
</dl>

## -returns
<p><b>WdfDpcEnqueue</b> returns <b>TRUE</b> if it successfully adds the specified DPC object to the system's DPC queue. Otherwise, the method returns <b>FALSE</b>.</p>

<p>A bug check occurs if the driver supplies an invalid object handle.

</p>

## -remarks
<p>The <b>WdfDpcEnqueue</b> method adds the specified DPC object to the system's DPC queue, if it is not already in the queue. (If the DPC object was already in the queue, the method returns <b>FALSE</b>.) When the system is not executing higher-priority tasks, it removes the DPC object from the queue and calls the object's <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function. </p>

<p>After the callback function executes, a subsequent call to <b>WdfDpcEnqueue</b> will add the DPC object back into the DPC queue.</p>

<p>For more information about using DPC objects, see <a href="wdf.servicing_an_interrupt">Servicing an Interrupt</a>.</p>

<p>The following code example schedules the execution of the callback function that is associated with a DPC object. The example uses the <b>WdfDpcEnqueue</b> method's return value as the containing function's return value. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff547140">WdfDpcCreate</a> code example shows how the DPC object was created.</p>

<p>The <b>WdfDpcEnqueue</b> method adds the specified DPC object to the system's DPC queue, if it is not already in the queue. (If the DPC object was already in the queue, the method returns <b>FALSE</b>.) When the system is not executing higher-priority tasks, it removes the DPC object from the queue and calls the object's <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function. </p>

<p>After the callback function executes, a subsequent call to <b>WdfDpcEnqueue</b> will add the DPC object back into the DPC queue.</p>

<p>For more information about using DPC objects, see <a href="wdf.servicing_an_interrupt">Servicing an Interrupt</a>.</p>

<p>The following code example schedules the execution of the callback function that is associated with a DPC object. The example uses the <b>WdfDpcEnqueue</b> method's return value as the containing function's return value. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff547140">WdfDpcCreate</a> code example shows how the DPC object was created.</p>

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
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfdpc.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
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
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547140">WdfDpcCreate</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDpcEnqueue method%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>