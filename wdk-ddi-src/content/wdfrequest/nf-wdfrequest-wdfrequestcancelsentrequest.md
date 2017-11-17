---
UID: NF.wdfrequest.WdfRequestCancelSentRequest
title: WdfRequestCancelSentRequest
author: windows-driver-content
description: The WdfRequestCancelSentRequest method attempts to cancel an I/O request that the caller previously submitted to an I/O target.
old-location: wdf\wdfrequestcancelsentrequest.htm
ms.assetid: 24319054-5e5c-4330-86e5-b1527c48eaf2
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfRequestCancelSentRequest
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, EvtIoStopCancel, EvtIoStopCompleteOrStopAck, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); 
WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
ms.keywords: WdfRequestCancelSentRequest
req.iface: 
req.product: Windows 10 or later.
---

# WdfRequestCancelSentRequest function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WdfRequestCancelSentRequest</b> method attempts to cancel an I/O request that the caller previously submitted to an I/O target.</p>


## -syntax

````
BOOLEAN WdfRequestCancelSentRequest(
  _In_ WDFREQUEST Request
);
````


## -parameters
<dl>

### -param <i>Request</i> [in]

<dd>
<p>A handle to a framework request object.</p>
</dd>
</dl>

## -returns
<p><b>WdfRequestCancelSentRequest</b> returns <b>TRUE</b> if it successfully delivers the cancel request to the driver's I/O target. This method returns <b>FALSE</b> if the request has already been completed or canceled, or if the I/O target driver has not called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549983">WdfRequestMarkCancelable</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a>.</p>

<p>A bug check occurs if the driver supplies an invalid object handle.

</p>

## -remarks
<p>A driver can call <b>WdfRequestCancelSentRequest</b> to attempt to cancel an I/O request that it previously had sent to an I/O target by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>.</p>

<p>If the request is in the I/O target's queue, the framework cancels the request. If the framework has already delivered the request to the I/O target's driver, and if that driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549983">WdfRequestMarkCancelable</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a> to enable canceling, the framework calls that driver's <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a> callback function. If the target's driver has not called <b>WdfRequestMarkCancelable</b> or <b>WdfRequestMarkCancelableEx</b>, the request is not canceled unless the request becomes cancelable.</p>

<p>If the driver has registered a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function for the request, the framework calls the callback function after the request has been canceled.</p>

<p>Typically, if your driver calls <b>WdfRequestCancelSentRequest</b>, it must increment the request object's reference count. For more information, see <a href="wdf.synchronizing_cancellation_of_sent_requests">Synchronizing Cancellation of Sent Requests</a>.</p>

<p>For more information about request cancellation, see <a href="wdf.canceling_i_o_requests">Canceling I/O Requests</a>.</p>

<p>The following code example is from the <a href="http://go.microsoft.com/fwlink/p/?linkid=256131">kmdf_fx2</a> sample driver. This example is an <a href="https://msdn.microsoft.com/71a789f1-4f10-44c3-8bd0-a0ea74ec28ab">EvtIoStop</a> callback function. Because this driver sends each request to its I/O target, the <i>EvtIoStop</i> callback function calls <b>WdfRequestCancelSentRequest</b> if the device has been removed.</p>

<p>A driver can call <b>WdfRequestCancelSentRequest</b> to attempt to cancel an I/O request that it previously had sent to an I/O target by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>.</p>

<p>If the request is in the I/O target's queue, the framework cancels the request. If the framework has already delivered the request to the I/O target's driver, and if that driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549983">WdfRequestMarkCancelable</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a> to enable canceling, the framework calls that driver's <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a> callback function. If the target's driver has not called <b>WdfRequestMarkCancelable</b> or <b>WdfRequestMarkCancelableEx</b>, the request is not canceled unless the request becomes cancelable.</p>

<p>If the driver has registered a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function for the request, the framework calls the callback function after the request has been canceled.</p>

<p>Typically, if your driver calls <b>WdfRequestCancelSentRequest</b>, it must increment the request object's reference count. For more information, see <a href="wdf.synchronizing_cancellation_of_sent_requests">Synchronizing Cancellation of Sent Requests</a>.</p>

<p>For more information about request cancellation, see <a href="wdf.canceling_i_o_requests">Canceling I/O Requests</a>.</p>

<p>The following code example is from the <a href="http://go.microsoft.com/fwlink/p/?linkid=256131">kmdf_fx2</a> sample driver. This example is an <a href="https://msdn.microsoft.com/71a789f1-4f10-44c3-8bd0-a0ea74ec28ab">EvtIoStop</a> callback function. Because this driver sends each request to its I/O target, the <i>EvtIoStop</i> callback function calls <b>WdfRequestCancelSentRequest</b> if the device has been removed.</p>

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
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfrequest.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545711">EvtIoStopCancel</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545713">EvtIoStopCompleteOrStopAck</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547261">InvalidReqAccess</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547267">InvalidReqAccessLocal</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549983">WdfRequestMarkCancelable</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestCancelSentRequest method%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>