---
UID: NF.ntifs.SecLookupAccountName
title: SecLookupAccountName
author: windows-driver-content
description: SecLookupAccountName accepts an account as input and retrieves a security identifier (SID) for the account and the name of the domain on which the account was found.
old-location: ifsk\seclookupaccountname.htm
ms.assetid: 5b1c3cc4-6185-4299-86ed-662a2b445042
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The SecLookupAccountName function is only available on Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SecLookupAccountName
req.alt-loc: Ksecdd.lib,Ksecdd.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ksecdd.lib
req.dll: 
req.irql: <= APC_LEVEL
ms.keywords: SecLookupAccountName
req.iface: 
---

# SecLookupAccountName function



## -description
<p><b>SecLookupAccountName</b> accepts an account as input and retrieves a security identifier (SID) for the account and the name of the domain on which the account was found.</p>


## -syntax

````
NTSTATUS SecLookupAccountName(
  _In_    PUNICODE_STRING Name,
  _Inout_ PULONG          SidSize,
  _Out_   PSID            Sid,
  _Out_   PSID_NAME_USE   NameUse,
  _Out_   PULONG          DomainSize,
  _Inout_ PUNICODE_STRING ReferencedDomain
);
````


## -parameters
<dl>

### -param <i>Name</i> [in]

<dd>
<p>A pointer to a Unicode string that specifies the account name. Use a fully qualified string in the domain_name\user_name format to ensure that <b>SecLookupAccountName</b> finds the account in the desired domain. </p>
</dd>

### -param <i>SidSize</i> [in, out]

<dd>
<p>A pointer to a variable that specifies the size of the <i>Sid</i> buffer. On input, this value specifies the size in bytes of the input <i>Sid</i> buffer. If the function fails because the buffer is too small or if <i>SidSize</i> is zero, this variable receives the required buffer size. On success, this variable contains the size of the returned <i>Sid</i>.</p>
</dd>

### -param <i>Sid</i> [out]

<dd>
<p>A pointer to a buffer that receives the SID structure that corresponds to the account name pointed to by the <i>Name</i> parameter. If this parameter is <b>NULL</b>, <i>SidSize</i> must be zero. </p>
</dd>

### -param <i>NameUse</i> [out]

<dd>
<p>A pointer to a SID_NAME_USE enumerated type that indicates the type of the account when the function returns. </p>
</dd>

### -param <i>DomainSize</i> [out]

<dd>
<p>A pointer to an optional variable that specifies the size of the <i>ReferencedDomain</i> parameter. On input, this value specifies the size of the <i>ReferencedDomain</i> buffer. If the function fails because the buffer is too small, this variable receives the required buffer size. If the <i>ReferencedDomain</i> parameter is <b>NULL</b>, this parameter must be zero.</p>
</dd>

### -param <i>ReferencedDomain</i> [in, out]

<dd>
<p>A pointer to a buffer that receives the name of the domain as a Unicode string where the account name is found. For computers that are not joined to a domain, this buffer receives the computer name. If this parameter is <b>NULL</b>, the function returns the required buffer size in the <i>DomainSize</i> variable. </p>
</dd>
</dl>

## -returns
<p><b>SecLookupAccountName</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: </p><dl>
<dt><b>SEC_E_INTERNAL_ERROR</b></dt>
</dl><p>An internal error occurred while trying to connect to the Local System Authority (LSA) or the local procedure call (LPC) to the security provider failed. </p><dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl><p>The process ID associated with the currently executing thread does not match the current process ID. </p><dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl><p>The buffer size for the <i>Sid</i> or the <i>ReferencedDomain</i> parameter was too small.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>The length of the <i>Name</i> parameter exceeded the length allowed in a message to the Local System Authority. </p><dl>
<dt><b>STATUS_NONE_MAPPED</b></dt>
</dl><p>The <i>Name</i> parameter could not be found. </p><dl>
<dt><b>STATUS_PROCESS_IS_TERMINATING</b></dt>
</dl><p>This process has terminated so it is not possible to establish the local procedure call (LPC) connection.</p>

<p> </p>

## -remarks
<p><b>SecLookupAccountName</b> attempts to find a SID for the specified name. The function checks built-in and administratively defined local accounts. Next, the function checks the primary domain. If the name is not found there, trusted domains are checked.</p>

<p>Use fully qualified account names (for example, domain_name\user_name) instead of isolated names (for example, user_name). Fully qualified names are unambiguous and provide better performance when the lookup is performed. This function also supports fully qualified DNS names (for example, example.example.com\user_name) and user principal names (UPN) (for example, someone@example.com).</p>

<p>In addition to looking up local accounts, local domain accounts, and explicitly trusted domain accounts, <b>SecLookupAccountName</b> can look up the name for any account in any domain in the forest.</p>

<p><b>SecLookupAccountName</b> is equivalent to the Win32 <b>LookupAccountName</b> function. </p>

<p><b>SecLookupAccountName</b> is exported by the ksecdd driver, which implements this function by using user-mode helper services. Accordingly, the use of this function within file systems must obey the usual rules for communication with user-mode services. <b>SecLookupAccountName</b> cannot be used during paging file I/O. </p>

<p><b>SecLookupAccountName</b> attempts to find a SID for the specified name. The function checks built-in and administratively defined local accounts. Next, the function checks the primary domain. If the name is not found there, trusted domains are checked.</p>

<p>Use fully qualified account names (for example, domain_name\user_name) instead of isolated names (for example, user_name). Fully qualified names are unambiguous and provide better performance when the lookup is performed. This function also supports fully qualified DNS names (for example, example.example.com\user_name) and user principal names (UPN) (for example, someone@example.com).</p>

<p>In addition to looking up local accounts, local domain accounts, and explicitly trusted domain accounts, <b>SecLookupAccountName</b> can look up the name for any account in any domain in the forest.</p>

<p><b>SecLookupAccountName</b> is equivalent to the Win32 <b>LookupAccountName</b> function. </p>

<p><b>SecLookupAccountName</b> is exported by the ksecdd driver, which implements this function by using user-mode helper services. Accordingly, the use of this function within file systems must obey the usual rules for communication with user-mode services. <b>SecLookupAccountName</b> cannot be used during paging file I/O. </p>

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
<p>The SecLookupAccountName function is only available on Windows XP and later.</p>
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
<dt>Ksecdd.lib</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556579">SecLookupAccountSid</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556582">SecLookupWellKnownSid</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556744">SID_NAME_USE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SecLookupAccountName function%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>