---
UID: NF.wdbgexts.ReadPhysical
title: ReadPhysical
author: windows-driver-content
description: The ReadPhysical function reads from physical memory.
old-location: debugger\readphysical.htm
ms.assetid: 02ca3358-7740-4eda-ab7c-f4b8a88389c2
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
req.alt-api: ReadPhysical
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
ms.keywords: ReadPhysical
req.iface: 
req.product: Windows 10 or later.
---

# ReadPhysical function



## -description
<p>The <b>ReadPhysical</b> function reads from physical memory.</p>


## -syntax

````
__inline VOID ReadPhysical(
   ULONG64 address,
   PVOID   buf,
   ULONG   size,
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