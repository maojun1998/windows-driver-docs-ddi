---
UID: NF.ntifs.RtlGetSaclSecurityDescriptor
title: RtlGetSaclSecurityDescriptor
author: windows-driver-content
description: The RtlGetSaclSecurityDescriptor routine returns a pointer to the system ACL (SACL) for a security descriptor.
old-location: ifsk\rtlgetsaclsecuritydescriptor.htm
ms.assetid: 5dd4b15a-63e1-4b80-a156-bc44aeeafb0e
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows Server 2003 SP1 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlGetSaclSecurityDescriptor
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
req.irql: <= APC_LEVEL
ms.keywords: RtlGetSaclSecurityDescriptor
req.iface: 
---

# RtlGetSaclSecurityDescriptor function



## -description
<p>The <b>RtlGetSaclSecurityDescriptor</b> routine returns a pointer to the system ACL (SACL) for a security descriptor.</p>


## -syntax

````
NTSTATUS RtlGetSaclSecurityDescriptor(
  _In_  PSECURITY_DESCRIPTOR SecurityDescriptor,
  _Out_ PBOOLEAN             SaclPresent,
  _Out_ PACL                 *Sacl,
  _Out_ PBOOLEAN             SaclDefaulted
);
````


## -parameters
<dl>

### -param <i>SecurityDescriptor</i> [in]

<dd>
<p>Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a> whose SACL is to be returned.</p>
</dd>

### -param <i>SaclPresent</i> [out]

<dd>
<p>Pointer to a Boolean variable that indicates the presence of a SACL in the specified security descriptor. If this variable receives <b>TRUE</b>, the security descriptor contains a SACL, and the remaining output parameters receive valid values. If this variable receives <b>FALSE</b>, the security descriptor does not contain a SACL, and the remaining output parameters do not receive valid values.</p>
</dd>

### -param <i>Sacl</i> [out]

<dd>
<p>Pointer to a variable that receives the address of the SACL for the security descriptor. If the security descriptor does not have a SACL, this variable does not receive a value. If the security descriptor has a <b>NULL</b> SACL, this variable receives <b>NULL</b>. </p>
</dd>

### -param <i>SaclDefaulted</i> [out]

<dd>
<p>Pointer to a Boolean variable that receives the value of the SE_SACL_DEFAULTED flag in the security descriptor's SECURITY_DESCRIPTOR_CONTROL structure if a SACL exists for the security descriptor. </p>
</dd>
</dl>

## -returns
<p><b>RtlGetSaclSecurityDescriptor</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following:</p><dl>
<dt><b>STATUS_UNKNOWN_REVISION</b></dt>
</dl><p>The security descriptor's revision level is unknown or is not supported. This is an error code.</p>

<p> </p>

## -remarks
<p>For more information about security and access control, see the documentation for these topics in the Microsoft Windows SDK. </p>

<p>For more information about security and access control, see the documentation for these topics in the Microsoft Windows SDK. </p>

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
<p>This routine is available on Microsoft Windows Server 2003 SP1 and later.</p>
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
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561827">RtlCreateSecurityDescriptor</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552292">RtlGetDaclSecurityDescriptor</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562025">RtlLengthSecurityDescriptor</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562781">RtlSetDaclSecurityDescriptor</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563024">RtlValidSecurityDescriptor</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlGetSaclSecurityDescriptor routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>