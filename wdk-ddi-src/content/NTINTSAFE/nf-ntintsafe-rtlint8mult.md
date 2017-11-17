---
UID: NF.ntintsafe.RtlInt8Mult
title: RtlInt8Mult
author: windows-driver-content
description: Multiplies one value of type INT8 by another.
old-location: kernel\rtlint8mult.htm
ms.assetid: A2551FD2-55E7-4931-887B-1CB9901F23D6
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: ntintsafe.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlInt8Mult
req.alt-loc: Ntintsafe.h
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
ms.keywords: RtlInt8Mult
req.iface: 
---

# RtlInt8Mult function



## -description
<p>Multiplies one value of type <b>INT8</b> by another.</p>


## -syntax

````
NTSTATUS RtlInt8Mult(
  _In_  INT8 i8Multiplicand,
  _In_  INT8 i8Multiplier,
  _Out_ INT8 *pi8Result
);
````


## -parameters
<dl>

### -param <i>i8Multiplicand</i> [in]

<dd>
<p>The value to be multiplied by <i>i8Multiplier</i>.</p>
</dd>

### -param <i>i8Multiplier</i> [in]

<dd>
<p>The value by which to multiply <i>i8Multiplicand</i>.</p>
</dd>

### -param <i>pi8Result</i> [out]

<dd>
<p>A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.</p>
</dd>
</dl>

## -remarks
<p>This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.</p>

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
<dt>Ntintsafe.h</dt>
</dl>
</td>
</tr>
</table>