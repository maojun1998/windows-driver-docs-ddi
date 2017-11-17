---
UID: NF.ntifs.SePrivilegeCheck
title: SePrivilegeCheck
author: windows-driver-content
description: The SePrivilegeCheck routine determines whether a specified set of privileges is enabled in the subject's access token.
old-location: ifsk\seprivilegecheck.htm
ms.assetid: 707ced39-4153-4a6e-b87d-7e4eb487e738
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SePrivilegeCheck
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
req.irql: PASSIVE_LEVEL
ms.keywords: SePrivilegeCheck
req.iface: 
---

# SePrivilegeCheck function



## -description
<p>The <b>SePrivilegeCheck</b> routine determines whether a specified set of privileges is enabled in the subject's access token. </p>


## -syntax

````
BOOLEAN SePrivilegeCheck(
  _Inout_ PPRIVILEGE_SET            RequiredPrivileges,
  _In_    PSECURITY_SUBJECT_CONTEXT SubjectSecurityContext,
  _In_    KPROCESSOR_MODE           AccessMode
);
````


## -parameters
<dl>

### -param <i>RequiredPrivileges</i> [in, out]

<dd>
<p>Pointer to a PRIVILEGE_SET structure. The <b>Privilege</b> member of this structure is an array of LUID_AND_ATTRIBUTES structures. Before calling <b>SePrivilegeCheck</b>, use the <b>Privilege</b> array to indicate the set of privileges to check. Set the <b>Control</b> member to PRIVILEGE_SET_ALL_NECESSARY if all of the privileges must be enabled; or set it to zero if it is sufficient that any one of the privileges be enabled. </p>
<p>When <b>SePrivilegeCheck</b> returns, the <b>Attributes</b> member of each LUID_AND_ATTRIBUTES structure is set to SE_PRIVILEGE_USED_FOR_ACCESS if the corresponding privilege is enabled. </p>
</dd>

### -param <i>SubjectSecurityContext</i> [in]

<dd>
<p>Pointer to the subject's captured security context.</p>
</dd>

### -param <i>AccessMode</i> [in]

<dd>
<p>The access mode to use for the privilege check. Either <b>UserMode</b> or <b>KernelMode</b>. If <i>AccessMode</i> is set to <b>KernelMode</b>, then all privileges are marked as being possessed by the subject, and <b>SePrivilegeCheck</b> returns <b>TRUE</b>.</p>
</dd>
</dl>

## -returns
<p><b>SePrivilegeCheck</b> returns <b>TRUE</b> if all specified privileges are held by the subject, <b>FALSE</b> otherwise.</p>

## -remarks
<p>An access token contains a list of the privileges held by the account associated with the token. These privileges can be enabled or disabled; most are disabled by default. <b>SePrivilegeCheck</b> checks only for enabled privileges. To get a list of all the enabled and disabled privileges held by an access token, call <b>SeQueryInformationToken</b>. </p>

<p>For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.</p>

<p>An access token contains a list of the privileges held by the account associated with the token. These privileges can be enabled or disabled; most are disabled by default. <b>SePrivilegeCheck</b> checks only for enabled privileges. To get a list of all the enabled and disabled privileges held by an access token, call <b>SeQueryInformationToken</b>. </p>

<p>For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549716">LUID_AND_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551860">PRIVILEGE_SET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563674">SeAccessCheck</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554762">SeAppendPrivileges</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563714">SECURITY_SUBJECT_CONTEXT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556656">SeFreePrivileges</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563740">SeSinglePrivilegeCheck</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SePrivilegeCheck routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>