---
UID: NF.ntddk.PsAttachSiloToCurrentThread
title: PsAttachSiloToCurrentThread
author: windows-driver-content
description: This routine places a thread temporarily into the specified Silo.
old-location: kernel\psattachsilotocurrentthread.htm
ms.assetid: 1C66E50F-3BD7-4038-9FDF-2F2B712D9B5E
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PsAttachSiloToCurrentThread
req.alt-loc: ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
ms.keywords: PsAttachSiloToCurrentThread
req.iface: 
---

# PsAttachSiloToCurrentThread function



## -description
<p>This routine places a thread temporarily into the specified <i>Silo</i>.</p>


## -syntax

````
PESILO PsAttachSiloToCurrentThread(
  _In_ PESILO Silo
);
````


## -parameters
<dl>

### -param <i>Silo</i> [in]

<dd>
<p>The silo that the thread is to impersonate. The caller must hold a  reference to the silo throughout the duration of the impersonation.</p>
</dd>
</dl>

## -returns
<p>The previous silo that was attached to the current thread.</p>

## -remarks
<p>The specified <i>Silo</i> is attached to the current thread so that it becomes the effective silo for the thread.

The thread then operates within the namespace of the attached silo until <a href="https://msdn.microsoft.com/library/windows/hardware/mt735060">PsDetachSiloFromCurrentThread</a> is called.</p>

<p>The specified <i>Silo</i> is attached to the current thread so that it becomes the effective silo for the thread.

The thread then operates within the namespace of the attached silo until <a href="https://msdn.microsoft.com/library/windows/hardware/mt735060">PsDetachSiloFromCurrentThread</a> is called.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10, version 1607</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt735060">PsDetachSiloFromCurrentThread</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsAttachSiloToCurrentThread routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>