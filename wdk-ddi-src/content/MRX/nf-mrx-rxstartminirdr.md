---
UID: NF.mrx.RxStartMinirdr
title: RxStartMinirdr
author: windows-driver-content
description: RxStartMinirdr is called to start up a network mini-redirector that has previously called to register with RDBSS.
old-location: ifsk\rxstartminirdr.htm
ms.assetid: d5b091fa-13bf-4761-a03d-1790e7045b69
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: mrx.h
req.include-header: Mrx.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxStartMinirdr
req.alt-loc: mrx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
ms.keywords: RxStartMinirdr
req.iface: 
---

# RxStartMinirdr function



## -description
<p><b>RxStartMinirdr</b> is called to start up a network mini-redirector that has previously called to register with RDBSS. As part of <b>RxStartMinirdr</b>, RDBSS will also register the network mini-redirector driver as a universal naming convention (UNC) provider with the Multiple UNC Provider (MUP) if the driver indicates support for UNC names.</p>


## -syntax

````
NTSTATUS RxStartMinirdr(
  _In_  PRX_CONTEXT RxContext,
  _Out_ PBOOLEAN    PostToFsp
);
````


## -parameters
<dl>

### -param <i>RxContext</i> [in]

<dd>
<p>A pointer to the RX_CONTEXT structure to use to get the device object and determine if this is a file system process. </p>
</dd>

### -param <i>PostToFsp</i> [out]

<dd>
<p>A pointer to a logical value set to <b>TRUE</b> on return if the request must be posted for later processing by the file system process. </p>
</dd>
</dl>

## -returns
<p><b>RxStartMinirdr</b> returns STATUS_SUCCESS if the startup sequence was successful or one of the following error values: </p><dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl><p>The request to register as a UNC provider failed because access was denied. </p><dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl><p>The request to register as a UNC provider failed with an access violation. </p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>There were insufficient resources to complete this routine.</p><dl>
<dt><b>STATUS_PENDING</b></dt>
</dl><p>The startup sequence for RDBSS and network mini-redirectors must be completed in the context of system process, not a user-mode application process. If the call to <b>RxStartMinirdr</b> comes from a user-mode process (a user-mode service request, for example), then the request is posted for later processing within RDBSS and STATUS_PENDING will be returned. This error can also be returned if certain internal RDBSS locks cannot be acquired without waiting. The call will be completed later from a system thread. </p><dl>
<dt><b>STATUS_REDIRECTOR_STARTED</b></dt>
</dl><p>The network mini-redirector was already started. </p>

<p> </p>

## -remarks
<p>A network mini-redirector registers with RDBSS whenever the driver is loaded by the kernel and then unregisters with RDBSS when the driver is unloaded. A network mini-redirector informs RDBSS that it has been loaded by calling <b>RxRegisterMinirdr</b>, the registration routine exported from RDBSS. As part of this registration process, the network mini-redirector passes a parameter to <b>RxRegisterMinirdr</b> that is a pointer to a large structure, MINIRDR_DISPATCH, which contains configuration information for the network mini-redirector and a table of pointers to callback routines implemented by the network mini-redirector driver. RDBSS uses the callback routines passed in this structure to communicate with the network mini-redirector.  </p>

<p>The network mini-redirector does not actually start operation until it receives a call to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff550829">MRxStart</a> routine, one of the callback routines passed in the MINIRDR_DISPATCH structure. The <b>MrxStart</b> callback routine must be implemented by the network mini-redirector driver if it wishes to receive callback routines for operations unless the network mini-redirector preserves its own driver dispatch entry points. Otherwise, RDBSS will only allow the following I/O request packets through to the driver until <b>MrxStart</b> returns successfully:</p>

<p>IRP requests for device create operations and device operations where the <i>FileObject-&gt;FileName.Length</i> parameter on the IRPSP is zero and the <i>FileObject-&gt;RelatedFileObject</i> parameter is <b>NULL</b>.</p>

<p>For any other IRP request, the RDBSS dispatch routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff554468">RxFsdDispatch</a> will return a status of STATUS_REDIRECTOR_NOT_STARTED. </p>

<p>The RDBSS dispatch routine will also fail any requests for the following I/O request packets:</p>

<p>IRP_MJ_CREATE_MAILSLOT</p>

<p>IRP_MJ_CREATE_NAMED_PIPE</p>

