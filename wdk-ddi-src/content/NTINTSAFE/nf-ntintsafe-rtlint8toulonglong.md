---
UID: NF.ntintsafe.RtlInt8ToULongLong
title: RtlInt8ToULongLong
author: windows-driver-content
description: Converts a value of type INT8 to a value of type ULONGLONG.
old-location: kernel\rtlint8toulonglong.htm
ms.assetid: C840CDA4-36C8-4D7C-88EB-19292429C45C
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
req.alt-api: RtlInt8ToULongLong
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
ms.keywords: RtlInt8ToULongLong
req.iface: 
---

# RtlInt8ToULongLong function



## -description
<p>Converts a value of type <b>INT8</b> to a value of type <b>ULONGLONG</b>.</p>


## -syntax

````
NTSTATUS RtlInt8ToULongLong(
  _In_  INT8      i8Operand,
  _Out_ ULONGLONG *pullResult
);
````


## -parameters
<dl>

### -param <i>i8Operand</i> [in]

<dd>
<p>The value to be converted.</p>
</dd>

### -param <i>pullResult</i> [out]

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