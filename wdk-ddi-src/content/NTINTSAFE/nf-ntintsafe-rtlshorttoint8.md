---
UID: NF.ntintsafe.RtlShortToInt8
title: RtlShortToInt8
author: windows-driver-content
description: Converts a value of type SHORT to a value of type INT8.
old-location: kernel\rtlshorttoint8.htm
ms.assetid: 644559BB-9842-4261-9A9C-720185E6E9F4
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
req.alt-api: RtlShortToInt8
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
ms.keywords: RtlShortToInt8
req.iface: 
---

# RtlShortToInt8 function



## -description
<p>Converts a value of type <b>SHORT</b> to a value of type <b>INT8</b>.</p>


## -syntax

````
NTSTATUS RtlShortToInt8(
  _In_  SHORT sOperand,
  _Out_ INT8  *pi8Result
);
````


## -parameters
<dl>

### -param <i>sOperand</i> [in]

<dd>
<p>The value to be converted.</p>
</dd>

### -param <i>pi8Result</i> [out]

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