<p>The network mini-redirector <b>MrxStart</b> routine is called by RDBSS when the <b>RxStartMinirdr</b> routine is called. The RDBSS <b>RxStartMinirdr </b>routine is usually called as a result of an FSCTL or IOCTL request from a user-mode application or service to start the network mini-redirector. The call to <b>RxStartMinirdr </b>cannot be made from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine of the network mini-redirector after a successful call to <b>RxRegisterMinirdr </b>since some of the start processing requires that the driver initialization be completed. </p>

<p>When RDBSS receives an FSCTL or IOCTL request sent to network mini-redirector driver from user mode, RDBSS creates an RX_CONTEXT structure and passes this call to the network mini-redirector's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550709">MRxLowIOSubmit[LOWIO_OP_FSCTL]</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550715">MRxLowIOSubmit[LOWIO_OP_IOCTL]</a> call back routine defined in the MINIRDR_DISPATCH structure. The network mini-redirector's implementation of this call back routine would recognize the request to start and call <b>RxStartMinirdr</b>. This normal process of events is listed below in more detail:</p>

<p>A user-mode application issues a private FSCTL or IOCTL request to start the network mini-redirector.</p>

<p>The RDBSS kernel driver receives the FSCTL or IOCTL request on behalf of the network mini-redirector since RDBSS has replaced the driver dispatch entry points of the mini-redirector driver to point to RDBSS internal routines. Note that this assumes that the network mini-redirector did not set the RX_REGISTERMINI_FLAG_DONT_INIT_DRIVER_DISPATCH in the <i>Controls</i> parameter when calling <b>RxRegisterMinirdr</b>. This option passed to <b>RxRegisterMinirdr</b> would be unusual and indicates that the network mini-redirector does not want RDBSS to replace its driver dispatch entry points.</p>

<p>RDBSS receives the FSCTL or IOCTL request internally on behalf of the network redirector. The RDBSS dispatcher allocates and initializes an RX_CONTEXT structure. RDBSS then calls the network mini-redirector <b>MRxLowIOSubmit[LOW_OP_FSCTL]</b> or <b>MRxLowIOSubmit[LOW_OP_IOCTL]</b> routine defined in the MINIRDR_DISPATCH structure for this network mini-redirector, passing in the initialized RX_CONTEXT structure as a parameter.</p>

<p>The network mini-redirector implementation of this call back routine would recognize the private FSCTL or IOCTL request to start and call <b>RxStartMinirdr</b>, passing in a pointer the RX_CONTEXT structure it received from RDBSS as the <i>RxContext</i> parameter and the address of the <b>PostToFSP</b> member of <i>RxContext</i> as the <i>PostToFsp</i> parameter.</p>

<p>Since this call was initiated from user mode, <b>RxStartMinirdr</b> would return STATUS_PENDING and set <i>PostToFsp</i> to <b>TRUE</b>. </p>

<p>The network mini-redirector <b>MRxLowIOSubmit[LOW_OP_FSCTL]</b> or <b>MRxLowIOSubmit[LOW_OP_IOCTL]</b> routine would receive this return value and pass it back to the RDBSS dispatcher.</p>

<p>The RDBSS dispatcher would receive the STATUS_PENDING return value and would set <i>PostToFsp</i> to <b>TRUE</b> and would then post a request to a worker thread to re-execute the call to the network mini-redirector. </p>

<p>After this point, there are two possible outcomes based on whether the FSCTL or IOCTL was requested as an asynchronous or a synchronous operation. </p>

<p>If this were an asynchronous request, the following would occur:</p>

<p>The user-mode caller would receive the STATUS_PENDING response from the call. The posted worker thread would eventually call <b>RxStartMinirdr</b> from a file system thread and the call woud be processed. The <b>RxStartMinirdr</b> routine will try to register the network mini-redirector as a UNC provider, if requested. On versions of Windows prior to Windows Vista, RDBSS will then try to register the network mini-redirector as a file system with the I/O manager. If these calls are successful, then <b>RxStartMinirdr</b> calls the <b>MrxStart</b> callback routine implemented by the network mini-redirector. The return value from <b>MrxStart</b> would eventually be returned to the user-mode application that initiated the calling sequence process as an asynchronous operation.</p>

<p>If this were a synchronous request, the following would occur:</p>

