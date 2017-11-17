---
UID: NF.ntifs.SeMarkLogonSessionForTerminationNotification
title: SeMarkLogonSessionForTerminationNotification
author: windows-driver-content
description: The SeMarkLogonSessionForTerminationNotification routine marks a logon session so that the caller's registered callback routine is called when the logon session terminates.
old-location: ifsk\semarklogonsessionforterminationnotification.htm
ms.assetid: ca259e03-4770-48ce-a4c0-a26159a172aa
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
req.alt-api: SeMarkLogonSessionForTerminationNotification
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
ms.keywords: SeMarkLogonSessionForTerminationNotification
req.iface: 
---

# SeMarkLogonSessionForTerminationNotification function



## -description
<p>The <b>SeMarkLogonSessionForTerminationNotification</b> routine marks a logon session so that the caller's registered callback routine is called when the logon session terminates. A logon session terminates when the last token referencing the logon session is deleted.</p>


## -syntax

````
NTSTATUS SeMarkLogonSessionForTerminationNotification(
  _In_ PLUID LogonId
);
````


## -parameters
<dl>

### -param <i>LogonId</i> [in]

<dd>
<p>Pointer to the logon ID of the logon session.</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The logon session was successfully marked.</p><dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl><p>The logon session was not found.</p>

<p> </p>

## -remarks
<p>To register the callback routine, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff556702">SeRegisterLogonSessionTerminatedRoutine</a>.</p>

<p>For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.</p>

<p>To register the callback routine, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff556702">SeRegisterLogonSessionTerminatedRoutine</a>.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556702">SeRegisterLogonSessionTerminatedRoutine</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556738">SeUnregisterLogonSessionTerminatedRoutine</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeMarkLogonSessionForTerminationNotification routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>