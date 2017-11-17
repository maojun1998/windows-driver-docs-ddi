---
UID: NF.ntifs.IoUnregisterFsRegistrationChange
title: IoUnregisterFsRegistrationChange
author: windows-driver-content
description: The IoUnregisterFsRegistrationChange routine unregisters file system filter driver's file system registration change notification routine.
old-location: ifsk\iounregisterfsregistrationchange.htm
ms.assetid: 4e10afc0-b9c4-4495-83a1-11f9b82143fc
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
req.alt-api: IoUnregisterFsRegistrationChange
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
req.irql: < DISPATCH_LEVEL
ms.keywords: IoUnregisterFsRegistrationChange
req.iface: 
---

# IoUnregisterFsRegistrationChange function



## -description
<p>The <b>IoUnregisterFsRegistrationChange</b> routine unregisters file system filter driver's file system registration change notification routine.</p>


## -syntax

````
VOID IoUnregisterFsRegistrationChange(
  _In_ PDRIVER_OBJECT          DriverObject,
  _In_ PDRIVER_FS_NOTIFICATION DriverNotificationRoutine
);
````


## -parameters
<dl>

### -param <i>DriverObject</i> [in]

<dd>
<p>Pointer to the driver object for the filter driver.</p>
</dd>

### -param <i>DriverNotificationRoutine</i> [in]

<dd>
<p>A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551037">PDRIVER_FS_NOTIFICATION</a> routine, which the file system calls when it registers or unregisters itself.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p><b>IoUnregisterFsRegistrationChange</b> unregisters a file system filter driver's notification routine so that it is no longer called whenever a file system calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff548494">IoRegisterFileSystem</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548552">IoUnregisterFileSystem</a>. <b>IoUnregisterFsRegistrationChange</b> also decrements the reference count on the filter driver's driver object.</p>

<p><b>IoUnregisterFsRegistrationChange</b> unregisters a file system filter driver's notification routine so that it is no longer called whenever a file system calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff548494">IoRegisterFileSystem</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548552">IoUnregisterFileSystem</a>. <b>IoUnregisterFsRegistrationChange</b> also decrements the reference count on the filter driver's driver object.</p>

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
<p>&lt; DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548494">IoRegisterFileSystem</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548499">IoRegisterFsRegistrationChange</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548552">IoUnregisterFileSystem</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoUnregisterFsRegistrationChange routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>