<p>The user-mode caller would not receive the STATUS_PENDING response but would be forced to wait until the call returned from the posted worker thread. The posted worker thread would eventually call <b>RxStartMinirdr</b> from a file system thread and the call woud be processed. The <b>RxStartMinirdr</b> routine will try to register the network mini-redirector as a UNC provider, if requested. On versions of Windows prior to Windows Vista, RDBSS will then try to register the network mini-redirector as a file system with the I/O manager. If these calls are successful, then <b>RxStartMinirdr</b> calls the <b>MrxStart</b> callback routine implemented by the network mini-redirector. The return value from <b>MrxStart</b> would be returned to the user mode application that initiated the calling sequence process.</p>

<p>If a network mini-redirector indicates support for UNC when registering with RDBSS (the <i>Controls</i> parameter to <b>RxRegisterMinirdr</b>), then <b>RxStartMinirdr</b> will try to register the <i>DeviceName</i> parameter of the network mini-redirector as a UNC provider with MUP (RDBSS calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547178">FsRtlRegisterUncProvider</a> on behalf of the network mini-redirector).</p>

<p>On versions of Windows prior to Windows Vista, <b>RxStartMinirdr</b> registers the file system with the I/O manager (RDBSS calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff548494">IoRegisterFileSystem</a> on behalf of the network mini-redirector).</p>

<p>If the calls are successful, then <b>RxStartMinirdr</b> calls the network mini-redirector <b>MrxStart</b> routine. If <b>MrxStart</b> returns success, the internal state of the mini-redirector in RDBSS is set to RDBSS_STARTED. The <b>StartStopContext.Version</b> member of the mini-redirector device object will also be incremented.</p>

<p>The startup sequence for RDBSS and the network mini-redirector must be completed in the context of the system process if asynchonous operation is requested. If the call to <b>RxStartMinirdr</b> comes from a user-mode process (a user mode service request, for example), then the request will be internally posted by RDBSS to a work queue for later processing and STATUS_PENDING will be returned and the <i>PostToFsp</i> parameter will be set to <b>TRUE</b>. In addition, If certain internal RDBSS locks cannot be obtained without waiting, STATUS_PENDING is returned and <i>PostToFsp</i> is set to <b>TRUE</b>. When STATUS_PENDING is returned, <b>RxStartMinirdr</b> will be called again from within a system process. If the FSCTL or IOCTL request that initiated the call to <b>RxStartMinirdr</b> was set for asynchronous operation, then RDBSS would return STATUS_PENDING back up the call chain to the original FSCTL or IOCTL request from user mode. In contrast, if the FSCTL or IOCTL request was for synchronous operation, then the call would also be posted to a work thread for later execution, but the FSCTL or IOCTL call would not return to user mode until <b>RxStartMinirdr</b> had been executed in the context of the file system process. In this case, the caller of the FSCTL or IOCTL would never see the STATUS_PENDING error return. The more typical behavior is to initiate a synchronous request for these start/stop operations to simplify the user-mode application code.</p>

<p>On an abnormal termination or other failure, <b>RxStartMinirdr</b> will try to undo these operations, including de-registering the UNC provider with MUP, unregistering the file system, freeing memory allocated for storing the domain name to be used by mailslot broadcasts, and updating internal RDBSS tables. </p>

<p>A network mini-redirector registers with RDBSS whenever the driver is loaded by the kernel and then unregisters with RDBSS when the driver is unloaded. A network mini-redirector informs RDBSS that it has been loaded by calling <b>RxRegisterMinirdr</b>, the registration routine exported from RDBSS. As part of this registration process, the network mini-redirector passes a parameter to <b>RxRegisterMinirdr</b> that is a pointer to a large structure, MINIRDR_DISPATCH, which contains configuration information for the network mini-redirector and a table of pointers to callback routines implemented by the network mini-redirector driver. RDBSS uses the callback routines passed in this structure to communicate with the network mini-redirector.  </p>

<p>The network mini-redirector does not actually start operation until it receives a call to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff550829">MRxStart</a> routine, one of the callback routines passed in the MINIRDR_DISPATCH structure. The <b>MrxStart</b> callback routine must be implemented by the network mini-redirector driver if it wishes to receive callback routines for operations unless the network mini-redirector preserves its own driver dispatch entry points. Otherwise, RDBSS will only allow the following I/O request packets through to the driver until <b>MrxStart</b> returns successfully:</p>

<p>IRP requests for device create operations and device operations where the <i>FileObject-&gt;FileName.Length</i> parameter on the IRPSP is zero and the <i>FileObject-&gt;RelatedFileObject</i> parameter is <b>NULL</b>.</p>

<p>For any other IRP request, the RDBSS dispatch routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff554468">RxFsdDispatch</a> will return a status of STATUS_REDIRECTOR_NOT_STARTED. </p>

<p>The RDBSS dispatch routine will also fail any requests for the following I/O request packets:</p>

<p>IRP_MJ_CREATE_MAILSLOT</p>

<p>IRP_MJ_CREATE_NAMED_PIPE</p>

<p>The network mini-redirector <b>MrxStart</b> routine is called by RDBSS when the <b>RxStartMinirdr</b> routine is called. The RDBSS <b>RxStartMinirdr </b>routine is usually called as a result of an FSCTL or IOCTL request from a user-mode application or service to start the network mini-redirector. The call to <b>RxStartMinirdr </b>cannot be made from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine of the network mini-redirector after a successful call to <b>RxRegisterMinirdr </b>since some of the start processing requires that the driver initialization be completed. </p>

<p>When RDBSS receives an FSCTL or IOCTL request sent to network mini-redirector driver from user mode, RDBSS creates an RX_CONTEXT structure and passes this call to the network mini-redirector's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550709">MRxLowIOSubmit[LOWIO_OP_FSCTL]</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550715">MRxLowIOSubmit[LOWIO_OP_IOCTL]</a> call back routine defined in the MINIRDR_DISPATCH structure. The network mini-redirector's implementation of this call back routine would recognize the request to start and call <b>RxStartMinirdr</b>. This normal process of events is listed below in more detail:</p>

<p>A user-mode application issues a private FSCTL or IOCTL request to start the network mini-redirector.</p>

<p>The RDBSS kernel driver receives the FSCTL or IOCTL request on behalf of the network mini-redirector since RDBSS has replaced the driver dispatch entry points of the mini-redirector driver to point to RDBSS internal routines. Note that this assumes that the network mini-redirector did not set the RX_REGISTERMINI_FLAG_DONT_INIT_DRIVER_DISPATCH in the <i>Controls</i> parameter when calling <b>RxRegisterMinirdr</b>. This option passed to <b>RxRegisterMinirdr</b> would be unusual and indicates that the network mini-redirector does not want RDBSS to replace its driver dispatch entry points.</p>

<p>RDBSS receives the FSCTL or IOCTL request internally on behalf of the network redirector. The RDBSS dispatcher allocates and initializes an RX_CONTEXT structure. RDBSS then calls the network mini-redirector <b>MRxLowIOSubmit[LOW_OP_FSCTL]</b> or <b>MRxLowIOSubmit[LOW_OP_IOCTL]</b> routine defined in the MINIRDR_DISPATCH structure for this network mini-redirector, passing in the initialized RX_CONTEXT structure as a parameter.</p>

<p>The network mini-redirector implementation of this call back routine would recognize the private FSCTL or IOCTL request to start and call <b>RxStartMinirdr</b>, passing in a pointer the RX_CONTEXT structure it received from RDBSS as the <i>RxContext</i> parameter and the address of the <b>PostToFSP</b> member of <i>RxContext</i> as the <i>PostToFsp</i> parameter.</p>

<p>Since this call was initiated from user mode, <b>RxStartMinirdr</b> would return STATUS_PENDING and set <i>PostToFsp</i> to <b>TRUE</b>. </p>

<p>The network mini-redirector <b>MRxLowIOSubmit[LOW_OP_FSCTL]</b> or <b>MRxLowIOSubmit[LOW_OP_IOCTL]</b> routine would receive this return value and pass it back to the RDBSS dispatcher.</p>

<p>The RDBSS dispatcher would receive the STATUS_PENDING return value and would set <i>PostToFsp</i> to <b>TRUE</b> and would then post a request to a worker thread to re-execute the call to the network mini-redirector. </p>

<p>After this point, there are two possible outcomes based on whether the FSCTL or IOCTL was requested as an asynchronous or a synchronous operation. </p>

<p>If this were an asynchronous request, the following would occur:</p>

<p>The user-mode caller would receive the STATUS_PENDING response from the call. The posted worker thread would eventually call <b>RxStartMinirdr</b> from a file system thread and the call woud be processed. The <b>RxStartMinirdr</b> routine will try to register the network mini-redirector as a UNC provider, if requested. On versions of Windows prior to Windows Vista, RDBSS will then try to register the network mini-redirector as a file system with the I/O manager. If these calls are successful, then <b>RxStartMinirdr</b> calls the <b>MrxStart</b> callback routine implemented by the network mini-redirector. The return value from <b>MrxStart</b> would eventually be returned to the user-mode application that initiated the calling sequence process as an asynchronous operation.</p>

<p>If this were a synchronous request, the following would occur:</p>

<p>The user-mode caller would not receive the STATUS_PENDING response but would be forced to wait until the call returned from the posted worker thread. The posted worker thread would eventually call <b>RxStartMinirdr</b> from a file system thread and the call woud be processed. The <b>RxStartMinirdr</b> routine will try to register the network mini-redirector as a UNC provider, if requested. On versions of Windows prior to Windows Vista, RDBSS will then try to register the network mini-redirector as a file system with the I/O manager. If these calls are successful, then <b>RxStartMinirdr</b> calls the <b>MrxStart</b> callback routine implemented by the network mini-redirector. The return value from <b>MrxStart</b> would be returned to the user mode application that initiated the calling sequence process.</p>

<p>If a network mini-redirector indicates support for UNC when registering with RDBSS (the <i>Controls</i> parameter to <b>RxRegisterMinirdr</b>), then <b>RxStartMinirdr</b> will try to register the <i>DeviceName</i> parameter of the network mini-redirector as a UNC provider with MUP (RDBSS calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547178">FsRtlRegisterUncProvider</a> on behalf of the network mini-redirector).</p>

<p>On versions of Windows prior to Windows Vista, <b>RxStartMinirdr</b> registers the file system with the I/O manager (RDBSS calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff548494">IoRegisterFileSystem</a> on behalf of the network mini-redirector).</p>

<p>If the calls are successful, then <b>RxStartMinirdr</b> calls the network mini-redirector <b>MrxStart</b> routine. If <b>MrxStart</b> returns success, the internal state of the mini-redirector in RDBSS is set to RDBSS_STARTED. The <b>StartStopContext.Version</b> member of the mini-redirector device object will also be incremented.</p>

<p>The startup sequence for RDBSS and the network mini-redirector must be completed in the context of the system process if asynchonous operation is requested. If the call to <b>RxStartMinirdr</b> comes from a user-mode process (a user mode service request, for example), then the request will be internally posted by RDBSS to a work queue for later processing and STATUS_PENDING will be returned and the <i>PostToFsp</i> parameter will be set to <b>TRUE</b>. In addition, If certain internal RDBSS locks cannot be obtained without waiting, STATUS_PENDING is returned and <i>PostToFsp</i> is set to <b>TRUE</b>. When STATUS_PENDING is returned, <b>RxStartMinirdr</b> will be called again from within a system process. If the FSCTL or IOCTL request that initiated the call to <b>RxStartMinirdr</b> was set for asynchronous operation, then RDBSS would return STATUS_PENDING back up the call chain to the original FSCTL or IOCTL request from user mode. In contrast, if the FSCTL or IOCTL request was for synchronous operation, then the call would also be posted to a work thread for later execution, but the FSCTL or IOCTL call would not return to user mode until <b>RxStartMinirdr</b> had been executed in the context of the file system process. In this case, the caller of the FSCTL or IOCTL would never see the STATUS_PENDING error return. The more typical behavior is to initiate a synchronous request for these start/stop operations to simplify the user-mode application code.</p>

<p>On an abnormal termination or other failure, <b>RxStartMinirdr</b> will try to undo these operations, including de-registering the UNC provider with MUP, unregistering the file system, freeing memory allocated for storing the domain name to be used by mailslot broadcasts, and updating internal RDBSS tables. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Mrx.h (include Mrx.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547178">FsRtlRegisterUncProvider</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548494">IoRegisterFileSystem</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550709">MRxLowIOSubmit[LOWIO_OP_FSCTL]</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550715">MRxLowIOSubmit[LOWIO_OP_IOCTL]</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550829">MRxStart</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554468">RxFsdDispatch</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554693">RxRegisterMinirdr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554718">RxSetDomainForMailslotBroadcast</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554743">RxStopMinirdr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/84155e3f-8090-4b0d-a101-25ecd126bc37">, RxpUnregisterMinirdr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554744">RxUnregisterMinirdr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557374">__RxFillAndInstallFastIoDispatch</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxStartMinirdr function%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>