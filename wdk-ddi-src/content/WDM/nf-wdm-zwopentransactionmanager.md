---
UID: NF.wdm.ZwOpenTransactionManager
title: ZwOpenTransactionManager
author: windows-driver-content
description: The ZwOpenTransactionManager routine obtains a handle to an existing transaction manager object.
old-location: kernel\zwopentransactionmanager.htm
ms.assetid: b3eb40ad-cda9-4a2f-a794-670bd2ee9102
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwOpenTransactionManager,NtOpenTransactionManager
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
ms.keywords: ZwOpenTransactionManager
req.iface: 
req.product: Windows 10 or later.
---

# ZwOpenTransactionManager function



## -description
<p>The <b>ZwOpenTransactionManager</b> routine obtains a handle to an existing transaction manager object.</p>


## -syntax

````
NTSTATUS ZwOpenTransactionManager(
  _Out_    PHANDLE            TmHandle,
  _In_     ACCESS_MASK        DesiredAccess,
  _In_opt_ POBJECT_ATTRIBUTES ObjectAttributes,
  _In_opt_ PUNICODE_STRING    LogFileName,
  _In_opt_ LPGUID             TmIdentity,
  _In_opt_ ULONG              OpenOptions
);
````


## -parameters
<dl>

### -param <i>TmHandle</i> [out]

<dd>
<p>A pointer to a caller-allocated variable that receives a handle to the <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a> if <b>ZwOpenTransactionManager</b> returns STATUS_SUCCESS.</p>
</dd>

### -param <i>DesiredAccess</i> [in]

<dd>
<p>An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that specifies the caller's requested access to the transaction manager object. For information about how to specify this parameter, see the <i>DesiredAccess</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff566430">ZwCreateTransactionManager</a>. </p>
</dd>

### -param <i>ObjectAttributes</i> [in, optional]

<dd>
<p>A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a> routine to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. This parameter is optional and can be <b>NULL</b>. </p>
</dd>

### -param <i>LogFileName</i> [in, optional]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains the path and file name of the <a href="https://msdn.microsoft.com/d7ad0e16-d1f2-4c41-b647-95b5445c2708">log file stream</a> that was created when the transaction manager object was created. For more information, see the <i>LogFileName</i> parameter of <b>ZwCreateTransactionManager</b>. This parameter is optional and can be <b>NULL</b>. </p>
</dd>

### -param <i>TmIdentity</i> [in, optional]

<dd>
<p>A pointer to a GUID that identifies the transaction manager object.  This parameter is optional and can be <b>NULL</b>. </p>
</dd>

### -param <i>OpenOptions</i> [in, optional]

<dd>
<p>This parameter is not used and must be zero.</p>
</dd>
</dl>

## -returns
<p><b>ZwOpenTransactionManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: </p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>The value of an input parameter is invalid.</p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>KTM could not allocate system resources (typically memory).</p><dl>
<dt><b>STATUS_OBJECT_NAME_INVALID</b></dt>
</dl><p>The object name that the <i>ObjectAttributes </i>parameter specifies is invalid.</p><dl>
<dt><b>STATUS_LOG_CORRUPTION_DETECTED</b></dt>
</dl><p>KTM encountered an error while creating or opening the log file.</p><dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl><p>The value of the <i>DesiredAccess</i> parameter is invalid.</p>

<p> </p>

<p>The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.</p>

## -remarks
<p>The caller can identify which transaction manager object to open by using one of the following three techniques:</p>

<p>Use the <i>LogFileName</i> parameter to specify the path and file name of a log file stream that was created when the transaction manager object was created.</p>

<p>Use the <i>TmIdentity</i> parameter to specify the GUID that identifies the transaction manager object. </p>

<p>Use the <i>ObjectAttributes</i> parameter to supply an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure that contains the object name that the caller previously specified to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566430">ZwCreateTransactionManager</a> routine. </p>

<p>You must specify only one of the above-listed parameters (an object name, a log file name, or a GUID) and set the other two parameters to <b>NULL</b>.</p>

<p>Your TPS component must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff567079">ZwRecoverTransactionManager</a> after it has called <b>ZwOpenTransactionManager</b>.</p>

<p>A TPS component that calls <b>ZwOpenTransactionManager</b> must eventually call <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a> to close the object handle.</p>

<p>For more information about how to use <b>ZwOpenTransactionManager</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564802">Transaction Manager Objects</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff542865">Creating a Resource Manager</a>.</p>

<p><b>NtOpenTransactionManager</b> and <b>ZwOpenTransactionManager</b> are two versions of the same Windows Native System Services routine. </p>

<p>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.</p>

<p>The caller can identify which transaction manager object to open by using one of the following three techniques:</p>

<p>Use the <i>LogFileName</i> parameter to specify the path and file name of a log file stream that was created when the transaction manager object was created.</p>

<p>Use the <i>TmIdentity</i> parameter to specify the GUID that identifies the transaction manager object. </p>

<p>Use the <i>ObjectAttributes</i> parameter to supply an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure that contains the object name that the caller previously specified to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566430">ZwCreateTransactionManager</a> routine. </p>

<p>You must specify only one of the above-listed parameters (an object name, a log file name, or a GUID) and set the other two parameters to <b>NULL</b>.</p>

<p>Your TPS component must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff567079">ZwRecoverTransactionManager</a> after it has called <b>ZwOpenTransactionManager</b>.</p>

<p>A TPS component that calls <b>ZwOpenTransactionManager</b> must eventually call <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a> to close the object handle.</p>

<p>For more information about how to use <b>ZwOpenTransactionManager</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564802">Transaction Manager Objects</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff542865">Creating a Resource Manager</a>.</p>

<p><b>NtOpenTransactionManager</b> and <b>ZwOpenTransactionManager</b> are two versions of the same Windows Native System Services routine. </p>

<p>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.</p>

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
<p>Available in Windows Vista and later operating system versions.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h or Ntifs.h)</dt>
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
<p>PASSIVE_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975204">PowerIrpDDis</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566430">ZwCreateTransactionManager</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567058">ZwQueryInformationTransactionManager</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwOpenTransactionManager routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>