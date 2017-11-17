---
UID: NF.wdfrequest.WdfRequestMarkCancelable
title: WdfRequestMarkCancelable
author: windows-driver-content
description: The WdfRequestMarkCancelable method enables cancellation of a specified I/O request.
old-location: wdf\wdfrequestmarkcancelable.htm
ms.assetid: 1bd1ec2a-8b07-4843-84b6-6b651453328c
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
req.alt-api: WdfRequestMarkCancelable
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, EvtIoStopCancel, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, MarkCancOnCancReqLocal, ReqIsCancOnCancReq, ReqMarkCancelableSend, ReqNotCanceledLocal, RequestCompleted, RequestCompletedLocal
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
ms.keywords: WdfRequestMarkCancelable
req.iface: 
req.product: Windows 10 or later.
---

# WdfRequestMarkCancelable function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WdfRequestMarkCancelable</b> method enables cancellation of a specified I/O request.</p>


## -syntax

````
VOID WdfRequestMarkCancelable(
  _In_ WDFREQUEST             Request,
  _In_ PFN_WDF_REQUEST_CANCEL EvtRequestCancel
);
````


## -parameters
<dl>

### -param <i>Request</i> [in]

<dd>
<p>A handle to a framework request object.</p>
</dd>

### -param <i>EvtRequestCancel</i> [in]

<dd>
<p>A pointer to a driver-defined <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a> callback function, which the framework calls if it cancels the I/O request.</p>
</dd>
</dl>

## -returns
<p>None.</p>

<p>A bug check occurs if the driver supplies an invalid object handle.</p>

## -remarks
<p>After your driver has <a href="wdf.receiving_i_o_requests">received an I/O request</a> from the framework, the driver can call <b>WdfRequestMarkCancelable</b> or, starting with  KMDF version 1.9, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a> to make the request cancelable.</p>

<p>When calling <b>WdfRequestMarkCancelable</b>, your driver must specify an <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a> callback function. The framework calls the callback function if the I/O manager or another driver is attempting to cancel the I/O request.</p>

<p>If your driver uses the framework's <a href="wdf.using_automatic_synchronization">automatic synchronization</a>, the driver can call either <b>WdfRequestMarkCancelable</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a>.</p>

<p>If the driver does not use automatic synchronization, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a> instead of <b>WdfRequestMarkCancelable</b> for the following reasons:</p>

<p>If the specified request has already been canceled, <b>WdfRequestMarkCancelable</b> calls the driver's <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a> callback function before returning. If the driver acquires a spinlock before calling <b>WdfRequestMarkCancelable</b> and attempts to acquire the same spinlock inside  <i>EvtRequestCancel</i>, the same thread attempts to acquire the same spinlock twice, causing a deadlock.</p>

<p>However, because <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a> never calls <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a>, this scenario does not occur. If the request has already been canceled, <b>WdfRequestMarkCancelableEx</b> returns <b>STATUS_CANCELLED</b>. If your driver acquires a spinlock (which sets the IRQL to DISPATCH_LEVEL) before calling <b>WdfRequestMarkCancelableEx</b> and releases the spinlock (which sets the IRQL to PASSIVE_LEVEL) after <b>WdfRequestMarkCancelableEx</b> returns, the <i>EvtRequestCancel</i> callback function will not be called before the spinlock is released. Therefore, a deadlock does not occur even if the <i>EvtRequestCancel</i> callback function uses the same spinlock.</p>

<p>After a driver calls <b>WdfRequestMarkCancelable</b> to enable canceling, the request remains cancelable while the driver <a href="wdf.request_ownership">owns</a> the request object, unless the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550035">WdfRequestUnmarkCancelable</a>. </p>

<p>If a driver has called <b>WdfRequestMarkCancelable</b>, and if the driver's <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a> callback function has not executed and called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a>, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550035">WdfRequestUnmarkCancelable</a> before it calls <b>WdfRequestComplete</b> outside of the <i>EvtRequestCancel</i> callback function.</p>

<p>If the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549958">WdfRequestForwardToIoQueue</a> to forward the request to a different queue, the following rules apply:</p>

<p>I/O requests cannot be cancelable when your driver forwards them to a different queue. </p>

<p>Generally, your driver should not call <b>WdfRequestMarkCancelable</b> to enable canceling the request before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549958">WdfRequestForwardToIoQueue</a>. If the driver does make the request cancelable, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550035">WdfRequestUnmarkCancelable</a> to disable cancellation before calling <b>WdfRequestForwardToIoQueue</b>.</p>

<p>While the request is in the second queue, the framework owns it and can cancel it without notifying the driver.</p>

