---
UID: NF.ntintsafe.RtlULongLongToUIntPtr
title: RtlULongLongToUIntPtr
author: windows-driver-content
description: Converts a value of type ULONGLONG to a value of type UINT_PTR.
old-location: kernel\rtlulonglongtouintptr.htm
ms.assetid: A6B49838-11DE-4860-9D4C-D55D21C54157
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
req.alt-api: RtlULongLongToUIntPtr
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
ms.keywords: RtlULongLongToUIntPtr
req.iface: 
---

# RtlULongLongToUIntPtr function



## -description
<p>Converts a value of type <b>ULONGLONG</b> to a value of type <b>UINT_PTR</b>.</p>


## -syntax

````
NTSTATUS RtlULongLongToUIntPtr(
  _In_  ULONGLONG ullOperand,
  _Out_ UINT_PTR  *puResult
);
````


## -parameters
<dl>

### -param <i>ullOperand</i> [in]

<dd>
<p>The value to be converted.</p>
</dd>

### -param <i>puResult</i> [out]

<dd>
<p>A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.</p>
</dd>
</dl>

## -remarks
<p>This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.</p>

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