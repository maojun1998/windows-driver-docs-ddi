---
UID: NF.ntintsafe.RtlLongLongToIntPtr
title: RtlLongLongToIntPtr
author: windows-driver-content
description: Converts a value of type LONGLONG to a value of type INT_PTR.
old-location: kernel\rtllonglongtointptr.htm
ms.assetid: 7BFAB50B-7C0A-40D8-AB6D-ECBBDA0387AA
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
req.alt-api: RtlLongLongToIntPtr
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
ms.keywords: RtlLongLongToIntPtr
req.iface: 
---

# RtlLongLongToIntPtr function



## -description
<p>Converts a value of type <b>LONGLONG</b> to a value of type <b>INT_PTR</b>.</p>


## -syntax

````
NTSTATUS RtlLongLongToIntPtr(
  _In_  LONGLONG llOperand,
  _Out_ INT_PTR  *piResult
);
````


## -parameters
<dl>

### -param <i>llOperand</i> [in]

<dd>
<p>The value to be converted.</p>
</dd>

### -param <i>piResult</i> [out]

<dd>
<p>A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.</p>
</dd>
</dl>

## -remarks
<p>This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.</p>

<p>This function uses the following alternate name:</p>

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