<p>If the driver requires cancellation notification (so that it can deallocate any resources that it might have allocated before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549958">WdfRequestForwardToIoQueue</a>), the driver should register an <a href="https://msdn.microsoft.com/1b938ee8-a5f3-4a1e-9beb-231d88aa5848">EvtIoCanceledOnQueue</a> callback function, and it should use request-specific context memory to store information about the request's resources.</p>

<p>After the framework has dequeued the request from the second queue and delivered it to the driver, the driver can call <b>WdfRequestMarkCancelable</b> to enable canceling.</p>

<p>For more information about <b>WdfRequestMarkCancelable</b>, see <a href="wdf.canceling_i_o_requests">Canceling I/O Requests</a>.</p>

<p>The following code example shows parts of two callback functions: </p>

<p>An <a href="https://msdn.microsoft.com/d6fbb153-1355-4e94-b5d3-a218bd8c565d">EvtIoRead</a> callback function that performs request-specific work (such as creating subrequests to send to an I/O target), then enables cancellation of the received I/O request.</p>

<p>An <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a> callback function that cancels an I/O request.</p>

<p>The driver must use the framework's <a href="wdf.using_automatic_synchronization">automatic synchronization</a>.</p>

<p>After your driver has <a href="wdf.receiving_i_o_requests">received an I/O request</a> from the framework, the driver can call <b>WdfRequestMarkCancelable</b> or, starting with  KMDF version 1.9, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a> to make the request cancelable.</p>

<p>When calling <b>WdfRequestMarkCancelable</b>, your driver must specify an <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a> callback function. The framework calls the callback function if the I/O manager or another driver is attempting to cancel the I/O request.</p>

<p>If your driver uses the framework's <a href="wdf.using_automatic_synchronization">automatic synchronization</a>, the driver can call either <b>WdfRequestMarkCancelable</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a>.</p>

<p>If the driver does not use automatic synchronization, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a> instead of <b>WdfRequestMarkCancelable</b> for the following reasons:</p>

<p>If the specified request has already been canceled, <b>WdfRequestMarkCancelable</b> calls the driver's <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a> callback function before returning. If the driver acquires a spinlock before calling <b>WdfRequestMarkCancelable</b> and attempts to acquire the same spinlock inside  <i>EvtRequestCancel</i>, the same thread attempts to acquire the same spinlock twice, causing a deadlock.</p>

<p>However, because <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a> never calls <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a>, this scenario does not occur. If the request has already been canceled, <b>WdfRequestMarkCancelableEx</b> returns <b>STATUS_CANCELLED</b>. If your driver acquires a spinlock (which sets the IRQL to DISPATCH_LEVEL) before calling <b>WdfRequestMarkCancelableEx</b> and releases the spinlock (which sets the IRQL to PASSIVE_LEVEL) after <b>WdfRequestMarkCancelableEx</b> returns, the <i>EvtRequestCancel</i> callback function will not be called before the spinlock is released. Therefore, a deadlock does not occur even if the <i>EvtRequestCancel</i> callback function uses the same spinlock.</p>

<p>After a driver calls <b>WdfRequestMarkCancelable</b> to enable canceling, the request remains cancelable while the driver <a href="wdf.request_ownership">owns</a> the request object, unless the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550035">WdfRequestUnmarkCancelable</a>. </p>

<p>If a driver has called <b>WdfRequestMarkCancelable</b>, and if the driver's <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a> callback function has not executed and called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a>, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550035">WdfRequestUnmarkCancelable</a> before it calls <b>WdfRequestComplete</b> outside of the <i>EvtRequestCancel</i> callback function.</p>

<p>If the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549958">WdfRequestForwardToIoQueue</a> to forward the request to a different queue, the following rules apply:</p>

<p>I/O requests cannot be cancelable when your driver forwards them to a different queue. </p>

<p>Generally, your driver should not call <b>WdfRequestMarkCancelable</b> to enable canceling the request before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549958">WdfRequestForwardToIoQueue</a>. If the driver does make the request cancelable, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550035">WdfRequestUnmarkCancelable</a> to disable cancellation before calling <b>WdfRequestForwardToIoQueue</b>.</p>

<p>While the request is in the second queue, the framework owns it and can cancel it without notifying the driver.</p>

<p>If the driver requires cancellation notification (so that it can deallocate any resources that it might have allocated before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549958">WdfRequestForwardToIoQueue</a>), the driver should register an <a href="https://msdn.microsoft.com/1b938ee8-a5f3-4a1e-9beb-231d88aa5848">EvtIoCanceledOnQueue</a> callback function, and it should use request-specific context memory to store information about the request's resources.</p>

<p>After the framework has dequeued the request from the second queue and delivered it to the driver, the driver can call <b>WdfRequestMarkCancelable</b> to enable canceling.</p>

<p>For more information about <b>WdfRequestMarkCancelable</b>, see <a href="wdf.canceling_i_o_requests">Canceling I/O Requests</a>.</p>

<p>The following code example shows parts of two callback functions: </p>

<p>An <a href="https://msdn.microsoft.com/d6fbb153-1355-4e94-b5d3-a218bd8c565d">EvtIoRead</a> callback function that performs request-specific work (such as creating subrequests to send to an I/O target), then enables cancellation of the received I/O request.</p>

<p>An <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a> callback function that cancels an I/O request.</p>

<p>The driver must use the framework's <a href="wdf.using_automatic_synchronization">automatic synchronization</a>.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544670">DeferredRequestCompleted</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545711">EvtIoStopCancel</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547261">InvalidReqAccess</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547267">InvalidReqAccessLocal</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549011">MarkCancOnCancReqLocal</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff551586">ReqIsCancOnCancReq</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff551589">ReqMarkCancelableSend</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff551596">ReqNotCanceledLocal</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff551603">RequestCompleted</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff551609">RequestCompletedLocal</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549958">WdfRequestForwardToIoQueue</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550035">WdfRequestUnmarkCancelable</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestMarkCancelable method%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>