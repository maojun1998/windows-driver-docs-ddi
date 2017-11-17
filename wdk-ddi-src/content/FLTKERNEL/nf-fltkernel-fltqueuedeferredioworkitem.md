---
UID: NF.fltkernel.FltQueueDeferredIoWorkItem
title: FltQueueDeferredIoWorkItem
author: windows-driver-content
description: The FltQueueDeferredIoWorkItem routine posts an IRP-based I/O operation to a work queue.
old-location: ifsk\fltqueuedeferredioworkitem.htm
ms.assetid: c6a51b9b-544e-4595-842a-76c667928350
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available in Microsoft Windows 2000 and later versions of all Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltQueueDeferredIoWorkItem
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: <= DISPATCH_LEVEL
ms.keywords: FltQueueDeferredIoWorkItem
req.iface: 
---

# FltQueueDeferredIoWorkItem function



## -description
<p>The <b>FltQueueDeferredIoWorkItem</b> routine posts an IRP-based I/O operation to a work queue. </p>


## -syntax

````
NTSTATUS FltQueueDeferredIoWorkItem(
  _In_ PFLT_DEFERRED_IO_WORKITEM         FltWorkItem,
  _In_ PFLT_CALLBACK_DATA                Data,
  _In_ PFLT_DEFERRED_IO_WORKITEM_ROUTINE WorkerRoutine,
  _In_ WORK_QUEUE_TYPE                   QueueType,
  _In_ PVOID                             Context
);
````


## -parameters
<dl>

### -param <i>FltWorkItem</i> [in]

<dd>
<p>A pointer to the work item to add to the work queue. The work item must have been allocated by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541720">FltAllocateDeferredIoWorkItem</a>. </p>
</dd>

### -param <i>Data</i> [in]

<dd>
<p>A pointer to the callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure for the I/O operation. The operation must be an IRP-based I/O operation. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. </p>
</dd>

### -param <i>WorkerRoutine</i> [in]

<dd>
<p>A pointer to a caller-supplied worker routine. This routine is declared as follows: </p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*PFLT_DEFERRED_IO_WORKITEM_ROUTINE) (
      _in PFLT_DEFERRED_IO_WORKITEM  FltWorkItem,
      __in PFLT_CALLBACK_DATA  CallbackData,
      __in_opt PVOID  Context
      );</pre>
</td>
</tr>
</table></span></div>
<p></p>
<dl>

### -param <a id="FltWorkItem"></a><a id="fltworkitem"></a><a id="FLTWORKITEM"></a><i>FltWorkItem</i>

<dd>
<p>An opaque pointer to a deferred work item structure. </p>
</dd>

### -param <a id="CallbackData"></a><a id="callbackdata"></a><a id="CALLBACKDATA"></a><i>CallbackData</i>

<dd>
<p>A pointer to the callback data structure for the I/O operation. </p>
</dd>

### -param <a id="Context"></a><a id="context"></a><a id="CONTEXT"></a><i>Context</i>

<dd>
<p>An optional context information pointer that was passed as the <i>Context</i> parameter of <b>FltQueueDeferredIoWorkItem</b>. </p>
</dd>
</dl>
</dd>

### -param <i>QueueType</i> [in]

<dd>
<p>This parameter specifies the queue into which the work item that <i>FltWorkItem</i> points to is to be inserted. <i>QueueType</i> can be either of the following. </p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p><b>CriticalWorkQueue</b></p>
</td>
<td>
<p>Insert the work item into the queue from which a system thread with a real-time priority attribute processes the work item. </p>
</td>
</tr>
<tr>
<td>
<p><b>DelayedWorkQueue</b></p>
</td>
<td>
<p>Insert the work item into the queue from which a system thread with a variable priority attribute processes the work item. </p>
</td>
</tr>
</table>
<p> </p>
<p>The <i>QueueType</i> value <b>HyperCriticalWorkQueue</b> is reserved for system use. </p>
</dd>

### -param <i>Context</i> [in]

<dd>
<p>A pointer to caller-defined context information to be passed as the <i>Context</i> parameter of the callback routine specified in the <i>WorkerRoutine</i> parameter. </p>
</dd>
</dl>

## -returns
<p>The <b>FltQueueDeferredIoWorkItem</b> routine returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: </p><dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl><p>The target instance for the I/O operation (<i>Data-&gt;Iopb-&gt;TargetInstance</i>) is being torn down. This is an error code. </p><dl>
<dt><b>STATUS_FLT_NOT_SAFE_TO_POST_OPERATION</b></dt>
</dl><p>The I/O operation cannot be posted safely to a worker thread. Possible reasons include the following: </p>

