---
UID: NF.wdm.PopEntryList
title: PopEntryList
author: windows-driver-content
description: The PopEntryList routine removes the first entry from a singly linked list of SINGLE_LIST_ENTRY structures.
old-location: kernel\popentrylist.htm
ms.assetid: b24ec573-4164-4016-a19d-574ebd75ec8f
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PopEntryList
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level (see Remarks section)
ms.keywords: PopEntryList
req.iface: 
req.product: Windows 10 or later.
---

# PopEntryList function



## -description
<p>The <b>PopEntryList</b> routine removes the first entry from a singly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563799">SINGLE_LIST_ENTRY</a> structures.</p>


## -syntax

````
PSINGLE_LIST_ENTRY PopEntryList(
  _Inout_ PSINGLE_LIST_ENTRY ListHead
);
````


## -parameters
<dl>

### -param <i>ListHead</i> [in, out]

<dd>
<p>Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563799">SINGLE_LIST_ENTRY</a> structure that represents the head of the list. On return, <i>ListHead</i>-&gt;<b>Next</b> points to the beginning of the list with the first entry removed. </p>
</dd>
</dl>

## -returns
<p><b>PopEntryList</b> returns a pointer to the entry removed from the list, or <b>NULL</b> if the list is currently empty.</p>

## -remarks
<p><b>PopEntryList</b> removes the first entry from the list by setting <i>ListHead</i>-&gt;<b>Next</b> to point to the second entry in the list.</p>

<p>For information about using this routine when implementing a singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.</p>

<p>Callers of <b>PopEntryList</b> can be running at any IRQL. If <b>PopEntryList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for <i>ListHead</i> and the list entries must be resident.</p>

<p><b>PopEntryList</b> removes the first entry from the list by setting <i>ListHead</i>-&gt;<b>Next</b> to point to the second entry in the list.</p>

<p>For information about using this routine when implementing a singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.</p>

<p>Callers of <b>PopEntryList</b> can be running at any IRQL. If <b>PopEntryList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for <i>ListHead</i> and the list entries must be resident.</p>

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
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level (see Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545408">ExInterlockedPopEntryList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559964">PushEntryList</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PopEntryList routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>