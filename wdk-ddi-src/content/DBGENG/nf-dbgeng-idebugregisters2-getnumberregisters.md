---
UID: NF.dbgeng.IDebugRegisters2.GetNumberRegisters
title: IDebugRegisters2::GetNumberRegisters
author: windows-driver-content
description: The GetNumberRegisters method returns the number of registers on the target computer.
old-location: debugger\getnumberregisters.htm
ms.assetid: 51c521fc-e89c-49c9-8110-de31af3bed83
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: debugger
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugRegisters.GetNumberRegisters,IDebugRegisters2.GetNumberRegisters
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
ms.keywords: IDebugRegisters2, GetNumberRegisters, IDebugRegisters2::GetNumberRegisters
req.iface: IDebugRegisters2
---

# IDebugRegisters2::GetNumberRegisters method



## -description
<p>The <b>GetNumberRegisters</b> method returns the number of <a href="debugger.x86_architecture#registers#registers">registers</a> on the target computer.</p>


## -syntax

````
HRESULT GetNumberRegisters(
  [out] PULONG Number
);
````


## -parameters
<dl>

### -param <i>Number</i> [out]

<dd>
<p>Receives the number of registers on the target's computer.</p>
</dd>
</dl>

## -returns
<p>This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>For an overview of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550825">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.</p>

<p>For an overview of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550825">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.</p>

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
<dt>Dbgeng.h (include DbgEng.h)</dt>
</dl>
</td>
</tr>
</table>