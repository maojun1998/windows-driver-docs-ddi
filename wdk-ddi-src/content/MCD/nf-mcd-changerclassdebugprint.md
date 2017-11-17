---
UID: NF.mcd.ChangerClassDebugPrint
title: ChangerClassDebugPrint
author: windows-driver-content
description: The ChangerClassDebugPrint function prints debugging information.
old-location: storage\changerclassdebugprint.htm
ms.assetid: 452377f1-a926-4f43-8168-bea11622902e
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: Storage
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ChangerClassDebugPrint
req.alt-loc: Mcd.lib,Mcd.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Mcd.lib
req.dll: 
req.irql: 
ms.keywords: ChangerClassDebugPrint
req.iface: 
---

# ChangerClassDebugPrint function



## -description
<p>The <b>ChangerClassDebugPrint</b> function prints debugging information. </p>


## -syntax

````
VOID ChangerClassDebugPrint(
   ULONG  DebugPrintLevel,
   PCCHAR DebugMessage
);
````


## -parameters
<dl>

### -param <i>DebugPrintLevel</i> 

<dd>
<p>Indicates how verbose debug information should be. Caller must assign this parameter an integer value between zero and three, where three specifies the highest level of verbosity and zero the lowest. </p>
</dd>

### -param <i>DebugMessage</i> 

<dd>
<p>Caller can specify a message to be included with the debugging information that is printed by assigning a printable ASCII character string to this parameter.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks


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
<dt>Mcd.h (include Mcd.h or Ntddchgr.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Mcd.lib</dt>
</dl>
</td>
</tr>
</table>