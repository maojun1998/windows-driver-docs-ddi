---
UID: NF.ntifs.ZwDuplicateObject
title: ZwDuplicateObject
author: windows-driver-content
description: The ZwDuplicateObject routine creates a handle that is a duplicate of the specified source handle.
old-location: kernel\zwduplicateobject.htm
ms.assetid: 9a922379-b439-4f94-9eb1-7c229318382c
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: ntifs.h
req.include-header: Ntdef.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwDuplicateObject,NtDuplicateObject
req.alt-loc: ntoskrnl.lib,ntoskrnl.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: ZwDuplicateObject
req.iface: 
---

# ZwDuplicateObject function



## -description
<p>The <b>ZwDuplicateObject</b> routine creates a handle that is a duplicate of the specified source handle.</p>


## -syntax

````
NTSTATUS ZwDuplicateObject(
  _In_      HANDLE      SourceProcessHandle,
  _In_      HANDLE      SourceHandle,
  _In_opt_  HANDLE      TargetProcessHandle,
  _Out_opt_ PHANDLE     TargetHandle,
  _In_      ACCESS_MASK DesiredAccess,
  _In_      ULONG       HandleAttributes,
  _In_      ULONG       Options
);
````


## -parameters
<dl>

### -param <i>SourceProcessHandle</i> [in]

<dd>
<p>A handle to the source process for the handle being duplicated.</p>
</dd>

### -param <i>SourceHandle</i> [in]

<dd>
<p>The handle to duplicate.</p>
</dd>

### -param <i>TargetProcessHandle</i> [in, optional]

<dd>
<p>A handle to the target process that is to receive the new handle. This parameter is optional and can be specified as NULL if the <b>DUPLICATE_CLOSE_SOURCE</b> flag is set in <i>Options</i>.</p>
</dd>

### -param <i>TargetHandle</i> [out, optional]

<dd>
<p>A pointer to a HANDLE variable into which the routine writes the new duplicated handle. The duplicated handle is valid in the specified target process. This parameter is optional and can be specified as NULL if no duplicate handle is to be created.</p>
</dd>

### -param <i>DesiredAccess</i> [in]

<dd>
<p>An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that specifies the desired access for the new handle.</p>
</dd>

### -param <i>HandleAttributes</i> [in]

<dd>
<p>A ULONG that specifies the desired attributes for the new handle. For more information about attributes, see the description of the <b>Attributes</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a>.</p>
</dd>

### -param <i>Options</i> [in]

<dd>
<p>A set of flags to control the behavior of the duplication operation. Set this parameter to zero or to the bitwise OR of one or more of the following flags.</p>
<table>
<tr>
<th>Flag name</th>
<th>Description</th>
</tr>
<tr>
<td><b>DUPLICATE_SAME_ATTRIBUTES</b></td>
<td>Instead of using the <i>HandleAttributes</i> parameter, copy the attributes from the source handle to the target handle.</td>
</tr>
<tr>
<td><b>DUPLICATE_SAME_ACCESS</b></td>
<td>Instead of using the <i>DesiredAccess</i> parameter, copy the access rights from the source handle to the target handle.</td>
</tr>
<tr>
<td><b>DUPLICATE_CLOSE_SOURCE</b></td>
<td>Close the source handle.</td>
</tr>
</table>
<p> </p>
</dd>
</dl>

## -returns
<p><b>ZwDuplicateObject</b> returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.</p>

## -remarks
<p>The source handle is evaluated in the context of the specified source process. The calling process must have <b>PROCESS_DUP_HANDLE</b> access to the source process. The duplicate handle is created in the handle table of the specified target process. The calling process must have <b>PROCESS_DUP_HANDLE</b> access to the target process.</p>

<p>By default, the duplicate handle is created with the attributes specified by the <i>HandleAttributes</i> parameter, and with the access rights specified by the <i>DesiredAccess</i> parameter. If necessary, the caller can override one or both defaults by setting the <b>DUPLICATE_SAME_ATTRIBUTES</b> and <b>DUPLICATE_SAME_ACCESS</b> flags in the <i>Options</i> parameter.</p>

<p>If the call to this function occurs in user mode, you should use the name "<b>NtDuplicateObject</b>" instead of "<b>ZwDuplicateObject</b>".</p>

<p>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.</p>

<p>The source handle is evaluated in the context of the specified source process. The calling process must have <b>PROCESS_DUP_HANDLE</b> access to the source process. The duplicate handle is created in the handle table of the specified target process. The calling process must have <b>PROCESS_DUP_HANDLE</b> access to the target process.</p>

<p>By default, the duplicate handle is created with the attributes specified by the <i>HandleAttributes</i> parameter, and with the access rights specified by the <i>DesiredAccess</i> parameter. If necessary, the caller can override one or both defaults by setting the <b>DUPLICATE_SAME_ATTRIBUTES</b> and <b>DUPLICATE_SAME_ACCESS</b> flags in the <i>Options</i> parameter.</p>

<p>If the call to this function occurs in user mode, you should use the name "<b>NtDuplicateObject</b>" instead of "<b>ZwDuplicateObject</b>".</p>

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
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntdef.h, Ntifs.h, or Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.lib</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwDuplicateObject routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>