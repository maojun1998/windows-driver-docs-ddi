---
UID: NF.rxprocs.RxPrepareToReparseSymbolicLink
title: RxPrepareToReparseSymbolicLink
author: windows-driver-content
description: RxPrepareToReparseSymbolicLink sets up the file object name to facilitate a reparse. This routine is used by the network mini-redirectors to traverse symbolic links.
old-location: ifsk\rxpreparetoreparsesymboliclink.htm
ms.assetid: 6a05b25f-e529-469a-8bfc-e75c0f7a9a8a
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: rxprocs.h
req.include-header: Rxprocs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxPrepareToReparseSymbolicLink
req.alt-loc: rxprocs.h
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
ms.keywords: RxPrepareToReparseSymbolicLink
req.iface: 
req.product: Windows 10 or later.
---

# RxPrepareToReparseSymbolicLink function



## -description
<p><b>RxPrepareToReparseSymbolicLink</b> sets up the file object name to facilitate a reparse. This routine is used by the network mini-redirectors to traverse symbolic links. </p>


## -syntax

````
NTSTATUS RxPrepareToReparseSymbolicLink(
   PRX_CONTEXT     RxContext,
   BOOLEAN         SymbolicLinkEmbeddedInOldPath,
   PUNICODE_STRING NewPath,
   BOOLEAN         NewPathIsAbsolute,
   PBOOLEAN        ReparseRequired
);
````


## -parameters
<dl>

### -param <i>RxContext</i> 

<dd>
<p>A pointer to the RX_CONTEXT structure.</p>
</dd>

### -param <i>SymbolicLinkEmbeddedInOldPath</i> 

<dd>
<p>A Boolean value that indicates that a symbolic link was encountered. If the value is <b>TRUE</b>, a symbolic link was encountered as part of the traversal of the old path.</p>
</dd>

### -param <i>NewPath</i> 

<dd>
<p>A pointer to a Unicode string that contains the new path name to be traversed.</p>
</dd>

### -param <i>NewPathIsAbsolute</i> 

<dd>
<p>A Boolean value that indicates if the new path is absolute. If this value is <b>FALSE</b>, \Device\Mup should be prepended to <i>NewPath</i>. If this value is <b>TRUE</b>, the <i>NewPath</i> parameter is the full path to reparse. In this case, the buffer that contains <i>NewPath</i> is used directly, rather than allocating a new buffer.</p>
</dd>

### -param <i>ReparseRequired</i> 

<dd>
<p>A pointer to a Boolean value that indicates whether a reparse is required. If this value is <b>TRUE</b>, a reparse is required.</p>
</dd>
</dl>

## -returns
<p><b>RxPrepareToReparseSymbolicLink</b> returns STATUS_SUCCESS on success or one of the following error values on failure: </p><dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl><p>A request to delete failed.</p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>There were insufficient resources available.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>An invalid parameter was passed to the routine. This error will be returned if the <b>MajorFunction</b> member of <i>RxContext </i>is not IRP_MJ_CREATE. </p>

<p> </p>

## -remarks
<p>The <b>RxPrepareToReparseSymbolicLink</b> routine would only be used by a network mini-redirector that supports symbolic links and uses reparse points to implement symbolic links. The <b>RxPrepareToReparseSymbolicLink</b> routine would normally be called by a network mini-redirector from its <b>MrxCreate</b> callback routine.</p>

<p>The <i>SymbolicLinkEmbeddedInOldPath</i> parameter passed to this routine is very important. To preserve the correct semantics, it should be carefully used. For example, consider the old path \A\B\C\D where C happens to be a symbolic link. In this case, the symbolic link is embedded in the path and <i>SymbolicLinkEmbeddedInOldPath</i> should be set to <b>TRUE</b>. In contrast, this is very different from the case when D happens to be a symbolic link. In the former case, the reparse constitutes an intermediate step. In the second example, the reparse constitutes the final step of the name resolution and <i>SymbolicLinkEmbeddedInOldPath</i> should be set to <b>FALSE</b>.</p>

<p>If DELETE access is specified, the open or create operation is denied for all cases in which the symbolic link is not embedded. It is possible that if DELETE access were the only one specified, then the open attempt must succeed without reparse. This conforms UNIX symbolic link semantics.</p>

<p>As part of this routine, <i>RxContext</i> is also tagged appropriately. This ensures that the return value can be crosschecked with the invocation of this routine. Once <b>RxPrepareToReparseSymbolicLink</b> is invoked, the network mini redirector has to return STATUS_REPARSE.</p>

<p>The value of the <i>ReparseRequired</i> parameter assumes significance only if STATUS_SUCCESS is returned from this routine. If <i>ReparseRequired</i> is <b>FALSE</b>, this implies that no reparse attempt is required and the symbolic link file itself should be manipulated as opposed to the target of the link. If <i>ReparseRequired</i> is <b>TRUE</b>, this implies that a reparse attempt was successfully setup. In such cases, it is imperative that the network mini redirector returns STATUS_REPARSE for the associated <b>MRxCreate</b> call. RDBSS will initiate a check for this condition. </p>

<p>The <b>RxPrepareToReparseSymbolicLink</b> routine would only be used by a network mini-redirector that supports symbolic links and uses reparse points to implement symbolic links. The <b>RxPrepareToReparseSymbolicLink</b> routine would normally be called by a network mini-redirector from its <b>MrxCreate</b> callback routine.</p>

<p>The <i>SymbolicLinkEmbeddedInOldPath</i> parameter passed to this routine is very important. To preserve the correct semantics, it should be carefully used. For example, consider the old path \A\B\C\D where C happens to be a symbolic link. In this case, the symbolic link is embedded in the path and <i>SymbolicLinkEmbeddedInOldPath</i> should be set to <b>TRUE</b>. In contrast, this is very different from the case when D happens to be a symbolic link. In the former case, the reparse constitutes an intermediate step. In the second example, the reparse constitutes the final step of the name resolution and <i>SymbolicLinkEmbeddedInOldPath</i> should be set to <b>FALSE</b>.</p>

<p>If DELETE access is specified, the open or create operation is denied for all cases in which the symbolic link is not embedded. It is possible that if DELETE access were the only one specified, then the open attempt must succeed without reparse. This conforms UNIX symbolic link semantics.</p>

<p>As part of this routine, <i>RxContext</i> is also tagged appropriately. This ensures that the return value can be crosschecked with the invocation of this routine. Once <b>RxPrepareToReparseSymbolicLink</b> is invoked, the network mini redirector has to return STATUS_REPARSE.</p>

<p>The value of the <i>ReparseRequired</i> parameter assumes significance only if STATUS_SUCCESS is returned from this routine. If <i>ReparseRequired</i> is <b>FALSE</b>, this implies that no reparse attempt is required and the symbolic link file itself should be manipulated as opposed to the target of the link. If <i>ReparseRequired</i> is <b>TRUE</b>, this implies that a reparse attempt was successfully setup. In such cases, it is imperative that the network mini redirector returns STATUS_REPARSE for the associated <b>MRxCreate</b> call. RDBSS will initiate a check for this condition. </p>

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
<dt>Rxprocs.h (include Rxprocs.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxPrepareToReparseSymbolicLink routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>