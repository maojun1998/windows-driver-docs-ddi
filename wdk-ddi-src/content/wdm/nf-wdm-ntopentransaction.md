---
UID: NF.wdm.NtOpenTransaction
title: NtOpenTransaction function
author: windows-driver-content
description: The ZwOpenTransaction routine obtains a handle to an existing transaction object.
old-location: kernel\zwopentransaction.htm
old-project: kernel
ms.assetid: 5ffa50af-24e6-4dab-81cc-6ac26356e9c6
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: NtOpenTransaction
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwOpenTransaction,NtOpenTransaction
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
req.product: Windows 10 or later.
---

# NtOpenTransaction function



## -description
The <b>ZwOpenTransaction</b> routine obtains a handle to an existing <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>.



## -syntax

````
NTSTATUS ZwOpenTransaction(
  _Out_    PHANDLE            TransactionHandle,
  _In_     ACCESS_MASK        DesiredAccess,
  _In_opt_ POBJECT_ATTRIBUTES ObjectAttributes,
  _In_     LPGUID             Uow,
  _In_opt_ HANDLE             TmHandle
);
````


## -parameters

### -param TransactionHandle [out]

A pointer to a caller-allocated variable that receives a handle to the transaction object if <b>ZwOpenTransaction</b> returns STATUS_SUCCESS.


### -param DesiredAccess [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that specifies the caller's requested access to the transaction object. For information about how to specify this parameter, see the <i>DesiredAccess</i> parameter of <a href="kernel.zwcreatetransaction">ZwCreateTransaction</a>. 


### -param ObjectAttributes [in, optional]

A pointer to an <a href="kernel.object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies the object's attributes. Use the <a href="kernel.initializeobjectattributes">InitializeObjectAttributes</a> routine to initialize this structure, but specify only that routine's <i>InitializedAttributes</i> and <i>Attributes</i> parameters. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE flag in the <i>Attributes</i> parameter. The <i>ObjectAttributes</i> parameter is optional and can be <b>NULL</b>. 


### -param Uow [in]

A pointer to a GUID that is a transaction object's <a href="https://msdn.microsoft.com/927a417b-35f5-49b8-85f3-7e6b1f5c0225">unit of work (UOW) identifier</a>. This GUID identifies the transaction object to open. 


### -param TmHandle [in, optional]

A handle to a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a>. If this parameter is not <b>NULL</b>, KTM searches only for transaction objects that belong to the specified transaction manager object. If this parameter is <b>NULL</b>, KTM searches all transaction objects.


## -returns
<b>ZwCreateTransaction</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>DesiredAccess</i> or <i>Uow</i> parameter was zero.
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>The specified handle is not a handle to a transaction object.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>An object handle is invalid.
<dl>
<dt><b>STATUS_TRANSACTION_NOT_FOUND</b></dt>
</dl>KTM could not find the transaction object.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The value of the <i>DesiredAccess</i> parameter is invalid.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
Typically, a resource manager calls <b>ZwOpenTransaction</b> after it receives a transaction UOW from a transactional client that had previously called <a href="kernel.zwcreatetransaction">ZwCreateTransaction</a>. 

For more information about <b>ZwOpenTransaction</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542865">Creating a Resource Manager</a>.

<b>NtOpenTransaction</b> and <b>ZwOpenTransaction</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.


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
Available in Windows Vista and later operating system versions.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
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
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="kernel.initializeobjectattributes">InitializeObjectAttributes</a>
</dt>
<dt>
<a href="kernel.object_attributes">OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="kernel.zwcommittransaction">ZwCommitTransaction</a>
</dt>
<dt>
<a href="kernel.zwcreatetransaction">ZwCreateTransaction</a>
</dt>
<dt>
<a href="kernel.zwqueryinformationtransaction">ZwQueryInformationTransaction</a>
</dt>
<dt>
<a href="kernel.zwrollbacktransaction">ZwRollbackTransaction</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwOpenTransaction routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
