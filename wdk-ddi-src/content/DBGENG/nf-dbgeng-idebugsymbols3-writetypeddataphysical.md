---
UID: NF.dbgeng.IDebugSymbols3.WriteTypedDataPhysical
title: IDebugSymbols3::WriteTypedDataPhysical
author: windows-driver-content
description: The WriteTypedDataPhysical method writes the value of a variable in the target computer's physical memory.
old-location: debugger\writetypeddataphysical.htm
ms.assetid: 5f29249f-bb62-45d1-aa0e-108db1d7f906
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: debugger
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugSymbols.WriteTypedDataPhysical,IDebugSymbols2.WriteTypedDataPhysical,IDebugSymbols3.WriteTypedDataPhysical
req.alt-loc: dbgeng.h
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
ms.keywords: IDebugSymbols3, WriteTypedDataPhysical, IDebugSymbols3::WriteTypedDataPhysical
req.iface: IDebugSymbols3
---

# IDebugSymbols3::WriteTypedDataPhysical method



## -description
<p>The <b>WriteTypedDataPhysical</b> method writes the value of a variable in the target computer's physical memory.</p>


## -syntax

````
HRESULT WriteTypedDataPhysical(
  [in]            ULONG64 Offset,
  [in]            ULONG64 Module,
  [in]            ULONG   TypeId,
  [in]            PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesWritten
);
````


## -parameters
<dl>

### -param <i>Offset</i> [in]

<dd>
<p>Specifies the physical address in the target computer's memory of the variable.</p>
</dd>

### -param <i>Module</i> [in]

<dd>
<p>Specifies the base address of the module containing the type of the variable.</p>
</dd>

### -param <i>TypeId</i> [in]

<dd>
<p>Specifies the type ID of the type of the variable.</p>
</dd>

### -param <i>Buffer</i> [in]

<dd>
<p>Specifies the buffer containing the data to be written.</p>
</dd>

### -param <i>BufferSize</i> [in]

<dd>
<p>Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes to be written.</p>
</dd>

### -param <i>BytesWritten</i> [out, optional]

<dd>
<p>Receives the number of bytes that were written.  If <i>BytesWritten</i> is <b>NULL</b>, this information is not returned.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p><dl>
<dt><b>S_FALSE</b></dt>
</dl><p>The method was successful.  All the bytes in the buffer <i>Buffer</i> were written.  However, the buffer was smaller than the size of the specified type.</p>

<p> </p>

## -remarks
<p>This method is only available in kernel mode debugging.</p>

<p>The number of bytes this method attempts to write is the smaller of the size of the buffer and the size of the variable.</p>

<p>This is a convenience method.  The same result can be obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549457">GetTypeSize</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561432">WritePhysical</a>.</p>

<p>For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.</p>

<p>This method is only available in kernel mode debugging.</p>

<p>The number of bytes this method attempts to write is the smaller of the size of the buffer and the size of the variable.</p>

<p>This is a convenience method.  The same result can be obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549457">GetTypeSize</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561432">WritePhysical</a>.</p>

<p>For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.</p>

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
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>