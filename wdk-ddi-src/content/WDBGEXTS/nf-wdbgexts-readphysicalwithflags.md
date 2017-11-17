---
UID: NF.wdbgexts.ReadPhysicalWithFlags
title: ReadPhysicalWithFlags
author: windows-driver-content
description: The ReadPhysicalWithFlags function reads from physical memory.
old-location: debugger\readphysicalwithflags.htm
ms.assetid: 7ff5787f-f663-4ceb-be59-4f48ecea03a9
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: debugger
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ReadPhysicalWithFlags
req.alt-loc: wdbgexts.h
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
ms.keywords: ReadPhysicalWithFlags
req.iface: 
req.product: Windows 10 or later.
---

# ReadPhysicalWithFlags function



## -description
<p>The <b>ReadPhysicalWithFlags</b> function reads from physical memory.</p>


## -syntax

````
__inline VOID ReadPhysicalWithFlags(
   ULONG64 address,
   PVOID   buf,
   ULONG   size,
   ULONG   flags,
   PULONG  sizer
);
````


## -parameters
<dl>

### -param <i>address</i> 

<dd>
<p>Specifies the physical address to read.</p>
</dd>

### -param <i>buf</i> 

<dd>
<p>Specifies the address of an array of bytes to hold the data that is read.</p>
</dd>

### -param <i>size</i> 

<dd>
<p>Specifies the number of bytes to read. </p>
</dd>

### -param <i>flags</i> 

<dd>
<p>Specifies the properties of the physical memory to be read.  This must match the way the physical memory was advertised to the operating system on the target.  Possible values are listed in the following table.</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
<p>PHYS_FLAG_DEFAULT</p>
</td>
<td>
<p>Use the default memory caching.</p>
</td>
</tr>
<tr>
<td>
<p>PHYS_FLAG_CACHED</p>
</td>
<td>
<p>The physical memory is cached.</p>
</td>
</tr>
<tr>
<td>
<p>PHYS_FLAG_UNCACHED</p>
</td>
<td>
<p>The physical memory is uncached.</p>
</td>
</tr>
<tr>
<td>
<p>PHYS_FLAG_WRITE_COMBINED</p>
</td>
<td>
<p>The physical memory is write-combined.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param <i>sizer</i> 

<dd>
<p>Receives the number of bytes actually read.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).
</p>

<p>If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).
</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdbgexts.h (include Wdbgexts.h, Wdbgexts.h, or Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554313">ReadPhysical</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561448">WritePhysicalWithFlags</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ReadPhysicalWithFlags function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>