<p><b>FltQueueDeferredIoWorkItem</b> cannot post an I/O operation to a worker thread if the <b>TopLevelIrp</b> field of the current thread is not <b>NULL</b>, because the resulting file system recursion could cause deadlocks or stack overflows. (For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548405">IoGetTopLevelIrp</a>.) </p>

<p><b>FltQueueDeferredIoWorkItem</b> cannot post a paging I/O operation to a worker thread. </p>

<p>STATUS_FLT_NOT_SAFE_TO_POST_OPERATION is an error code. </p>

<p> </p>

## -remarks
<p>The <b>FltQueueDeferredIoWorkItem</b> routine posts an I/O operation to a system work queue. The specified <i>WorkerRoutine</i> callback routine is called in the context of a system thread, at IRQL PASSIVE_LEVEL. </p>

<p>The operation must be an IRP-based I/O operation. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. </p>

<p>A minifilter driver can use <b>FltQueueDeferredIoWorkItem</b> in a preoperation callback (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>) routine as follows: </p>

<p>The preoperation callback calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff541720">FltAllocateDeferredIoWorkItem</a> to allocate the work item. </p>

<p>The preoperation callback calls <b>FltQueueDeferredIoWorkItem</b> to post the operation to the work queue. </p>

<p>The preoperation callback returns FLT_PREOP_PENDING. </p>

<p>After processing the I/O operation, the work routine calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff541913">FltCompletePendedPreOperation</a> to return the I/O operation to the Filter Manager. </p>

<p>The work routine calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff542955">FltFreeDeferredIoWorkItem</a> to free the work item. </p>

<p>A minifilter driver can use <b>FltQueueDeferredIoWorkItem</b> in a post-operation callback (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>) routine as follows: </p>

<p>The post-operation callback calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff541720">FltAllocateDeferredIoWorkItem</a> to allocate the work item. </p>

<p>The post-operation callback calls <b>FltQueueDeferredIoWorkItem</b> to post the operation to the work queue. </p>

<p>The post-operation callback returns FLT_POSTOP_MORE_PROCESSING_REQUIRED. </p>

<p>After processing the I/O operation, the work routine calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff541897">FltCompletePendedPostOperation</a> to return the I/O operation to the Filter Manager. </p>

<p>The work routine calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff542955">FltFreeDeferredIoWorkItem</a> to free the work item. </p>

<p>IRP_MJ_READ</p>

<p>IRP_MJ_WRITE</p>

<p>IRP_MJ_FLUSH_BUFFERS</p>

<p>The <b>FltQueueDeferredIoWorkItem</b> routine posts an I/O operation to a system work queue. The specified <i>WorkerRoutine</i> callback routine is called in the context of a system thread, at IRQL PASSIVE_LEVEL. </p>

<p>The operation must be an IRP-based I/O operation. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. </p>

<p>A minifilter driver can use <b>FltQueueDeferredIoWorkItem</b> in a preoperation callback (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>) routine as follows: </p>

<p>The preoperation callback calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff541720">FltAllocateDeferredIoWorkItem</a> to allocate the work item. </p>

<p>The preoperation callback calls <b>FltQueueDeferredIoWorkItem</b> to post the operation to the work queue. </p>

<p>The preoperation callback returns FLT_PREOP_PENDING. </p>

<p>After processing the I/O operation, the work routine calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff541913">FltCompletePendedPreOperation</a> to return the I/O operation to the Filter Manager. </p>

<p>The work routine calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff542955">FltFreeDeferredIoWorkItem</a> to free the work item. </p>

<p>A minifilter driver can use <b>FltQueueDeferredIoWorkItem</b> in a post-operation callback (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>) routine as follows: </p>

<p>The post-operation callback calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff541720">FltAllocateDeferredIoWorkItem</a> to allocate the work item. </p>

<p>The post-operation callback calls <b>FltQueueDeferredIoWorkItem</b> to post the operation to the work queue. </p>

<p>The post-operation callback returns FLT_POSTOP_MORE_PROCESSING_REQUIRED. </p>

<p>After processing the I/O operation, the work routine calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff541897">FltCompletePendedPostOperation</a> to return the I/O operation to the Filter Manager. </p>

<p>The work routine calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff542955">FltFreeDeferredIoWorkItem</a> to free the work item. </p>

<p>IRP_MJ_READ</p>

<p>IRP_MJ_WRITE</p>

<p>IRP_MJ_FLUSH_BUFFERS</p>

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
<p>This routine is available in Microsoft Windows 2000 and later versions of all Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Fltmgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541720">FltAllocateDeferredIoWorkItem</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541897">FltCompletePendedPostOperation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541913">FltCompletePendedPreOperation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542955">FltFreeDeferredIoWorkItem</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548405">IoGetTopLevelIrp</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltQueueDeferredIoWorkItem routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>